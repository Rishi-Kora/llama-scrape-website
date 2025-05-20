# llama-scrape-website
A project that scrapes a website, processes its content into embeddings, stores them in a Chroma vector database, and provides a conversational retrieval interface powered by LangChain, OpenAI, and Gradio.

## Features

- **Web Scraping**: Uses a custom `Website` loader to fetch title, text, and links from any URL.
- **Document Splitting**: Splits long text into manageable chunks for efficient embedding.
- **Embeddings & Vector Store**: Generates embeddings via OpenAI or Hugging Face models and persists them in Chroma.
- **Conversational Retrieval**: Builds a conversational chain that retrieves relevant document chunks to answer user queries.
- **Interactive UI**: Launches a Gradio web app to enter URLs and chat with the scraped content.

## Requirements

- Python 3.8+
- An OpenAI API key (set `OPENAI_API_KEY` in a `.env` file)
- (Optional) Hugging Face API token for remote inference

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/llama-scrape-website.git
   cd llama-scrape-website
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key
   ```

5. (Optional) If using Hugging Face Inference API:
   ```env
   HUGGINGFACEHUB_API_TOKEN=your_hf_api_token
   ```

## Usage

### Jupyter Notebook

1. Launch Jupyter:
   ```bash
   jupyter notebook llama_scrape_website.ipynb
   ```
2. Walk through the notebook cells to scrape a website, build your vector store, and test queries.

### Gradio App

1. Run the Gradio script:
   ```bash
   python app.py
   ```
2. Open the URL printed in your terminal to enter a website URL and chat with the content.

## Configuration

- **`db_name`**: Directory name for the Chroma vector database (default: `scrape_website`).
- **`MODEL`**: AI model name (default: `o4-mini`, change to `gpt-4` or other supported model).
- **`chunk_size`** & **`chunk_overlap`**: Character-based splitting parameters in the notebook.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/new-feature`.
3. Commit your changes: `git commit -m "Add new feature"`.
4. Push to the branch: `git push origin feature/new-feature`.
5. Open a Pull Request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
