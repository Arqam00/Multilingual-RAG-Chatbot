# Multilingual RAG Chatbot

A retrieval-augmented generation (RAG) chatbot that answers questions in multiple languages using university-domain data. Built as a Generative AI course project.

## Overview

The pipeline scrapes university-related articles from Wikipedia's Category API across 4 languages (English, German, Spanish, Dutch), then retrieves relevant context and generates grounded answers — with automatic or manual control over the output language.

## What's Included

- **Dataset Collection**: Wikipedia Category API scraping across 4 languages
- **Preprocessing Comparison**: Raw text vs. cleaned text (lowercased, whitespace-normalized, special characters removed)
- **Chunking Comparison**: RecursiveCharacterTextSplitter vs. TokenTextSplitter, tested on both raw and cleaned text
- **Retrieval Model Comparison**: `paraphrase-multilingual-MiniLM-L12-v2` vs. `intfloat/multilingual-e5-small`, evaluated using L2 distance
- **Generation Model Comparison**: `google/gemma-3-4b-it` vs. `Qwen/Qwen2.5-3B-Instruct`
- **Full RAG Pipeline**: Combines the best-performing retriever and generator, with automatic language detection or manual override (`output_lang='French'`)
- **Edge Case Testing**: In-domain queries, out-of-domain/hallucination tests, and unsupported-language handling

## Tech Stack

Python, Sentence-Transformers, HuggingFace Transformers

## How to Run

This notebook is designed and tested for Google Colab but can work for a local Jupyter environment with GPU access (recommended for model loading and inference). Open `GenAI_Project.ipynb` and run cells sequentially — Section 2 (dataset collection) can be skipped if data is already saved locally.

## Notes

Retrieval and generation models are compared side-by-side rather than fixed upfront, so the notebook doubles as a small benchmarking exercise for choosing the best embedding/generation pair for a multilingual RAG use case.
