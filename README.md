# Chatbot
import openai
<br>
openai.api_key = "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"
<br>
def chat_with_gpt(prompt):
    response = openai.ChatCompletion.create(
        model = "gpt-3.5-turbo",
        messages = [{"role": "user", "content": prompt}]
    )
<br>
    return response.choices[0].messsage.content.strip()
<br>
if __name__=="__main__":
    while True:
        user_input = input("You:  ")
        if user_input.lower() in ["quit", "exit", "bye"]:
            break
<br>
        response = chat_with_gpt(user_input)
        print("Chatbot: ", response)
