# RAG-with-Ollama-Langchain
--------------------------------------------------------------

The following Repository contains a step by step guide on how to create a RAG (retrieval augmented generation) using Ollama and Langchain

----------------------------------------------------------------
## Pre-requisites

1- Install the required dependencies

2- Run the following command to open a bash terminal
```
%load_ext colabxterm
%xterm
```

3- After that Paste the following commands on the terminal 
``` python
curl -fsSL https://ollama.com/install.sh | sh
```
```python
ollama serve & ollama pull (model_name)
```

4- You might need to repeat the 3rd point after doing ctrl C as it checks the availability of GPU

------------------------------------------------------------------
## Specify the model

Specify the model you downloaded from from the terminal for me it was phi but you can check "https://ollama.com/library" for the models

```python
llm = Ollama(model="phi")
```
---------------------------------------------------------------
## Web Scraping

1- If you want to scrape the content from multiple web pages you do it like

```python
loader = WebBaseLoader(
    web_paths=[
        "https://www.gq.com/story/the-best-sweatpants",
        "https://www.gq.com/story/the-best-chinos-for-men",
        "https://www.gq.com/gallery/linen-pants-for-men",
        "https://www.gq.com/gallery/dress-pants-are-cool-now",
        "https://www.gq.com/story/the-best-linen-suits-for-men",
        "https://www.gq.com/story/the-best-summer-wedding-suits-for-men",
        "https://www.gq.com/story/best-affordable-suits",
        "https://www.gq.com/story/4-essential-suit-types-gq-recommends-show"
    ]
)
```
2- If there is only one web page do it like

```python
loader = WebBaseLoader( "https://blog.langchain.dev/langchain-v0-1-0/")
```
-------------------------------------------------------------------
## Embeddings

Note: "You can only use the model you downloaded from Ollama for embeddings. By default it uses llama"
