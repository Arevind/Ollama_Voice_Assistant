# Ollama Voice Assistant 🎙️

A powerful, voice-controlled personal AI assistant built with Python, integrating speech recognition, text-to-speech, and Langchain with Ollama’s Gemma model. 🚀

---

## 📌 Features

- 🎧 **Speech Recognition:** Uses Google’s speech recognition to understand user queries.
- 🗣️ **Text-to-Speech:** Responds back using `pyttsx3` with a customizable speech rate.
- 🧠 **AI-Powered Responses:** Utilizes `Langchain` with the Ollama Gemma model to generate dynamic, context-aware answers.
- 🔄 **Conversation Memory:** Maintains a conversation history, so responses stay contextual and natural.
- 🛠️ **Easy Interaction:** Just talk to it — say "exit" to stop.

---

## 🛠️ Setup Instructions

### 1️⃣ Prerequisites

Ensure you have the following installed:

- **Python 3.8+**
- **Pip**
- **Ollama** (Follow instructions at [Ollama's official site](https://ollama.ai))
- **Gemma Model** (Download by running `ollama pull gemma3:1b-it-fp16`)

### 2️⃣ Clone the Repository

```bash
$ git clone https://github.com/yourusername/Ollama_voice_assistant.git
$ cd Ollama_voice_assistant
```

### 3️⃣ Install Required Packages

```bash
$ pip install speechrecognition pyttsx3 langchain langchain_community langchain_core langchain_ollama
```

### 4️⃣ Run the Assistant

```bash
$ python PersonalAI.py
```

---

## 🔧 How It Works

1. The assistant **greets you** and asks how it can help.
2. It **listens** for your query.
3. It **processes** the query using **Langchain** and **Ollama’s Gemma** AI model.
4. It **responds** both in text and speech.
5. The assistant **remembers** previous interactions for better conversation flow.

✅ **Example conversation:**

```
You: What's the weather like today?
AI: I’m not connected to live data, but it’s always a good day to learn something new!

You: Can you help me summarize Langchain?
AI: Sure! Langchain is a framework designed to build applications powered by language models. It helps with prompts, memory, and more.
```

---

## 🛠️ Code Breakdown

### 🗣️ Speech Recognition

```python
recognizer = sr.Recognizer()
with sr.Microphone() as source:
    audio = recognizer.listen(source)
```

### 🔊 Text-to-Speech

```python
engine = pyttsx3.init()
engine.say("Hello! How can I help you today?")
engine.runAndWait()
```

### 🔥 AI Response with Langchain & Ollama

```python
llm = OllamaLLM(model = "gemma3:1b-it-fp16")
prompt = PromptTemplate(
    input_variables=["chat_history", "question"],
    template="Previous conversation: {chat_history}\nUser: {question}\nAI:"
)
response = llm.invoke(prompt.format(chat_history=chat_history_text, question=query))
```

---

## 🔮 Future Improvements

- 🎵 **Music control integration**
- 🌐 **Web search capabilities**
- 💬 **Multi-language support**
- 🔗 **API integration (e.g., weather, news)**

---

## 🏅 Credits

Made with ❤️ by Arevind Mohan

Special thanks to the creators of **Langchain**, **Ollama**, and **SpeechRecognition**!

---

## 📜 License

This project is licensed under the **MIT License** — feel free to fork, improve, and contribute!
