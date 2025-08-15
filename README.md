# 🤖 Auto Data Analyst

Welcome to Auto Data Analyst, an intelligent agent that transforms natural language questions into data-driven insights. Powered by Google's Gemini, this application can scrape web data, analyze datasets, and generate visualizations, acting as your personal data science assistant.


## ✨ Core Features

-   **Natural Language Processing**: Ask questions in plain English and get intelligent, accurate answers.
-   **Automated Web Scraping**: Extracts data from any URL, automatically parsing tables and text.
-   **Versatile Data Support**: Natively handles `CSV`, `Excel`, `JSON`, and `Parquet` files.
-   **Dynamic Visualizations**: Generates `Matplotlib` and `Seaborn` plots on-the-fly, delivered as images.
-   **AI-Powered Code Generation**: The agent writes and executes its own Python code to fulfill your requests.
-   **Simple & Fast Deployment**: Pre-configured for seamless deployment to Railway with Docker.

---

## ⚙️ How It Works

This isn't just another data tool. The Auto Data Analyst operates through a sophisticated, multi-step process:

1.  **Ingestion**: The FastAPI backend receives your questions and optional data files.
2.  **AI Analysis**: A LangChain agent, equipped with Google's Gemini model, analyzes your request. It determines whether to use the provided dataset or to scrape a new one from a URL.
3.  **Code Generation**: The agent writes a custom Python script using Pandas and other libraries to perform the required analysis.
4.  **Secure Execution**: This script is run in a secure, isolated environment. Any charts are saved as base64-encoded images.
5.  **Response**: The final results, including data and visualizations, are packaged into a clean JSON response and sent back to the user interface.

---

## 🚀 Getting Started

You can get the Auto Data Analyst running on your local machine in just a few steps.

### Prerequisites

-   Python 3.9+
-   A **Google Generative AI API Key**. You can get one [here](https://aistudio.google.com/apikey).

### Local Installation

1.  **Clone the Repository**
    ```bash
    git clone [https://github.com/Krishnandu8/Auto-Data-Analyst.git](https://github.com/Krishnandu8/Auto-Data-Analyst.git)
    cd Auto-Data-Analyst
    ```

2.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Configure Your Environment**
    Create a file named `.env` in the project root and add your API key:
    ```
    GOOGLE_API_KEY="YOUR_GOOGLE_API_KEY_HERE"
    ```

4.  **Run the Server**
    Launch the application with Uvicorn:
    ```bash
    uvicorn app:app --reload
    ```
    Your agent is now live at `http://localhost:8000`.

---

## ☁️ Deployment to Railway

This project is built to deploy effortlessly on Railway.

1.  **Push to GitHub**: Make sure your local repository is up-to-date with your GitHub repository.
2.  **Create a New Railway Project**: From your Railway dashboard, select "Deploy from GitHub repo".
3.  **Select Your Repository**: Choose the `Auto-Data-Analyst` repository. Railway will automatically detect the `Dockerfile` and start the build process.
4.  **Add Your API Key**: In your new Railway project, navigate to the "Variables" tab and add your `GOOGLE_API_KEY`. The application will not work without it.

That's it! Railway will handle the rest and provide a public URL for your deployed application.

---

## 📄 License

This project is open-source and available under the **MIT License**. See the `LICENSE` file for more details.
````