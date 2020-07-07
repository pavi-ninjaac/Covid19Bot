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
- 2)	Search for Watson assistant and click on it. 149
- 3)	Leave all details as it is and click create . 151
- 4)	Your Watson assistant is now created.
- 5)	Do the same for Watson Discovery service and create it. 150
# Upload and configure data in Watson Discovery:

- 1)	Go to your IBM Watson discovery service and click on “Launch Watson discovery”.<br/> 142
- 2)	You have to create a new collection here click on “upload your own data” name your collection and then click create.<br/> 143
- 3)	Click on “select documents “ and upload the pdf document. Watson support several document type like excel, pdf, png, jpg, html.<br/>
  But they wont allow the CSV files you have to change your CSV to PDF if you want to upload the CSV file.<br/>
  That conversion I mentioned in the other repository that link is.<br./>
  >  _________________link here_______________ <br/>145
- 4)	After you uploaded the page look like below, this will give you some sentiment analysis of your document.,br/>
- 5)	You can configure your document, for that just click on the configure data on the top right. 146
- 6)	In “Identify fileds” you can  identify and limit the fields that are all should be present in that page.<br/>
-     So  by defining this that Watson will search result on the mentioned places and leave the unwanted things in that ,br/>
      documents and speed up the search task.147<br/>
      In “Manage field” you can restrict the fields that are not allow in your documents.<br/>
- 7)	 Make copy of the collection id, environment id and the configuration id and the API key, URL in the Watson home page for the future use.,br/>148 142 modifyed

