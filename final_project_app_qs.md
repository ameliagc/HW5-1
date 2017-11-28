# SI 364 - Final Project questions

## Overall

* **What's a one-two sentence description of what your app will do?**
My app will allow users to search and read articles from the New York Times archive and save their favorites. 

## The Data

* **What data will your app use? From where will you get it? (e.g. scraping a site? what site? -- careful not to run it too much. An API? Which API?)**
The NYT archives and articles APIs.

* **What data will a user need to enter into a form?**
The user needs to provide the month and year that they wish to view articles from.

* **How many fields will your form have? What's an example of some data user might enter into it?**
The form will only need 2 fields, since the archive API only takes the month and year.

* **After a user enters data into the form, what happens? Does that data help a user search for more data? Does that data get saved in a database? Does that determine what already-saved data the user should see?**
The data is used to return a list of titles. From there, the user will select the article they want to view. This will be stored in a temporary variable used to call the articles API that will display the text. 

* **What models will you have in your application?**
I will need a model for article title and date and one for article title and text that the user saves. I will also need a model for the user login credentials.

* **What fields will each model have?**
All will have two fields each for strings of the title and either date or text, and the username/password.

* **What uniqueness constraints will there be on each table? (e.g. can't add a song with the same title as an existing song)**
The table with the article title and text can only have 1 entry per article, meaning that the user can only save an article one time. The user table can only have 1 password per username.

* **What relationships will exist between the tables? What's a 1:many relationship between? What about a many:many relationship?**
The one to many relationship will be the all of the articles in a given month and year. There is a many-to-many relationship between keywords and articles, since articles have many keywords and one keyword can be used on multiple articles. 

* **How many get_or_create functions will you need? In what order will you invoke them? Which one will need to invoke at least one of the others?**
One get_or_create function will be for adding new users to the table, or checking a user's login credentials. The other get_or_create function to add the article titles and text that the user wants to save. 

## The Pages

* **How many pages (routes) will your application have?**
5 routes - there is a login page,  a page for the form, a page to show the search results, a page to display the article title and text, and a page to view the saved articles. 

* **How many different views will a user be able to see, NOT counting errors?**
4 views

* **Basically, what will a user see on each page / at each route? Will it change depending on something else -- e.g. they see a form if they haven't submitted anything, but they see a list of things if they have?**
The home page will be the login page. After a user logs in they will be able to see the search form. After they submit the form, they will see the search result page that shows a list of article titles and authors that are links. When they click on the link for an article, they will see a page of the article title and text. There will be a link on every page to navigate to the page that shows a list of articles the user has already saved.

## Extras

* **Why might your application send email?**
This application could send an email each time the user saves a new article.

* **If you plan to have user accounts, what information will be specific to a user account? What can you only see if you're logged in? What will you see if you're not logged in -- anything?**
The list of saved emails will be specific to the user account and you can only see this if you are logged in.

* **What are your biggest concerns about the process of building this application?**
My biggest concern is setting up the login code for different users and making sure that data can be stored so they can come back to the site. 
