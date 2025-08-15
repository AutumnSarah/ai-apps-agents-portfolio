# How I Built a Retrieval Augmented Generation Agent on MindStudio:

1. **Create a datasource and upload some documents:** 

![][image1]  
I created an imaginary tech company with 5 flagship products.   
I generated documents detailing the critical information about the company and each document.   
Upload the documents under datasource and label the datasource with a title and description. 

2. **Start with a User Input block to collect the user query:**

**![][image2]**  
Configure the User Input form with guidance for the user:  
**![][image3]**  
Use the Label, Help, and Placeholder text to inform the user how to use the agent.   
This is the first thing the user will see. 

**4\. Use the Query Data Source Block:**  
**![][image4]**  
Use {{user\_query}} variable from the user input block is used to query the datasource.   
The agent will search the data source for chunks of text that can be used to answer the query.   
The result is saved to a variable named {{context\_chunks}}. 

**5\. Format a response for the user:**  
**![][image5]**  
The generate text block is prompted using the query result variable, the user input variable, and   
some additional instruction to generate a response which is displayed to the user. 

**6\. End with the Chat Block:**  
**![][image6]**  
A chat block with RAG strategy enabled in the message processing takes in the history of the run,   
displays the response to the user, and allows the user to ask follow up questions. 

