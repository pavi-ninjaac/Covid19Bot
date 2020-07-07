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


