# Chain of Draft Prompting Implementation
This repository showcases how to implement Chain of Draft prompting example with source code using Groq and Google Geminii.

## Steps to Implement Chain-of-Draft (CoD) Prompting

### **Step 1: Get the API Key**
Sign up on the platform:
- For **Gemini**: Go to [Google AI Studio](https://aistudio.google.com/app/prompts) and generate an API key.
- For **Groq**: Visit [Groq Cloud](https://console.groq.com/), log in, and create an API key.

---

### **Step 2: Install Required Libraries**
Use pip to install the SDKs:

```bash
# For Gemini
pip install google-genai

# For Groq
pip install groq --quiet
```
---

### **Step 3: Import Libraries & Set Up API Key**
Import the necessary libraries and set your API key securely as an environment variable:

```python
import os
# For Gemini
os.environ["GEMINI_API_KEY"] = "your_gemini_api_key_here"

# For Groq
os.environ["GROQ_API_KEY"] = "your_groq_api_key_here"
```
---

### **Step 4: Define the Generation Function**
Write a function to query the model with the CoD prompt style.

System prompt format:
> “Think step by step, but only keep a minimum draft for each thinking step, with 5 words at most. Return the answer at the end of the response after a separator ####.”

You'll pass this prompt with your question and optional example to the model.

---

### **Step 5: Run the Model with Inputs**
You can try two methods:
- **Zero-shot prompting**: Only system prompt + question.
- **One-shot prompting**: Add a similar example followed by your new question.

Both can help you observe how well the model performs with or without examples.
