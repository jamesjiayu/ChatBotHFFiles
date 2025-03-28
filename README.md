# CodeLlama Chatbot with Document Context

This is a Gradio-based chatbot application that utilizes the CodeLlama-34b-Instruct-hf model from Hugging Face for conversational interactions. It allows users to upload `.txt` or `.docx` files to provide additional context for the chatbot's responses.

## Features

* **Chat Interface:** A user-friendly chat interface powered by Gradio.
* **Document Context:** Users can upload `.txt` or `.docx` files to provide context for the chatbot.
* **CodeLlama Model:** Uses the CodeLlama-34b-Instruct-hf model for generating responses.
* **Parameter Tuning:** Users can adjust `max_tokens` and `temperature` for response generation.
* **Error Handling:** Robust error handling for network issues, invalid inputs, and unexpected exceptions.
* **Logging:** Uses Python's `logging` module to log execution details and errors.
* **Environment Variables:** Uses `.env` files to securely manage the Hugging Face API key.

## Prerequisites

* Python 3.6+
* `pip` (Python package installer)
* Hugging Face API key (stored in a `.env` file)

## Installation

1.  **Clone the repository (if applicable):**
    ```bash
    git clone <your-repository-url>
    cd <your-repository-directory>
    ```

2.  **Install dependencies:**
    ```bash
    pip install gradio huggingface_hub python-docx python-dotenv
    ```

3.  **Create a `.env` file:**
    * In the same directory as your Python script, create a file named `.env`.
    * Add your Hugging Face API key to the `.env` file:
        ```
        HUGGINGFACE_API_KEY=your_huggingface_api_key
        ```
        * Replace `your_huggingface_api_key` with your actual API key.

4.  **Run the application:**
    ```bash
    python your_script_name.py
    ```
    * Replace `your_script_name.py` with the actual name of your Python script.

## Usage

1.  **Launch the application:** Run the Python script.
2.  **Chat with the chatbot:** Enter your messages in the chat interface.
3.  **Upload a file (optional):** Upload a `.txt` or `.docx` file to provide additional context.
4.  **Adjust parameters:** Use the sliders to adjust `max_tokens` and `temperature`.
5.  **View responses:** The chatbot's responses will appear in the chat interface.

## Code Explanation

* **`respond(current_msg, history_msg, max_tokens, temperature, file)`:**
    * This function handles the chatbot's response generation.
    * It takes the current message, chat history, `max_tokens`, `temperature`, and uploaded file as input.
    * It constructs the system message, including any context from the uploaded file.
    * It uses the Hugging Face `InferenceClient` to interact with the CodeLlama model.
    * It handles potential errors and logs execution details.
* **`chatbot = gr.ChatInterface(...)`:**
    * This creates the Gradio chat interface.
    * It specifies the `respond` function as the chatbot's response generator.
    * It adds input components for `max_tokens`, `temperature`, and file upload.
* **`.env` and API Key:**
    * The `.env` file and `load_dotenv()` are used to securely manage the Hugging Face API key.
    * This prevents the API key from being hardcoded in the script.
* **File Handling:**
    * The code handles `.txt` and `.docx` files, extracting the text content for context.
    * The `python-docx` library is used for `.docx` files.
* **Logging:**
    * The `logging` module is used to log execution details and errors.

## Dependencies

* `gradio`
* `huggingface_hub`
* `python-docx`
* `python-dotenv`

## Notes

* Ensure your Hugging Face API key is correctly set in the `.env` file.
* The CodeLlama-34b-Instruct-hf model might require significant resources.
* Error handling is included, but further testing is recommended.
* The current time placeholder in the file output needs to be replaced with the actual current time implementation.
