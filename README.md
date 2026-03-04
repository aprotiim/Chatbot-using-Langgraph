# Multi-Utility AI Chatbots with LangGraph, MCP & RAG

This repository contains two production-style AI chatbots built using LangGraph + LangChain + OpenAI models + Streamlit.

The project demonstrates modern LLM application architecture, including:

* Tool-using AI agents

* MCP (Model Context Protocol) integration

* Retrieval Augmented Generation (RAG)

* Persistent conversation memory

* Multi-thread chat sessions

* Streaming responses

* The repository includes two independent chatbots:

1️⃣ LangGraph MCP Tool Agent
2️⃣ LangGraph RAG PDF Chatbot

Both chatbots share the same core design philosophy: LLM orchestration using LangGraph state machines.

## Architecture Overview

<img width="376" height="465" alt="image" src="https://github.com/user-attachments/assets/99600ae7-54bf-4474-af60-7b1c6486383a" />


# Chatbot 1 — LangGraph MCP Tool Agent
Files

Backend: 

langgraph_mcp_backend

Frontend: 

streamlit_frontend_mcp

## Description

This chatbot demonstrates LLM agents that can dynamically call tools using LangGraph orchestration and Model Context Protocol (MCP).

The LLM decides whether to:

* answer directly

* call a tool

* chain multiple tool calls

## Implemented Tools
| Tool               | Description                                     |
| ------------------ | ----------------------------------------------- |
| Web Search         | DuckDuckGo search integration                   |
| Stock API          | Fetch real-time stock prices using AlphaVantage |
| MCP Math Server    | External MCP server performing arithmetic       |
| MCP Expense Server | External MCP microservice                       |
| ToolNode           | LangGraph automatic tool execution              |

## LangGraph Agent Workflow
<img width="382" height="352" alt="image" src="https://github.com/user-attachments/assets/b1042a60-aedf-4027-a44c-b7f938187daf" />
This loop continues until the LLM produces a final answer.

# Chatbot 2 — LangGraph RAG PDF Chatbot
**Files**

* Backend: langraph_rag_backend

* Frontend: streamlit_rag_frontend

## Description

This chatbot implements Retrieval Augmented Generation (RAG) allowing users to:

* Upload PDFs

* Index documents automatically

* Ask questions about the document

Each chat thread has its own vector store.

## RAG Pipeline
<img width="251" height="457" alt="image" src="https://github.com/user-attachments/assets/6848f54b-d7e9-4e32-ac9f-ece5713f6794" />

## Thread-Aware Memory

Both chatbots support persistent conversation threads.

Each thread has:

* conversation history

* memory checkpoints

* document retriever (for RAG)

Memory is stored using:

 * SQLite checkpointer

This enables:

* multi-conversation support

* chat history persistence

* switching between conversations
## Streaming Responses

Responses stream token-by-token using:

chatbot.astream()

This provides a real-time chat experience similar to ChatGPT.
## User Interface

The chat UI is built with Streamlit.

Features include:

* real-time streaming responses

* conversation threads

* tool execution status

* PDF upload

* document indexing

  ## Tech Stack
| Component       | Technology         |
| --------------- | ------------------ |
| LLM             | OpenAI GPT-4o-mini |
| Agent Framework | LangGraph          |
| LLM Framework   | LangChain          |
| Embeddings      | OpenAI             |
| Vector DB       | FAISS              |
| Web UI          | Streamlit          |
| Storage         | SQLite             |
| Search          | DuckDuckGo         |
| APIs            | AlphaVantage       |
| Protocol        | MCP                |

