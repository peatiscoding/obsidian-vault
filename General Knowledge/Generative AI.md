#llm #knowledge-sharing 

Author: Kittiphat S
Last Update: 12 Dec 2023
## General Knowledge

General Knowledge based for Generative AI

1. LLM is like a RDS. It is more like a service that accept "INPUT" and throws out "OUTPUT"
2. Currently LLM are still predictor of words. All attempts toward AGI is still revolve around the same idea; given a logical ramp so that the next words would sounds and aligned with the previous one. This is why most of the time short answers tends to be hallucination. Hence when LLM answers 2+2 = 4 that refers to 4 as it is it next "prediction of such 2+2 tokens". Not that it really understands 2 + 2 is actual addition.
3. However to combat this problem. We tends to Ask LLM for source code generation instead. That's why ChatGPT release its new product that allow the ChatGPT to has the capability to run the Code Interpreter. Which means run the Generated source code and answer again with the prompt.
4. LLM's temperature - typically refers to value from 0~1. while 0 allows no variation. And 1 allow LLM to get more creative. However it will be much less consistent.
5. LLM has multiple variants. And within each LLM it has multiple components.
	1. LLM - Large Language Model
	3. Embeddings - The interpretation of each Token as an array of numbers.
	4. Prompt - the input of LLM can be comprise of; System Prompt, User Prompt, and History.
	5. Vector Store - The storage that holds the Embeddings. This is considered as Long Term Memory.
	6. RAG - Retrieval Augmented Generation - The technique that expands the LLM's memory span. By keeping the domain knowledge a side. And request it when needed.
	7. Fine-Tuning - the LLM itself is a static model that does not evolved overtime. Hence it was trained as a foundation; which is has very broad knowledge of everything (based on 7B/13B inputs). Fine-Tuning is running the LLM with given narrower dataset and tuning the activation neural to the required target application. Sometime we can even carved out the in-active neural from the equation making the Model a lot smaller.
	8. Tool/Function - Since LLM is a text interpreter. It can also emit the code, or the structured text. Hence it is also practically possible for it to make a function call! -- To do this we will need "Prompt" to help facilitate/provide the information to the LLM so that it knows what are the function call that it can call to. This would be a descriptive (Function's document). The LLM output will then need to interpret the result and resolve/recognized that it would like to call the Function. And invoke the function. Feedback the result again to the LLM to make it produce the final result. Notice that there are multiple calls to LLM at this point. This is where the Agent comes in. Example of Tool:
		1. Search Tool -- allow LLM access to realtime website data,
		2. Computation tool -- such as code interpreter, wolframalpha
		3. RAG,
		4. SQL interpreter - access to custom domain of data. We can have LLM generate SQL and use it to query the actual data. Hence the SQL can be a lot more humanized language. There is even an LLM for SQL!
		5. Custom tool. Create your own.
	9. Agent - In general, refers to the system that use LLM as a central, and perform specific action per the LLM output. May be keep calling the LLM for improved results. Within the Agent itself there are also another set of components
		1. memory - refers to how to collect the history.
		2. react - refers to "ReAct" which means Reasoning + Action. This allows agent to perform multiple steps between it reach the final answers
		3. tools - Tools at the Agent's disposal
		4. rag - a kind of tools that give the Ground truth for the LLM to answer. Rag normally backed by Vector Store.
		5. Note that in the Agent it is also possible to use multiple-LLMs; Consider one chain to back a SQL use case, another chain to help routing the message, another chain to produce the output.
6. Modality - or Mode - this refers to how would we interpret the input. Multi-modality is that the system can intercept and make sense these type of inputs.
7. Challenge of LLM
	1. interpret the input; Input need to be prepared in such way that it can be easily understand by the LLM you will be using. 
	2. Thai Language - The Thai Content need Thai's LLM to interpret. There is one available OpenThaiGPT (https://openthaigpt.aieat.or.th/released-models-version-less-than-1.0.0-beta-greater-than-16-08-23)

## Existing Tool Set

1. LangChain connecting LLM and its tool together. Available in both Python; TS/JS
2. Hugging Face - like a docker hub. provide a Hub for LLMs; Can run models in local machine as well via Transformer pipeline (Python). Or call it via **Inference API**
4. OpenAI - main stream, expensive LLM provider
5. Ollama - A tool like docker where you can download and run (limited LLM) on your local machine.
6. Vector Stores
	1. Pinecone
	2. ChromaDB
	3. ElasticSearch - Create explicit index with Vector index instead.
## Refs

- Tool: https://www.pinecone.io/learn/series/langchain/langchain-tools/