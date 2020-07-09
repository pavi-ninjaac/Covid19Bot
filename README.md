# Chat Bot using the IBM Watson assistant and Watson Discovery:
There are several simple chat bot can answer simple and general questions, but here I 
build a chat bot that will answer the question based on the discovered results from the given document,
This is made with the help of AI. For this we are going to use the IBM Watson assistant and discovery services. Here I build a Covid19 Bot that will
answer our question about covid19 pandemic and treatment and medicine.<br/>

-	Get the required services from the IBM
-	Upload and configure data in Watson Discovery
-	Make query using the Cloud function
-	Make the chat bot skill
-	Create integration between Watson Discovery and Watson assistant using cloud function
-	Test our chat bot  

# Get the required services from the IBM:<br/>

- 1)	Go to your IBM cloud account and Go to catalog.
- 2)	Search for Watson assistant and click on it.

![Screenshot (149)](https://user-images.githubusercontent.com/51699297/86823037-f9224480-c0a9-11ea-9b9a-304a903f39cb.png)
- 3)	Leave all details as it is and click create .

![Screenshot (151)](https://user-images.githubusercontent.com/51699297/86823066-02131600-c0aa-11ea-9255-52aac896acbf.png)

- 4)	Your Watson assistant is now created.
- 5)	Do the same for Watson Discovery service and create it.

![Screenshot (150)](https://user-images.githubusercontent.com/51699297/86823043-fb849e80-c0a9-11ea-9739-146b57a8a6fe.png)

# Upload and configure data in Watson Discovery:

- 1)	Go to your IBM Watson discovery service and click on “Launch Watson discovery”.<br/>

![Screenshot (142)](https://user-images.githubusercontent.com/51699297/86822949-e0199380-c0a9-11ea-926b-5db43154ce5f.png)

- 2)	You have to create a new collection here click on “upload your own data” name your collection and then click create.<br/> 

![Screenshot (143)](https://user-images.githubusercontent.com/51699297/86822959-e445b100-c0a9-11ea-91f1-b9d75c219a6f.png)

- 3)	Click on “select documents “ and upload the pdf document. Watson support several document type like excel, pdf, png, jpg, html.<br/>
  But they wont allow the CSV files you have to change your CSV to PDF if you want to upload the CSV file.<br/>
  That conversion I mentioned in the other repository that link is.<br./>
  >  _________________link here_______________ <br/>
  
 ![Screenshot (145)](https://user-images.githubusercontent.com/51699297/86822981-eb6cbf00-c0a9-11ea-90f3-824d623b1e70.png)
 
- 4)	After you uploaded the page look like below, this will give you some sentiment analysis of your document.,br/>
- 5)	You can configure your document, for that just click on the configure data on the top right.

![Screenshot (146)](https://user-images.githubusercontent.com/51699297/86822987-ed368280-c0a9-11ea-9802-3ab378d625ff.png)

- 6)	In “Identify fileds” you can  identify and limit the fields that are all should be present in that page.<br/>
    So  by defining this that Watson will search result on the mentioned places and leave the unwanted things in that ,br/>
      documents and speed up the search task.<br/>      
      In “Manage field” you can restrict the fields that are not allow in your documents.<br/>
![Screenshot (147)](https://user-images.githubusercontent.com/51699297/86823003-f1fb3680-c0a9-11ea-8684-2db077c8ce2b.png)
- 7) Make copy of the collection id, environment id and the configuration id and the API key, URL in the Watson home page for the future use.<br/>

![Screenshot (148)](https://user-images.githubusercontent.com/51699297/86824395-b8c3c600-c0ab-11ea-988e-1fb5f68d6bab.png)

![Screenshot (142)](https://user-images.githubusercontent.com/51699297/86822949-e0199380-c0a9-11ea-926b-5db43154ce5f.png)


# Make query using the Cloud function:
	 We want to search into the document by the keyword, that is asked by the user to the chatbot. So to make connection between the Watson assistant and the Watson discovery we use the cloud function. Open your cloud function on the IBM dashboard,<br/>
It is located on the left side navigator.
-	1) click on start creation. 

![Screenshot (155)](https://user-images.githubusercontent.com/51699297/87071318-affffb00-c237-11ea-8243-95739429dbb6.png)

-	2) click on “action” and name your action and leave other things as it is and click create.

![Screenshot (156)](https://user-images.githubusercontent.com/51699297/87071326-b2625500-c237-11ea-9cc0-2c5923ca0482.png)

-	3) there under code section copy the "cloud_function_node.js" file from the repository and paste it here.
![Screenshot (157)](https://user-images.githubusercontent.com/51699297/87071330-b3938200-c237-11ea-8119-adeaf433f05a.png)

-	4) Under the parameter section you have to specify the parameter you are going to use. 158 modify
-	5) just click invoke to see the results.
-	6) go to endpoint and check the “Enable as web action” and then copy the URL for the future use , through this we are going to connect the cloud function with assistant. 

![Screenshot (159)](https://user-images.githubusercontent.com/51699297/87071354-bc845380-c237-11ea-85fd-cd482af8a7e9.png)

# Make your assistant :
	Just open your Watson assistant, and click on “launch Watson assistant”.<br/>
-	1) click on create assistant, and name your assistant and click create.

![Screenshot (160)](https://user-images.githubusercontent.com/51699297/87071385-c6a65200-c237-11ea-84ff-a2859d3c09fc.png)

-	2) Under skill click “add dialog skill”. 

![Screenshot (161)](https://user-images.githubusercontent.com/51699297/87071430-d756c800-c237-11ea-9698-b2f70fc545a8.png)

-	3) under import skill import the "skill_watson_code/skill-covid.json" file. And click import.

![Screenshot (162)](https://user-images.githubusercontent.com/51699297/87071488-ec335b80-c237-11ea-8993-2dd413246b5b.png)

-	4) Dialog section you can check the instants, entities and dialog . and “try it “ to make conversation with that.

![Screenshot (164)](https://user-images.githubusercontent.com/51699297/87071516-f7868700-c237-11ea-9c3f-ddaa7d7f9e91.png)

-	5) Under “options  webhooks paste your url that you copied from the cloud function. 

![Screenshot (165)](https://user-images.githubusercontent.com/51699297/87071549-00775880-c238-11ea-9d7d-b62b2988a72c.png)

# Make UI flow using the node -red:
-	1) Open your node-red and click import and import the "covidbot_flow/chatbotv1.json" file.
-	2) go to your assistant and under skill select your skill and click on the 3 dots and click view API details. There copy the skill id and paste under the assistant node and click “deploy”. 


![Screenshot (166)](https://user-images.githubusercontent.com/51699297/87071561-066d3980-c238-11ea-98e7-5e97338d402c.png)
