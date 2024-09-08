# flask-app-gpt (sentiment) api

## Template openai connect model
```python
import openai

# Set your OpenAI API key
openai.api_key = "*****"

# Define the text you want to analyze or interact with
text = "กำหนดหัวข้อโปรเจค 'น้ำหอมกลิ่นหัวแมวเหมียวของตัวเอง'เพื่อแก้ปัญหาคิดถึงแมวที่บ้าน"

# Make a request to the OpenAI GPT-3.5 API
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo-0125",
    messages=[
        # prompt
        {"role": "system", "content": "ช่วยหาวิธีทำ และ แนวทางนำไปพัฒนาต่อในธุรกิจ"},
        {"role": "user", "content": text}
    ]
)

# Extract the response text
response_text = response['choices'][0]['message']['content'].strip()

print("Response from GPT-3.5:", response_text)
