# ai-story-writer

A small FastAPI-based project that searches the web for information about a location, extracts website content, and generates an Instagram Reel-style story in Hindi using OpenAI.

## Features

- FastAPI backend with a single story generation endpoint
- Google search integration to find relevant web pages for a query
- Website content extraction using BeautifulSoup
- LLM-based story generation using OpenAI
- Saves raw, extracted, and generated results to `data/`

## Project Structure

- `main.py` - FastAPI application entry point
- `api/routes.py` - API router registration
- `api/endpoints/story_writer.py` - main endpoint logic for search, extraction, and story generation
- `core/config.py` - environment and configuration management
- `scripts/google_search.py` - Google search helper
- `scripts/content_extractor.py` - website scraping and content extraction
- `scripts/llm_processor.py` - OpenAI prompt creation and response processing
- `data/` - storage for generated JSON and text output files

## Requirements

- Python 3.11 or newer
- `OPENAI_API_KEY` environment variable set

## Workflow

1. Submit a location or place query to `/api/v1/fetch-websites`
2. The API performs a Google search and saves raw URLs
3. It fetches and extracts text content from those websites
4. The extracted content is sent to OpenAI to generate a reel-style story
5. Results are stored under `data/` as JSON and text files

