MODULE 1: 

Video 1: Motivation

I learned that a solitary language model is fairly limited and it doesnt have access to tools, external context and mulitistep workflows. So many LLMs use control- flow that consists of pre/ post LLM calls. This control call forms a "chain". I also leaned that the control flow of an agent is defined by an LLM. A Router agent uses an LLM to decide which predefined step to take — it has less control Whereas a Fully Autonomous agent plans and executes all steps on its own — it has more control. I also understood the advantage of using Langraph is to bend the reliability curve ie to maintain reliability even after pushing the level of control given to an LLM.

Video 2: Simple graph

In this lesson I learned how to build a simple graph and got introduced to the core compoents of a langgraph. The edge between the start and node 1 is called normal edge. When we choe different nodes based on some condition then these edges are known as conditional edges. State is the object that we bass in between the nodes and edges or our graph.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/simple-graph.ipynb

Changes I made:

I made a simple graph in langchain which detects if the user is happy or not and cheers him if he's sad and appreciate him if he's happy.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/simple_graph_example.ipynb

Video 3: Langsmith Studio

I learned about LangGraph Studio which is an interactive IDE for building, visualizing, and debugging AI agent workflows made with LangGraph. It integrates with LangSmith to trace, test, and optimize prompts or graph runs in real time. I also learned that each module has a studio directory which helps us to run the langraph studio to run a graph for each module.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/langgraph-studio.ipynb

Changes I made:

Since there was no notebook related to this video. I sucessfully followed the tutorial ran the langgraph studio on my laptop and tested out a few graph states adn its working. I also attached the screenshots for the same in the above link.

Video 4: Chain

In this video I learned about chains and how to builc them. A simple chain combines 4 key concepts: using chat messages in our graph, using chat models, binding tools to our llm executing tool calls in our graph. I also learned how to pass a chat list containing AIMessage and HumanMessage to our llm model. I also learned how to connect a tool to our llm model. Then I learned how to use messages as graph state and about the "add_message" reducer.

Link:

Changes I made: 

I made my own examples by following the notebook and tested all the new concepts on them. I created a simple chain and few extra tools like a web search tool, subtracat tool, multiply tool etc and tested them.

Link:




