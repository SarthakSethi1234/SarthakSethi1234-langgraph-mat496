MODULE 1: Introduction

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

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/router.ipynb

Changes I made:

I added a node that actually calls the tool whenever the model returns a tool call and an conditional edge that will direct the workflow on seeing whether the llms response consits of a tool or or just end the workflow to my previous example which would only show the tool call and then I tested this workflow by some other prompts and I also analysed the same workflow in langgraph studio as well and attached the screenshots for the same in the notebook attached below.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/router-example.ipynb

Video 6: Agent

In the last tutorial we went to call on the tools whenever the model decided to do a tool call. Here in this video we explored a very popular architecture known as ReAct where we simply passed the "ToolMessage" back to the model where then the model decides that if it needs to call another tool or respond to the prompt directly. We then built this simple generic architecture. After creating this in the graph visualisation I observed that now after calling the tool theres an edge that feeds back the response to the assistant node. After that we ran a few examples and observed their tracing in langsmith. This helped me learn how to use both langsmith and langgraph to my advantage and also trace our llm calls and also keep a track of meta data such as tokens usage and latency.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/agent.ipynb

Changes I made:

I revamped my previous example by doing exactly the same as in the tutorial, that is, connecting my tool node with the llm calling node. Then I ran a few example prompts to test out if my ReAct agent could generate a proper response using all the tool calls it did after processing a single prompt. I alo noticed that my agent can now evaluate expressions ny repeatead tool calls. I also analysed the workflow of a few examples in langgraph studio and I attached the screenshots related to the same in the notebook below.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/agent-example.ipynb

Video 7: Agent with Memory

In this video we explored the idea of memory and why the functionality of the agent increases during multi-turn conversations with interruptions when it has a memory. Then we got introduced to persistence. LangGraph can use a checkpointer to automatically save the graph state after each step. This built-in persistence layer gives us memory, allowing LangGraph to pick up from the last state update. One of the easiest checkpointers to use is the MemorySaver, an in-memory key-value store for graph state that enables LangGraph to retain context and continue seamlessly across turns. Then we interacted with the same agent in langgraph studio. I also learned that in langgraph studeio we dont need to add persistence layer on our own because it used langcgain api key which has its own persistence layer, which happends to be postgress

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/agent-memory.ipynb

Changes I made:

I modified my own agent to have a memory by using the concept of persistence. I used a checkpointer which automatically saves the graph state after each step in a thread. After doing this I tested my agent out by having a multi-turn conversations with interruptions and analysing its output which was consistent keeping in mind the multi-turn coversations with interruptions. I also interacted with my agent in lanngraph studio and I attached the screenshorts for the same in the notebook below.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%201/agent-memory-example.ipynb

MODULE 2: Resources

Video 1: State Schema

In this video I learned about Schmea which is just the structure and types of the data the graph will use and we have been using type dict for this purpose till now. In this we learned about dataclass which is very similar to typedict but has a very minor difference in the way we access the values which in this case is by the "." operator. On eof the problems with bothdata classes and type dicts that we've been using is that the type hints aren't being enforced at the runtime that means we can asign an invalid value without raising an error and to overcome this pydantic is very sucessful as it provided data validation

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/state-schema.ipynb

Changes I made:

I made my own graph that decides whather the user wants to confirm an order or cancel it using PYDANTIC and I observed its working with valid and invalid inputs.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/state-schema-example.ipynb

Video 2: State Reducers

In this video we dived into reducers, which specify how state updates are performed on specific keys or channels in our schema. I learned that when we want to update a state which is shared among two nodes simultaneously ut gives a value error and to overcome this shortcoming we use state reducers. We used Annotated for this purpose. In some cases we are required to define custom reducers rather than using the inbuit reducers in python for edge cases such as null. Next we also learned about the message state reducers and add_reducer method. We learned about adding messages, overwriting them using id and deleting them using the inbuilt RemoveMessage reducers.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/state-reducers.ipynb

Changed I made:

I tested out the inbuit message reducers provided by langgraph with a few examples. I also made a custom reducer and a graph which adds 1, 5 and 7 in each node and ran a few testacases on wit which checks if our cutsom reducers are working or not.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/state-reducers-example.ipynb

Video 3: Multiple Schemas

In this videoo I learne that most of the graphs use single schema which contains their input and output keys but there are some cases where we want more control over this. There might be cases where the internal nodes of the graphs may return an information that is not at all related to the output of the graph but might be the internal communication between the graphs which we dont want to be exposed to the user at the end of the graph operation. For this purpose, we can use private state. This is useful when we need anything that is a part of the intermediate working logic but not relevant to the overall graph output or input. I also learned that, StateGraph uses a single schema for all nodes to communicate. However, we can define explicit input and output schemas while keeping an internal schema that holds all relevant keys for graph operations.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/multiple-schemas.ipynb

Changes I made:

I made a graph which converts celcius to farenheit using private schemas for internal communication and I also built another graph which used input and output schema which handles the users travel destinantioons, information about that destinantiona and outputs a message to the user.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/multiple-schemas-example.ipynb

Video 4: Trim and Filter Messages

In this video we learned how to work with messages. A practical problem with messages is managing long running conversations because there may be very long messages in the list and passing this into the graph will be both latency and tokean intensive which in turn will be very costly. To overcome this we can either keep a track of a few recent messages and delete the rest of the messages using "RemoveMessages". We can also filter some messages and invoke the graph using a subset of the messages and passing it to the chat model. Another way is trimming where can can trim the message by spoecifying the number of tokens we want to pass to the llm. This makes our llm respond even faster.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/trim-filter-messages.ipynb

Changes I made:

I made a simple chatbot that automatically forgets the old messages to save memory and costs. Here I'm not removing the messages permanently but using trim_messages to pass the recent messages to the llm instead of the whole thread. In this way I'm preserving the history and also reducing the token cost per invocation of the llm.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/trim-filter-messages-example.ipynb

Video 5: ChatBot with summarizing Messages and Memory

In this video, I learned how to build a chatbot that summarizes past messages when the count exceeds six, helping reduce LLM context size. I explored how to add memory using a checkpointer that saves the graph state after each step. This allows the chatbot to remember conversations even after interruptions. I also understood how persistence makes chatbots more practical and efficient for long-term use.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/chatbot-summarization.ipynb

Changes I made:

I modified the theme to a tech support chatbot. The chatbot uses MemorySaver for persistent memory and keeps only the last 2 messages after summarizing, which helps reduce the context passed to the LLM. This approach saves costs and improves response time while maintaining conversation continuity through summaries. I also revised the concepts of threads in a conversation. I also observed the thread in langsmith portal and attached the screenshots fro the same in the notebook below

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/chatbot-summarization-example.ipynb


Video 6: ChatBot with summarizing Messages and External Memory

In this video, I learned that not only does langgraph provides in-memory checkpoints but also external memory checkpoints like postgres, sqlite etc. These in-memory checkpointers stores the memory till our notebook is in the existence. But these external memory checkpoints stores the convesation in an external database indefinitely. We also verified that if our thread was saved locally or not by interrupting our interpreter and restarting our notebook. I also learned that when we run the same chatbot in langgraph studio a persistence layer get automatically added for us. In case of langgraph studio this persistence layer is postgres. Then we explored the working of this chatbot in langgraph studio and i attached the screenshots for the same in the notebook below.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/chatbot-external-memory.ipynb

Changes I made:

I modified my tech support chatbot which I made by connecting its memory to a local external database using sqlite. I also verified whether this external memory checkpoints stores the conversation in external database indefinitely or not. I also explored the working of this chatbot in langgraph studio, saw the automaticlaly built persistence later in studio tested it by restarting the conversation and I attached the screenshots of the same in the notebook below.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%202/chatbot-external-memory-example.ipynb

MODULE 3: UX and Human-in-the-loop

Video 1: Streaming

In this video, I learned about streaming. There are two types of streming: streaming values and streaming updates. Streaming values streams the full state of the graph after eah node is called whereas streaming updates streams the update to the state of the graph after every node is called. I also learned that we can stream tokens as they’re generated using the .astream_events method, which emits events as they occur inside nodes. Each event is a dict with event, name, data, and metadata (which includes langgraph_node). Further, I also learned how to stream tokens using langgraph API. We also saw about the LangGraph API application and how we could use them from the IDE and also the availablity of a new streaming method messages that updated the final message token by token and gave us the Output.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%203/streaming-interruption.ipynb

Changes I made:

Since what we learned was just streaming of tokens and states. I used my previous example of a graph and tried streaming updates, values, tokens on it.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%203/streaming-interruption-example.ipynb

Video 2: Breakpoints

In this video, I learned the advantages of adding human-in-the-loop: If we want to approve certain step our agent is going to take such as tool usage, we may also use it for debugging and directly modifying or editing the state of our graph with human feedback. Next, I learned about breakpoints which provides a simple way to stop the graph at certain steps. I also learnda trick that if we do graph.stream(None, {thread_id}) it will start executing the graph from that stateSnapshot. This will help us continue from where we interrupted the flow of the graph. Next we learned about breakpoints with langgraph API. Here I can pass the interrupt before to my agent as an argument through the API whih is pretty good because we had to speciy it while we were compiling our graph. We also looked interrupt in the langmith studio as well.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%203/breakpoints.ipynb

Changes I made: 

I created a simple calculator agent with breakpoints that requires human approval before executing any mathematical operations. Instead of using multiply and divide like in the tutorial, I made my own tools such as add_numbers, subtract_numbers, and square_number to test out different arithmetic operations. I set up the graph with interrupt_before=["tools"] which pauses the workflow right before any tool gets executed.

Link: https://github.com/SarthakSethi1234/SarthakSethi1234-langgraph-mat496/blob/main/MODULE%203/breakpoints_example.ipynb

Video 3: Editing State and Human Feedback

In this video we learned about how to edit the graph state once we have interrupted its flow. We know breakpoints are used for human approval but they also give us an opportunity to modify the state of the graph. This is done by the default message reducer "add_message" once we have updated the state of the graph. Next, I also learned how to add interrupt in langgrapg studio and explored its working there. We also learned how to edit the state of a graph using langgrapgh API. I also learned how to explicitly modify the graph state using user input by using a dummy node that will basically accept the user input and inject it into our graph at a particular point. By using the dummy node we will add feedback as if we are running that node and we can do this by simply with "as_node" feild in the update state function call.

Link: 

Changes I made:

In the exisiting example, I added more tools like subtract, divide,and a few other tools that add emotions and interrupted and changed the state of the graph by hardcoding and user input both and continued the execution of graph from there. I also modified the graphs state using langgraph API which I learned to do in the tutorial. I attached the working of the graph in the studio as well in the notebook below.

Link: 

Video 4: Dynamic Breakpoints
Video 5: Time Travel

