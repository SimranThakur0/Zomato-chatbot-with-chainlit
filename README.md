# Zomato OrderBot Chat Application with Chainlit

## 📋 **Project Overview**
Zomato OrderBot is an AI-powered chatbot application that allows users to place orders for food items via an interactive chat interface. The assistant helps users browse the menu, select items, choose between delivery or pickup, and process payment in a friendly and conversational manner.

This project utilizes **OpenAI's GPT-3.5-turbo** to manage conversations and **Chainlit** to build the user interface for chat interactions.

---

## 🛠️ **Project Structure**
```
Zomato-OrderBot/
├── src/
│   ├── llm_model.py     # Handles OpenAI API calls and logic for generating chatbot responses
│   ├── prompt.py        # Contains the system instruction prompt for the chatbot
│
├── .env                 # Contains the OpenAI API key
├── app.py               # Main file to run the Chainlit app
├── requirements.txt     # List of all dependencies for the project
├── README.md            # Documentation file (You are reading this!)
```

---

## 🚀 **How It Works**
1. **User Interaction**: Users send a message to the chatbot through a Chainlit-powered chat interface.
2. **Order Handling**: The chatbot responds with the Zomato menu, takes user orders, and confirms if it's for delivery or pickup.
3. **Order Confirmation**: Once the order is complete, the chatbot summarizes the order and confirms it with the user.
4. **Payment Processing**: Finally, the chatbot requests payment details to complete the order.

---

## 📚 **Features**
- 🛒 **Menu Browsing**: View and select items from a diverse menu of pizzas, pastas, Asian cuisine, Indian cuisine, and beverages.
- 🤖 **Interactive Chat**: Order items directly from a chat-based UI.
- 🛵 **Delivery or Pickup**: Option to choose between home delivery or store pickup.
- 💳 **Payment Request**: Processes and confirms payments (simulated for this demo).
- ⚙️ **Customizable Menu**: Easily update menu items and prices via the `prompt.py` file.

---

## 📦 **Installation**

### **1️⃣ Clone the Repository**
```bash
$ git clone https://github.com/your-username/zomato-orderbot.git
$ cd zomato-orderbot
```

### **2️⃣ Create a Virtual Environment**
```bash
$ python -m venv venv
$ source venv/bin/activate   # On Windows use `venv\Scripts\activate`
```

### **3️⃣ Install Required Packages**
```bash
$ pip install -r requirements.txt
```

### **4️⃣ Set Up Environment Variables**
Create a `.env` file in the project root and add your OpenAI API key as follows:
```env
OPENAI_API_KEY=your_openai_api_key_here
```
> **Note:** You need to have an active OpenAI API key. You can get it from [OpenAI](https://platform.openai.com/account/api-keys).

---

## 📋 **Usage Instructions**

### **1️⃣ Run the Chat Application**
```bash
$ chainlit run app.py
```
If everything is set up correctly, you should see this in the terminal:
```
2024-12-13 00:53:25 - Loaded .env file
2024-12-13 00:53:27 - Your app is available at http://localhost:8000
```

### **2️⃣ Interact With the Chatbot**
Open a web browser and go to [http://localhost:8000](http://localhost:8000). Interact with the chatbot to browse the menu, place an order, and choose delivery or pickup.

---

## 🗂️ **File Descriptions**

- **`app.py`**: The main entry point for running the Chainlit app. It listens for user messages, appends them to the message history, and calls the OpenAI API for a response.
- **`src/llm_model.py`**: Contains the function `ask_order()` that interacts with OpenAI's GPT-3.5-turbo model to generate responses for user queries.
- **`src/prompt.py`**: Contains the system instruction prompt that guides the AI on how to respond to user input.
- **`.env`**: File for environment variables like `OPENAI_API_KEY`.
- **`requirements.txt`**: List of Python libraries required to run the project.

---

## ⚙️ **Customization**

### **Update the Menu**
If you'd like to update the menu (add, remove, or change items), edit the `src/prompt.py` file under the `# Zomato Menu` section. Example:
```python
## Pizzas
- Cheese Pizza (12 inch) - $9.99
- Pepperoni Pizza (12 inch) - $10.99
- Hawaiian Pizza (12 inch) - $11.99
```

### **Change System Instructions**
To modify the chatbot's behavior, you can update the system instructions in `src/prompt.py`.
```python
system_instruction = """
You are Zomato OrderBot, an automated service to collect orders for an online restaurant...
"""
```
This file controls how the AI assistant behaves when talking to users.

---

## 🧪 **Example Chat**
```
**User:** Hi, I want to order pizza.

**Zomato OrderBot:** Sure! Here are the pizzas we have:
- Cheese Pizza ($9.99)
- Pepperoni Pizza ($10.99)
- Hawaiian Pizza ($11.99)
Which one would you like?

**User:** I'll have the Pepperoni Pizza.

**Zomato OrderBot:** Great! Do you want it for pickup or delivery?

**User:** Delivery.

**Zomato OrderBot:** Please provide your delivery address.

**User:** 123 Main Street, Springfield.

**Zomato OrderBot:** Got it! Here's your order:
- 1x Pepperoni Pizza ($10.99)
Delivery to: 123 Main Street, Springfield
Would you like to add anything else?
```

---

## 🛠️ **Troubleshooting**

### **1️⃣ OpenAI Quota Error**
If you see this error:
```
openai.RateLimitError: You exceeded your current quota.
```
**Solution:**
- Check if your OpenAI API key is valid.
- Make sure you have an active billing plan on the OpenAI platform.
- Verify your API key is being loaded correctly from the `.env` file.

### **2️⃣ No Response From the Assistant**
- Ensure the OpenAI API key is set in the `.env` file.
- Check that the `messages` list is updating with every user message.
- Restart the Chainlit server to make sure changes are applied.

---

## 🔧 **Technologies Used**
- **Python**: Main programming language for the project.
- **OpenAI GPT-3.5**: AI model used for chat responses.
- **Chainlit**: Framework for building conversational interfaces.

---

## 📄 **Requirements**
- Python 3.8+
- An OpenAI API key (create one at [OpenAI](https://platform.openai.com/account/api-keys))
- Internet access (to connect with OpenAI's API)

---

## 🤝 **Contributing**
If you'd like to contribute, feel free to fork the repository and submit a pull request. Contributions are welcome!

---

## 📜 **License**
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.

---

## 🙌 **Acknowledgments**
- Thanks to [OpenAI](https://openai.com/) for providing the GPT-3.5-turbo model.
- Thanks to the [Chainlit](https://www.chainlit.io/) team for creating a powerful conversational interface.

---

If you found this project useful, please ⭐️ star this repository on GitHub!

