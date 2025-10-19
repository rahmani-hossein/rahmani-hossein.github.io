---
title: "Bitcoin Question-Answering RAG System"
collection: portfolio
permalink: /portfolio/bitcoin-rag-system
excerpt: "A Retrieval Augmented Generation (RAG) system for answering questions from Bitcoin articles using Chroma Vector Database, Sentence Transformer, Langchain, OpenAI GPT-4, and Tavily LLM Search agent."
date: 2024-12-01
link: "https://github.com/rahmani-hossein/RAG-System"
---

A production-ready Retrieval Augmented Generation (RAG) system designed to provide accurate, context-aware answers about Bitcoin and cryptocurrency by combining vector search with large language models.

## Overview

This system demonstrates modern RAG architecture patterns, combining semantic search over a knowledge base of Bitcoin articles with GPT-4's reasoning capabilities. The integration of Tavily's search agent allows the system to augment responses with up-to-date information from the web when needed.

## Technical Stack

- **Vector Database**: Chroma for efficient semantic similarity search
- **Embeddings**: Sentence Transformers for converting text to dense vector representations
- **LLM Framework**: LangChain for orchestrating the RAG pipeline
- **Language Model**: OpenAI GPT-4 for answer generation and reasoning
- **Search Enhancement**: Tavily LLM Search agent for real-time web information

## Key Features

- **Semantic Search**: Uses dense embeddings to retrieve the most relevant Bitcoin articles based on meaning, not just keywords
- **Context-Aware Responses**: Combines retrieved documents with LLM reasoning for comprehensive answers
- **Hybrid Information Retrieval**: Falls back to web search for questions outside the knowledge base
- **Conversation Memory**: Maintains context across multiple questions for natural dialogue

## Implementation Highlights

The system follows a standard RAG pipeline:
1. Document ingestion and chunking of Bitcoin articles
2. Embedding generation using Sentence Transformers
3. Vector storage and indexing in Chroma
4. Query processing with semantic similarity search
5. Context injection and answer generation via GPT-4
6. Optional web search augmentation for current events

This project showcases practical experience with modern LLM application patterns including vector databases, embedding models, and prompt engineering for reliable question-answering systems.

[View on GitHub](https://github.com/rahmani-hossein/RAG-System) · [Documentation](https://github.com/rahmani-hossein/RAG-System#readme)
