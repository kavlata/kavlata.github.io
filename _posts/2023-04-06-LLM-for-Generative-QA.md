### LLM for Generative QA on Long Documents

Recently I was working on a problem statement that needed to explore LLM for Question Answering context. 
The problem was to use opensource LLM model (not Open AI gpt) and host in a local system for QA on custom data. 
I found very interesting set of articles and code repo that helped through this process. 
This is a fast moving topic and hence the code I wrote or the articles might get outdated in a weeks time. [My LLM Code repo](https://github.com/kavlata/LLM-experiments)
1. [This is an amazing article by Abonia Sojasingarayar](https://medium.com/@abonia/document-based-llm-powered-chatbot-bb316009de93) 
    1. Author gives basic architecture for a QA system to process Long and verbose documents eg: Contracts, Legal agreements, clinical research papers etc.
    1. Link to author's codebase gives starter help on Langchain, Chroma. Though the code is a little outdated considering the speed in which Langchain community is updating the repo so fast to keep up with latest trends.[Code](https://github.com/Abonia1/Context-Based-LLMChatbot)
1. This article by Mick gives a good view on constraints of using LLM models directly for a Long document QA system [Link](https://medium.com/@imicknl/how-to-create-a-private-chatgpt-with-your-own-data-15754e6378a1)
1. Matt Boegner talks about a generic knowledge retrieval architecture [Link](https://mattboegner.com/knowledge-retrieval-architecture-for-llms/)
1. Amazing blog by Langchain contributors. Talks about how they updated their framework for better retrieval by providing more classes and connectors. [Link](https://blog.langchain.dev/retrieval/) 
1. Couple of Youtube Creators who I follow to get amazing code samples and explanations on Langchain and LLM in general are
    1. 1littlecoder [playlist](https://www.youtube.com/playlist?list=PLpdmBGJ6ELULEfPWvvks0HtwzCvQo1zu0)
    1. Sam Witteveen [playlist](https://www.youtube.com/watch?v=J_0qvRt4LNk&list=PL8motc6AQftk1Bs42EW45kwYbyJ4jOdiZ)
1. Interesting projects to track. There are more projects in each space. The above articles can give a varied list. The ones which I have used are listed down.
    1. LLM framework - Langchain 
    1. Vector Stores - Chromadb, FAISS, Elastic Search, Milvus, Weaviate, Pinecone, Quadrant. Lot of traction I see is for Pinecone now. I saw a stack called OPL (Open AI, Pinecone and Langchain) 
    1. Connect data to LLMs - LLamaIndex  
    1. Models to try from HuggingFace - Google Flan T5 - XXL, Facebook Blenderbot 1B distill, Facebook Opt 66B, BigScience Bloom 560m
    1. To demo a quick version - Gradio, Streamlit 
