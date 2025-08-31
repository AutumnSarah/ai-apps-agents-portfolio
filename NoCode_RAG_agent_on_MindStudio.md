# How I Built a Retrieval Augmented Generation Agent on MindStudio:

1. **Create a datasource and upload some documents:** 

<img width="629" height="362" alt="Image" src="https://github.com/user-attachments/assets/d4a12d5f-e17e-4408-9092-16024ba79eb3" />   

I created an imaginary tech company with 5 flagship products.   
I generated documents detailing the critical information about the company and each of its products.   
Upload the documents under datasource and label the datasource with a title and description. 

2. **Start with a User Input block to collect the user query:**

<img width="857" height="448" alt="Image" src="https://github.com/user-attachments/assets/f83d27db-1753-45fb-9c0d-fc34764f92d7" />  

Configure the User Input form with guidance for the user:  
<img width="631" height="379" alt="Image" src="https://github.com/user-attachments/assets/4897e98f-a847-49e3-9971-a054c36bd6ef" />   

Use the Label, Help, and Placeholder text to inform the user how to use the agent.   
This is the first thing the user will see. 

**3\. Use a logic step to check the relevance of the user query to the Agent’s purpose.**   
<img width="859" height="413" alt="Image" src="https://github.com/user-attachments/assets/78f6890d-2f71-4d64-9363-f596ced7d6c8" />  

**4\. Query Data Source:**  
<img width="820" height="492" alt="Image" src="https://github.com/user-attachments/assets/4bdcd258-2ac4-4bef-a52c-f6e8641e5ce9" />  

Make a model call to transform the user query into a vector database query.  
Use the {{enhanced\_query}} to query the datasource.   
The agent will search the data source for chunks of text that can be used to answer the query.   
The result is saved to a variable named {{context\_chunks}}. 

**5\. Format a response for the user:**  
<img width="882" height="441" alt="Image" src="https://github.com/user-attachments/assets/e39df766-5194-48dd-969c-0704812a0608" />  

A model prompted using the query result variable, the user input variable, and   
some additional instruction to generate a response which is displayed to the user. 

**6\. End with the Chat Block:**  
A chat block with RAG strategy enabled in the message processing takes in the history of the run,   
displays the response to the user, and allows the user to ask follow up questions. 

