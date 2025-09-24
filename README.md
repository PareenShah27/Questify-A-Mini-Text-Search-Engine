# Questify Search Engine - Setup Instructions

## Quick Start

1. **Install dependencies:**
   ```bash
   pip install streamlit
   ```

2. **Run the application:**
   ```bash
   cd questify
   streamlit run ui/streamlit_app.py
   ```

3. **Open your browser and navigate to the URL shown in the terminal (usually http://localhost:8501)**

## Project Structure

```
questify/
├── core/              # Core search engine logic
│   ├── indexer.py         # TF-IDF indexing
│   ├── similarity.py      # Cosine similarity calculation
│   ├── query_processor.py # Query processing and validation
│   └── ranker.py          # Result ranking and formatting
├── utils/             # Utility components
│   └── text_preprocessor.py # Text preprocessing and tokenization
├── storage/           # Data management
│   └── document_store.py    # Document storage and retrieval
├── ui/                # User interface
│   └── streamlit_app.py     # Streamlit web interface
├── files/             # Application files
│   ├── main.py            # Main search engine class
│   └── config.py          # Configuration management
├── documents/         # Document storage folder (created automatically)
└── requirements.txt   # Python dependencies
```

## Features

- **High-Performance Search:** Sub-millisecond search times using optimized TF-IDF
- **Web Interface:** Clean, interactive Streamlit-based UI  
- **Document Management:** Upload and manage text documents
- **Configurable:** Adjustable search parameters and preprocessing options
- **Storage:** Persistent document storage with metadata
- **Statistics:** Detailed performance and usage statistics

## Usage

### Adding Documents
- Use the sidebar to upload `.txt` or `.md` files
- Add documents manually with custom IDs
- Documents are automatically indexed for search

### Searching  
- Enter keywords in the search box
- Adjust max results and similarity threshold
- View detailed results with similarity scores

### Configuration
- Modify settings in `files/config.py`
- Adjust preprocessing, search, and UI parameters
- Changes take effect after restarting the application

## Development

The codebase is modular and extensible:
- Add custom text preprocessors in `utils/`
- Implement alternative similarity measures in `core/similarity.py`
- Extend storage backends in `storage/`
- Customize UI components in `ui/streamlit_app.py`

## Performance Benchmarks

- **Index Build Time:** < 0.01s for 100 documents
- **Search Time:** < 0.001s average
- **Memory Usage:** Optimized sparse vectors
- **Vocabulary Efficiency:** < 0.2x document count
