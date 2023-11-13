# openai_debugging
Set of tricks that worked for me.


openai.OpenAIError: The api_key client option must be set either by passing api_key to the client or by setting the OPENAI_API_KEY environment variable.
Solution: Use dotenv to load env variables.

```
from openai import OpenAI
import os
from dotenv import load_dotenv

# this by deafult uses option 1
# client = OpenAI()

# 1. pass your api key from env variable: (recommended) ------------

# Load environment variables from .env file into os.environ
load_dotenv()

client = OpenAI(api_key=os.environ.get("OPENAI_API_KEY"))


# 2. pass your api key inside client call: (not recommended) ---------------

#OPENAI_API_KEY='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'
#client = OpenAI(api_key=OPENAI_API_KEY)
```


