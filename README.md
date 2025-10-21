# Building-a-Smart-OCR-Bot
# Intelligent Document Automation: Building a Smart OCR Bot 📄🤖

This project demonstrates how to build a "Smart OCR Bot" capable of extracting text from images (implicitly performing Optical Character Recognition - OCR) and answering natural language questions about the content using a multimodal Large Language Model (LLM). It leverages Google's Gemini Pro Vision model via the Google Generative AI API.

The notebook showcases loading an image, preparing prompts, interacting with the Gemini Vision model to interpret the image and text, and extracting structured information or answers based on user queries. It also includes the basic structure for deploying this logic as a Streamlit web application.

**LLM:** Google Gemini Pro Vision
**Framework:** Google Generative AI SDK
**Task:** Multimodal Question Answering (Image + Text Input -> Text Output) / Smart OCR
**Focus:** Demonstrating the use of multimodal LLMs for document understanding, API integration, prompt engineering for image-based queries, and basic Streamlit app structure.
**Repository:** [https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot](https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot)

***

## Key Techniques & Concepts Demonstrated

Based on the analysis within the notebook (`16_Intelligent_Document_Automation_Building_a_Smart_OCR_Bot.ipynb`), the following key concepts and techniques are applied:

* **Multimodal Large Language Models (LLMs):** Utilizing Google Gemini Pro Vision, which can process both image and text inputs simultaneously.
* **Implicit OCR:** The LLM performs text extraction from the image as part of its understanding process without needing a separate traditional OCR library.
* **Visual Question Answering (VQA):** Answering text-based questions based on the content of an input image.
* **Information Extraction:** Using prompts to guide the LLM in extracting specific pieces of information (like invoice details, items, totals) from the document image.
* **API Integration:** Interfacing with the Google Generative AI API using the Python SDK.
* **Prompt Engineering:** Crafting effective text prompts to instruct the LLM on what information to find or what question to answer based on the provided image.
* **Image Handling:** Using the Pillow (PIL) library to open and handle image files.
* **Streamlit Application Framework:** Basic code structure provided to build an interactive web application allowing users to upload images and ask questions.

***

## Analysis Workflow

The notebook follows a workflow for building and testing the core logic of the Smart OCR Bot:

1.  **Setup & Dependencies:**
    * Installing necessary libraries (`google-generativeai`, `python-dotenv`, `streamlit`, `Pillow`).
    * Importing required modules (`genai`, `PIL`, `streamlit`, `os`, `dotenv`).
2.  **API Key Configuration:** Loading the Google API key from environment variables using `dotenv`. Configuring the `genai` SDK with the key.
3.  **LLM Initialization:** Initializing the Gemini Pro Vision model (`genai.GenerativeModel('gemini-pro-vision')`).
4.  **Helper Function Definition:** Creating a function (`get_gemini_response`) that takes an input prompt and an image, sends them to the Gemini model, and returns the generated text response.
5.  **Image Loading:** Opening the target image file (`invoice.png`) using `PIL.Image.open()`.
6.  **Prompt Definition & Querying:**
    * Defining an initial text prompt/question (e.g., "What is the invoice total?").
    * Calling the `get_gemini_response` function with the prompt and the loaded image.
    * Printing the LLM's response.
7.  **Streamlit Application Structure (Conceptual):**
    * Providing commented-out or separate code blocks outlining how to build a Streamlit interface:
        * Setting up the page title.
        * Creating an input field for the user's question/prompt.
        * Creating a file uploader for the image.
        * Displaying the uploaded image.
        * Adding a button to trigger the analysis.
        * Calling the `get_gemini_response` function upon button click.
        * Displaying the LLM's response.

***

## Technologies Used

* **Python**
* **Google Generative AI SDK (`google-generativeai`):** For interacting with the Google Gemini Pro Vision LLM.
* **Pillow (`PIL`):** For opening and handling image files.
* **Streamlit:** Framework for building the interactive web application UI.
* **python-dotenv:** For managing API keys securely.
* **Jupyter Notebook / Google Colab:** For the interactive development and testing environment.

***

## Prerequisites

1.  **Google API Key:** You need an API key for Google Generative AI. Obtain one from [Google AI Studio](https://aistudio.google.com/).
2.  **Sample Image:** An image file (e.g., `invoice.png` as used in the notebook) containing text for the bot to process.
3.  **Environment Variable:** Store your Google API key in a `.env` file in the project directory with the key `GOOGLE_API_KEY`.
    ```
    GOOGLE_API_KEY="YOUR_API_KEY_HERE"
    ```

***

## How to Run the Project (Core Logic & Streamlit App)

**1. Run Core Logic in Notebook:**

* **Clone the repository:**
    ```bash
    git clone [https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot.git](https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot.git)
    cd Building-a-Smart-OCR-Bot
    ```
* **Install dependencies:**
    (It is recommended to use a virtual environment)
    ```bash
    pip install google-generativeai python-dotenv Pillow jupyter streamlit
    ```
* **Set up Prerequisites:**
    * Create a `.env` file in the root directory and add your `GOOGLE_API_KEY`.
    * Ensure the sample image (e.g., `invoice.png`) is in the directory.
* **Launch Jupyter Notebook:**
    ```bash
    jupyter notebook "16_Intelligent_Document_Automation_Building_a_Smart_OCR_Bot.ipynb"
    ```
* **Run Cells:** Execute the cells sequentially to test the interaction with the Gemini API using the sample image and prompts.

**2. Run as a Streamlit App:**

* **Create App File:** Save the Streamlit-specific code blocks from the notebook into a Python file (e.g., `app.py`) in the repository directory. Ensure this file includes the necessary imports, API key loading, `get_gemini_response` function, and the `st.` elements for UI.
* **Run Streamlit:** Open your terminal in the repository directory and run:
    ```bash
    streamlit run app.py
    ```
* **Interact:** Open the provided local URL in your web browser. Upload an image, type a question in the input box, and click the "Tell me about the invoice" button.

***

## Author & Portfolio Use

* **Author:** Jayasurya227
* **Portfolio:** This project ([https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot](https://github.com/Jayasurya227/Building-a-Smart-OCR-Bot)) showcases the ability to leverage state-of-the-art multimodal LLMs (Gemini Vision) for practical document automation tasks that traditionally required complex OCR pipelines. It demonstrates skills in API integration, prompt engineering, and building interactive AI applications (with Streamlit). Suitable for GitHub, resumes/CVs, LinkedIn, and interviews for AI/ML Engineer, NLP/CV Engineer, or Full Stack Developer roles with AI integration focus.
* **Notes:** Recruiters can see the application of advanced AI models to solve real-world problems like extracting information from documents (invoices, receipts, etc.) using natural language interaction. The inclusion of Streamlit also demonstrates UI development capabilities for AI applications.
