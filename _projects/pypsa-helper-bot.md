---
layout: page
title: PyPSA Helper Bot
description: A Discord bot that answers PyPSA questions from docs, code and past issues
importance: 4
category: engineering
github: https://github.com/GbotemiB/pypsa-helper-bot
---

Knowledge about the PyPSA ecosystem is spread across documentation, source code, configuration files and thousands of GitHub issues. That makes it hard for newcomers to get started and creates repeat questions for maintainers.

This Discord bot answers questions from the PyPSA community using retrieval-augmented generation:

- **Ingestion**: clones the `pypsa`, `pypsa-eur` and `pypsa-earth` repositories, and loads their documentation, Python source, YAML configuration, and historical issues and pull requests. It splits them into chunks, embeds them with the Gemini API, and stores them in a FAISS index.
- **Answering**: when mentioned in a channel, the bot retrieves the most relevant chunks and asks Gemini to answer using only that context.
- **Source citing**: answers include references to the source documents, so users can verify them.

Built with Python, discord.py, LangChain, Gemini and FAISS.
