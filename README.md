# PythonOpenAI
An example of utilizing OpenAI as a healthcare bot offering recommended benefits and supportive visuals

Empower and elevate the healthcare experience with OpenAI as a personalized healthcare buddy and trusted companion by providing basic information, and in return, receive tailored benefits recommendations, uplifting visuals for encouragement, immediate access to credible resources such as helplines and cognitive behavioral therapy programs, and professional guidance on lifestyle modifications for optimal physical and mental health.

This Python program tests the concept by allowing users to enter basic information and receive personalized recommendations and supporting visuals.

```
pip install openai
```

```
import openai
openai.api_key = "<OpenAI API Key>"
model_engine = "text-davinci-003"
prompt = "top 3 benefiits for improve cardio, precise, summerized, persuading, convincing"


# Creating completion
completion = openai.Completion.create(
    engine=model_engine,
    prompt=prompt,
    max_tokens=1024,
    n=1,
    temperature=0,
    top_p = 1,
    stream = False,
    stop= None,
)

response = completion.choices[0].text
print(response)

# Creating an Image
image = openai.Image.create(
  prompt="A lady doing cardio, photorealistic, Full View, Dark background",
  n=1,
  size="512x512"
)

image_url = image.data[0].url
print(image_url)

```

Sample response

```
1. Increased Energy: Improved cardiovascular health can lead to increased energy levels, allowing you to stay active and productive throughout the day.

2. Reduced Risk of Disease: Regular cardio exercise can help reduce the risk of heart disease, stroke, diabetes, and other chronic illnesses.

3. Improved Mental Health: Cardio exercise can help reduce stress, improve mood, and increase overall mental wellbeing.

[https://oaidalleapiprodscus.blob.core.windows.net/private/org-wC3H6P6m7dlxyBbmi6OCTpMA/user-A8VP5Df22Wddd1wDlKtWj6TW/img-oP9JO5RPr9LrjU9633JH3Uxr.png?st=2023-02-08T03%3A19%3A00Z&se=2023-02-08T05%3A19%3A00Z&sp=r&sv=2021-08-06&sr=b&rscd=inline&rsct=image/png&skoid=6aaadede-4fb3-4698-a8f6-684d7786b067&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2023-02-07T21%3A33%3A08Z&ske=2023-02-08T21%3A33%3A08Z&sks=b&skv=2021-08-06&sig=3LrYz29nzEzrL8eMzYpHh0dOQ6l2RfdU0OC8PzU31pQ%3D](https://oaidalleapiprodscus.blob.core.windows.net/private/org-wC3H6P6m7dlxyBbmi6OCTpMA/user-A8VP5Df22Wddd1wDlKtWj6TW/img-oP9JO5RPr9LrjU9633JH3Uxr.png?st=2023-02-08T03%3A19%3A00Z&se=2023-02-08T05%3A19%3A00Z&sp=r&sv=2021-08-06&sr=b&rscd=inline&rsct=image/png&skoid=6aaadede-4fb3-4698-a8f6-684d7786b067&sktid=a48cca56-e6da-484e-a814-9c849652bcb3&skt=2023-02-07T21%3A33%3A08Z&ske=2023-02-08T21%3A33%3A08Z&sks=b&skv=2021-08-06&sig=3LrYz29nzEzrL8eMzYpHh0dOQ6l2RfdU0OC8PzU31pQ%3D)
```
