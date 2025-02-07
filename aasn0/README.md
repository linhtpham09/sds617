
## Set up Python

Ensure you have Python installed. If not, you can download it from [python.org](https://www.python.org/). You'll also need `pip` to install packages. 

You will need to install the `openai` package. 
```commandline
pip install openai
```

## Set your API key in Python
This is the most secure method to set your API key. Set your API key as an environment variable and then access it within your script. 
**You should not hard-code your key into the script or Python notebook directly.**

### Step 1: Create a `.env` File
1. Open a text editor and create a new file named `.env`.
2. Add the OpenAI API key in the following format:
    OPENAI_API_KEY=your_openai_api_key_here
3. Save the file in the root directory of your project.

### Step 2: Install `python-dotenv`
Install the `python-dotenv` library to load environment variables from the `.env` file into your Python application.

Run the following command:
```bash
pip install python-dotenv
```

### Step 3: Load the `.env` File in Python
Use the `dotenv` module to read the `.env` file and access the API key.

Here’s an example Python script:

```python
import os
from dotenv import load_dotenv

# Load environment variables from the .env file
load_dotenv()

# Access the OpenAI API key
openai_api_key = os.getenv("OPENAI_API_KEY")

# Use the API key
if openai_api_key:
    print("OpenAI API Key loaded successfully!")
else:
    print("OpenAI API Key not found. Please check your .env file.")
```

### Step 4: Add `.env` to `.gitignore`
To prevent accidentally exposing your API key when using version control, add `.env` to your `.gitignore` file:
```bash
.env
```