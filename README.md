MODULE 1: 

Video 1: Motivation

I learned that a solitary language model is fairly limited and it doesnt have access to tools, external context and mulitistep workflows. So many LLMs use control- flow that consists of pre/ post LLM calls. This control call forms a "chain". I also leaned that the control flow of an agent is defined by an LLM. A Router agent uses an LLM to decide which predefined step to take — it has less control Whereas a Fully Autonomous agent plans and executes all steps on its own — it has more control. I also understood the advantage of using Langraph is to bend the reliability curve ie to maintain reliability even after pushing the level of control given to an LLM.

Video 2: Simple graph

In this lesson I learned how to build a simple graph and got introduced to the core components of a langgraph. The edge between the start and node 1 is called normal edge. When we choose different nodes based on some condition then these edges are known as conditional edges. State is the object that we pass in between the nodes and edges or our graph.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/simple-graph.ipynb

Changes I made:

I made a simple graph in langchain which detects if the user is happy or not and cheers the user if he's sad and appreciates the user if he's happy. This was a basic example but helped me understand the basic workflow of graphs in langgraph.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/simple_graph_example.ipynb

Video 3: Langsmith Studio

I learned about LangGraph Studio which is an interactive IDE for building, visualizing, and debugging AI agent workflows made with LangGraph. It integrates with LangSmith to trace, test, and optimize prompts or graph runs in real time. I also learned that each module has a studio directory which helps us to run the langraph studio to run a graph for each notebook that we create or work on.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/langgraph-studio.ipynb

Changes I made:

Since there was no notebook related to this video. I sucessfully followed the tutorial ran the langgraph studio on my laptop and tested out a few graph states and analysed its working. I also attached the screenshots for the same in the above attached notebook.

Video 4: Chain

In this video I learned about chains and how to build them. A simple chain combines 4 key concepts: using chat messages in our graph, using chat models, binding tools to our llm executing tool calls in our graph. I also learned how to pass a chat list containing AIMessage and HumanMessage to our llm model. Moreover, I also learned how to bind a tool to our llm and use it in our workflow. Then I learned how to use messages as graph state and about the reducers which helps us to specify how state updates our performed. If no reducer function is specified, then it is assumed that updates to the key should override it as we saw before. But to append messages we can use the pre-built add_messages reducer. This ensures that any messages are appended to the existing list of messages instead of getting overwritten.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/chain.ipynb

Changes I made: 

I made my own examples by following the notebook and tested all the new concepts that I learned like reducers, chains, tools on them. I created a simple chain and few extra tools like a web search tool, subtracat tool, multiply tool etc and binded them with my llm created a simple workflow and tested it out on a few prompts. I also explored reducers separately on a list of messages by appending another message to that list using the built in "add_message" reducer fundtion.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/chain-example.ipynb

Video 5: Router

In the previous video we learned that a graph can either retun a tool call or return a NLP response and we also saw that an llm was directing the workflow of our our application. In this video we added a node that actually calls the tool whenever the model returns a tool call and an conditional edge that will direct the workflow on seeing whether the llms response consits of a tool or or just end the workflow. Then we saw the same workflow in langgraph studio and saw it visually by entering some prompts.

Link:

Changes I made:

I added a node that actually calls the tool whenever the model returns a tool call and an conditional edge that will direct the workflow on seeing whether the llms response consits of a tool or or just end the workflow to my previous example which would only show the tool call and then I tested this workflow by some other prompts and I also analysed the same workflow in langgraph studio as well and attached the screenshots for the same in the notebook attached below.

Link: 




