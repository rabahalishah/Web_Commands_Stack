# About: Web_Commands_Stack
This repository includes bunch of frequently used commands of most popular technologies used in full stack web development. You can use it as cheat sheet.

# 01 DOM
Here are some commonly used DOM functions and properties:
```bash
getElementById(): // Retrieves an element from the DOM using its id attribute.
getElementsByClassName(): //Retrieves a collection of elements from the DOM based on their class name.
getElementsByTagName(): // Retrieves a collection of elements from the DOM based on their tag name.
querySelector(): // Retrieves the first element that matches a specified CSS selector.
querySelectorAll(): // Retrieves a collection of elements that match a specified CSS selector.
createElement(): // Creates a new element node.
createTextNode(): // Creates a new text node.
appendChild(): // Appends a node as the last child of a parent node.
removeChild(): // Removes a child node from its parent node.
parentNode: // Gets the parent node of an element.
childNodes: // Gets a collection of child nodes of an element.
classList: // Provides methods to add, remove, toggle, or check the presence of CSS classes on an element.
innerHTML: // Gets or sets the HTML content of an element.
innerText: // Gets or sets the text content of an element.
style: // Provides access to CSS styles of an element.
addEventListener(): // Attaches an event listener to an element.
removeEventListener(): // Removes an event listener from an element.
setAttribute(): //  Sets the value of an attribute on an element.
getAttribute(): // Retrieves the value of an attribute on an element.
document.body.FirstElementChild.style.background - "red"
classList: // Provides methods to manipulate the class names of an element.
```


These are just a few of the many functions and properties available in the DOM. The DOM provides a rich set of methods and 
properties for working with HTML elements and manipulating the structure and content of web pages.


**NOTE:**
The main difference between the selectElementByID or class and queryselector is that SelectElementById uses id name or class name whereas queryselector use CSS selectors (.class for class and #anyname for id) for selecting the element 

Handling events
```bash
element.onclick = function () { alert('yes') };

let handler = function (e) {}
```

here e is an event object which is always automatically created by the browser when an event happens and this contains all details of that event to see that print 
```bash
console.log(e).
//or
 console.log(e.type) etc. 
```
You can give any name you want to that event object e.g, function(cool) now cool is an event object.

```bash
element.addEventListner(event, handler); //here handler could be any function
element.removeEventListner(event, handler);
```


### Call back function
Passing a function as an argument to another function is called callback

```bash
function loadscript(src, callback) {
var script = document.createElement("Script");
script.src = src;

script.onload = function() {
console.log("Script loaded");
callback();
}

script.onerror = function() {
console.log("Script not loaded ERROR");
callback(new ERROR("SRC error" );
}
document.body.appendChild(script);
}


funciton hello() {
if (error) {
handle error
}
else {
do something else}
alert('hello')
}


loadscript("https://dashd.js", hello)
```


here hello will act as callback function

### Promise

```bash
let p = new promise((resolve, reject) => {}
```
# 02 Deploying React on GitHub

https://create-react-app.dev/docs/deployment/#github-pages-https-pagesgithubcom

# 03 Flask Deployment
- upload your files on github
- create account on pythonanywhere
- then clone the repository using HTTPS link in bash terminal of pythonanywhere
- then go to web app tab on the dashboard
- then create manual configuration
- select your python version
- scroll down and give your file path
- then go to https://help.pythonanywhere.com/pages/Flask
- and follow the documentation means that make venv and install  requirement.txt

# 04 MongoDB Queries
CRUD opertions > Create, read, update and delete these 4 are the most performed operations in working with DBMS

use database_name (this will create a database and will automatically switched to it)
```bash

db.text (this query is use to create text file)
db.text.insert({"name":"rabah"})   (this query is used to insert data in your db text file)
```
```bash
show dbs	//(used to show all databases)
```
```bash
show collections //(used to show collections/table we created)

```

# Creating and inserting only one documen/object in DB

```bash
use mykart 
//this will create a database of the given name
```
```bash
 db.items.insertOne({name: "Samsung", price : 200000,rating: 4.7, qty:220, sold: 200})  
```
// Inserting data, here items are are actually table but they called as collections

### Inserting multiple documents in DB

```bash
db.items.insertMany([{name: "Samsung", price : 200000,rating: 4.7, qty:220, sold: 200},{name: "Apple", price:300000, rating: 4.7, qty:500, sold: 450}, {name: "Realme", price:350000, rating: 4.2, qty:250, sold: 150}])  
```
In this function we can insert more than one object at time by passing objects in array.

### How to search objects inserted in DataBase
```bash
show dbs	//(used to show all databases)
```
```bash
>show collections (used to show collections/table we created)
> db.items.find({price : 200000})
```

### Query for items having rating greater than equal (gte) 4.0

```bash
db.items.find({rating :{$lte:4.0}})
```
items having rating less than equal 4.0 
```bash
db.items.find({rating :{$gte:4.0}})
```

### Query for items having rating greater than equal (gte) 4.0
```bash
db.items.find({rating :{$lt:4.0}})
```

### Query for items having rating less than (lt) 4.0
```bash
db.items.find({rating :{$gt:4.0}})
```

### AND operator
```bash
db.items.find({rating :{$gte:4.0},price:{$gt:4.2}})
```
```bash
db.items.find({rating :{$gte:4.0}},{rating:1})
// (this query will sort object and will show rating only as rating:1 means rating is true)
```
```bash
db.items.find({rating :{$gte:4.0}},{rating:1, qty:1})
// (this query will sort object and will show rating and quantity only, as rating:1 and qty:1 means rating and qty are true)
```

### OR operator
```bash
db.items.find({$or:[ {rating :{$lt:5.0}}, {rating: {$gt:4.0}} ]})
```
by adding $or now my comma has become OR operator


here comma is working as AND operator 


### Deleting items from Database
**NOTE:** The deleting and find syntax are almost similar

```bash
db.items.deleteMany({name :'Samsung'})
// This Query will delete multiple items of the given parameters
```
```bash
db.items.deleteOne({name :'Samsung'})
// This Query will delete only first item in case of multiple document match
```

### Query for Adding collections in my database
```bash
db.collections.insertOne({a:89})
```
```bash
db.items.updateOne({name:"Apple"},{$set:{name:"Samsung"}})
```
```bash
db.items.updateOne({name:"Apple"},{$set:{price:10000}})
```
This query is used to update the first matched item
```bash
db.items.updateMany({name:"Realme"},{$set:{name:"Samsung", rating:4.7}})
```
Query used to update the more than one items matched

# 05 NPM Setup Settings

NPM stands for Node package manager

first insatll Node from the webiste
then for verification
```bash
npm -v
```
```bash
node -v
```
now follow the below steps go to you project folder
```bash
npm init // (this will create packages.JSON file)
```

```bash
sudo npm install -g live-server // (this will install live server module globally which will create a fake server in browsers)
```
```bash
npm install lodash // (this will install lodash module locally)
```

```bash
sudo npm install -g browserify // (this will install browserify globally which will run modules commands in browsers)
```

```bash
browserify script.js > bundle.js

```
(this will create a bundler file namely bundle.js once the file is create link this bundle.js file to your html file bundle.js will load modules and other JS files in itself and then will return these files on running bundle.js)

after that whenever you will make any changes in your script.js file you have to run the above command and then live-server command

6. to save your time go to packages.JSON file and look for script tag
change the "test" name let say "build" now change its function to
```bash
"build" :"browserify script.js > bundle.js && live-server" 
```

now run
```bash
npm run build
```

# 06 SQL Queries
### SOME important points
1. DONT forget to put ; at the end of every statement.

2. Primary keys are always unique to each row.

3. NOT NULL means it cannot be empty

4. Fields are refer as columns

5. Records are refer as rows.

6. SQL requires single quotes around text values (most database systems will also allow double quotes). However, numeric fields should not be enclosed in quotes.

7. Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!

8. Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!

9. The percent sign (%) represents zero, one, or multiple characters. The underscore sign (_) represents one, single character.

10. The UNION operator is used to combine the result-set of two or more SELECT statements. Every SELECT statement within UNION must have the same number of columns. The columns must also have similar data types. The columns in every SELECT statement must also be in the same order.

11. If some customers or suppliers have the same city, each city will only be listed once, because UNION selects only distinct values. Use UNION ALL to also select duplicate values!

12. Single line comments start with --. Any text between -- and the end of the line will be ignored (will not be executed).

### Creating database FOR Windows User
```bash
createdb -U postgres name_of_database;
//(query used to create database)
```
```bash
psql -U postgres name_of_database;
// (verifying whether the database has created or not and this query is also used to switched to the created database)
```

```bash
\l
// (this query is used to check the list of all created databases)
```
```bash
\c 'name_of_database'
// (this command is used to connect/switch to the other databases)
```

```bash
CREATE TABLE table_name (column_1 datatype, column_2 datatype, column_3 datatype);
// (this query syntax is used to create table in SQL)
```
```bash
> \dt 
// (this query is used to display tables which you have created in you database)
```
```bash
 INSERT INTO table_name (column_1, column_2, column_3) VALUES ('Value_1', 'Value_2', 'Value_3');
 INSERT INTO users (name,age,birthday) VALUES ('john',12,2003-01-09);
// (this query is used to enter rows in the table)
```
```bash
SELECT * FROM table_name;
// (this query is used to diplay the data which you have entered into the table)
```

### Adding Column
```bash
ALTER TABLE table_name ADD column_name datatype;
// (this query is used to add column in your existing table)
```
```bash
UPDATE table_name SET column_name = some_value WHERE column_name = some_value
UPDATE table_name SET column_name = some_value WHERE column_name = some_value AND column_name = some_value
UPDATE table_name SET column_name = some_value WHERE column_name = some_value OR column_name2 = some_value
// (query to is used to update or make changes in your existing table)
```


### JOIN
```bash
SELECT * FROM table_1 JOIN table_2 ON table1.primary_key = table2.foreign_key;
```

### DELETE
```bash
DELETE FROM table_name WHERE name='sallu' OR name='James';
// (query to delete row)
```
```bash
DROP TABLE table_name;
// (query to delete whole table);
```

### Conditional Selection
```bash
SELECT * FROM table_name WHERE column_name LIKE 'any_value%'
// (here % means any value after that)
```
```bash
SELECT * FROM table_name ORDER BY column_name DESC;
// (this will select the data will display as sorted data in descending order)
```
```bash
SELECT * FROM table_name ORDER BY column_name ASC;
```
### FUNCTIONS
```bash
SELECT AVG(column_name) FROM table_name;
SELECT SUM(column_name) FROM table_name;
SELECT MIN(column_name) FROM table_name;
SELECT MAX(column_name) FROM table_name;
SELECT COUNT(column_name) FROM table_name;
```



### More Detail
```bash
SELECT Distinct Column_name FROM Table_name;
// (this query will return only unique value means without repitition)
```


The WHERE clause is used to filter records.
It is used to extract only those records that fulfill a specified condition.
```bash
SELECT column1, column2 FROM table_name WHERE condition;
SELECT * FROM Customers WHERE Country='Germany';
```


### AND
```bash
SELECT * FROM Customers WHERE Country='Germany' AND Country='Germany' AND City='Berlin';
```

### NOT
```bash
SELECT * FROM Customers WHERE NOT Country='Germany';
```

### OR

```bash
SELECT * FROM Customers WHERE Country='Germany' OR Country='Germany' OR City='Berlin';
```


### COMBINE AND OR and NOT
```bash
SELECT * FROM Customers WHERE Country='Germany' AND (City='Berlin' OR City='München');
```

### ORDER BY

```bash
SELECT * FROM Customers ORDER BY Country;
SELECT * FROM Customers ORDER BY Country DESC;
SELECT * FROM Customers ORDER BY Country ASC;
```

### ORDER BY more than one column
```bash
SELECT * FROM Customers ORDER BY Country ASC, CustomerName DESC;
```


### Adding Rows
```bash
INSERT INTO table_name (column1, column2, column3, ...) VALUES (value1, value2, value3, ...);
```


### SELECTING Empty Column
```bash
SELECT column_names FROM table_name WHERE column_name IS NULL;
```
```bash
SELECT column_names FROM table_name WHERE column_name IS NOT NULL;
```




### Updating data in the table
```bash
UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition;
```

### Deleting Data from the tables
```bash
DELETE FROM table_name WHERE condition;
```


### SELECTING TOP 
```bash
SELECT * FROM Customers LIMIT anynumber;
SELECT * FROM Customers LIMIT 3;
```


### COUNT
function to return the number of records that have the Price value set to 18.
```bash
SELECT COUNT(*) FROM Products WHERE Price = 18;
```


### Minimum and Maximum values
```bash
SELECT MIN(Price) AS SmallestPrice FROM Products;
```
(here AS is called Alias and it will be temporary name of the value which will be returned as minimum value)
```bash
SELECT MAX(Price) AS SmallestPrice FROM Products;
```


### Alias
```bash
SELECT CustomerID AS ID, CustomerName AS Customer FROM Customers;
```

### JOIN
Here are the different types of the JOINs in SQL:

1. (INNER) JOIN: Returns records that have matching values in both tables
2. LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
3. RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
4. FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table.


### SELECT INTO (for copy tables)
The SELECT INTO statement copies data from one table into a new table.
```bash
SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```

### IF ELSE in SQL
The CASE expression goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL
```bash
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;


CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;

```

### What is a Stored Procedure?
A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.

You can also pass parameters to a stored procedure, so that the stored procedure can act based on the parameter value(s) that is passed.

Stored Procedure Syntax:
```bash
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;	

EXEC procedure_name;	
```


### COMMENTS

**Multi line comment:**
```bash
/*SELECT * FROM Customers;
SELECT * FROM Products;
SELECT * FROM Orders;
SELECT * FROM Categories;*/
```

**Single Line Comment**
```bash
--Happy Comment
```


### DELETE/DROP Table or DATABASE
```bash
CREATE DATABASE testDB;

DROP DATABASE testDB;

CREATE TABLE users;

DROP TABLE users;
```


### BACKUP DATABASE
```bash
BACKUP DATABASE databasename TO DISK = 'filepath';
BACKUP DATABASE testDB TO DISK = 'D:\backups\testDB.bak';
BACKUP DATABASE databasename TO DISK = 'filepath' WITH DIFFERENTIAL;
```



A differential back up only backs up the parts of the database that have changed since the last full database backup. 

### DELECTE Column
```bash
ALTER TABLE table_name DROP COLUMN column_name;
```

### RENAME TABLE 
```bash
ALTER TABLE table_name RENAME COLUMN old_name to new_name;
```

### Changing the DATATYPE

```bash
ALTER TABLE table_name ALTER COLUMN column_name datatype;
```


### SQL Constraints

SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.

The following constraints are commonly used in SQL:

- NOT NULL - Ensures that a column cannot have a NULL value
- UNIQUE - Ensures that all values in a column are different
- PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
- FOREIGN KEY - Prevents actions that would destroy links between tables
- CHECK - Ensures that the values in a column satisfies a specific condition
- DEFAULT - Sets a default value for a column if no value is specified
- CREATE INDEX - Used to create and retrieve data from the database very quickly

# 07 Setting Mongoose in NodeJS
simply go to your app.js
and then go to the documentation of Mongoose and copy the code and paste that code in your main function as below
before running this code you must have to make sure your main database that is mongod query is running in another terminal and on the other hand open another terminal and run mongosh query to access you collected data which you have gathered by 
dealing with the post request of the user:
```bash
const mongoose = require('mongoose');

// Mongoose stuff
main().catch(err => console.log(err));

async function main() {
  await mongoose.connect('mongodb://127.0.0.1:27017/contactdance');
// Defining schemas in Mongoose
  const ContactSchema = new mongoose.Schema({
    name: String,
    phone: String,
    email: String,
    address: String,
    desc: String
  });
  const Contact = mongoose.model('Contact', ContactSchema);
  
  app.post("/contact", (req,res)=> {
    var myData = new Contact(req.body);
    myData.save().then(()=>{
      res.send("This item has been saved in Database");
    }).catch(()=>{
      res.status(400).send("Item was not saved to the data base");
    })})
```
now open your mongosh
type following queries to see your data

```bash
use contactdance
```
```bash
show collections
```
```bash
db.contact.find()
```
# 08 Tailwind Setup

open VS code
run following commands:
```bash
npm init -y
```
```bash
npm install -D tailwindcss postcss autoprefixer vite
```
```bash
npx tailwindcss init -p
```

**NOTE:** where Vite is a local development server written by Evan You and used by default by the Vue project templates.


Create a css file input.css". add it to your html and edit it with this content: 
```bash
@tailwind base;
@tailwind components;
@tailwind utilities;
```

dont forget to link thi css file in your project index.html
```bash
<link href="input.css" rel="stylesheet">
```

Now go to package.json and make a script section as follow:
```bash
  "scripts": {
    "start": "vite"
  },
```
now go to tailwind.config.json file
and replace content: [], with content: ["*"]

Now install a VS code extension
Tailwind css intellisense

```bash
npm run start
```


### How to extend taiwind.config file
first generate tailwind full configuration file using the following command
npx tailwindcss init rabah --full (give any name)

see what you want to change and under which section it lies

then go to tailwind.config file
and add your section in extend section and add your custom properties



### Deployment
simply go to your package.json file and in your script add 
```bash
"scripts": {
    "start": "vite",
    "build": "vite build"
}
```

then
```bash
npm run build
```
# 09 Updating React Project
once you have cloned the repo in your directory
open vs code and type 
```bash
npm install
```
if it shows vulnerablities then type
```bash
npm audit fix
```
if still showing vulnurabilities
review your file and 
type 
```bash
npm audit fix --force
```
after that type
```bash
npm update
```
or you can change manually the version of your libraries by going into 
react.json file and then again insatll npm using
```bash
npm install
```
then run your app
```bash
npm start
```
go to console of you browser look for any error 
if no error then push your app to your master repo 

# 10 CMD Comomands
```bash
ls/dir
```
```bash
pwd
```
```bash
cd 
```
```bash
cd ..
```
```bash
cd ../.. (used to come back twice)
```
```bash
clear/cls
```
```bash
cd / **—> root director**
```
```bash
cd ~
```
```bash
cd <folder/folder/folder> ** <> means to add your own folder names that exist on your computer.
```
```bash
mkdir <folder>
```
```bash
rmdir <folder>
```
```bash
del index.html
```
```bash
start <folder>
```
```bash
echo > index.html to create file
```
```bash
start index.html
```
```bash
open . **for windows use: start .
```
```bash
rename index.html about.html
```
The command rename index.html about.html renames the file index.html to about.html.

start "C:\Program Files\Google\Chrome\Application\chrome.exe"



```bash
rm filename (for deleting file)
```

# 11 Git Commands
```bash
code ~/Desktop/my-project
```
```bash
code index.html
```
```bash
code . (to open Vs code)
```

- i to insert
- q for quit
- escape :wq 

### setting git
```bash
git config --global user.name "username"
```
```bash
git config --global user.email "abc@gmail.com"
```
```bash
git config --global user.name
```
```bash
git config --global user.email
```


### git commands
```bash
git init // (to initialize the git)
```
```bash
git status // (to check whats going on)
```
```bash
touch filename.extension // (create any file)
```
```bash
touch foldername/ // (create a folder)
```
```bash
ls // (list)
```
```bash
ls -lart //  (show all hidden folders)
```
```bash
git rm -filename //  (remove file)
```
```bash
git rm -cached filename  //  (remove file only from staging area)
```
```bash
git log // (to check the history log what we have done)
```
```bash
git checkout -p -no.ofcommits // (to check desired number of modifications  )
```
```bash
git commit -a -m "any message" // (to commit all files)
```
```bash
git commit filename -m "any message" // (to commit) 
```
```bash
git add -A // (tracking all files)
```
```bash
git add filename // (tracking a file by its name)
```
```bash
git checkout branchname //  (to switch from 1 branch to another)
```
```bash
git checkout filename // (to match the file with the last commit)
```
```bash
git checkout -f // (to match all the file with the last commit)
```
```bash
git branch branch_name // (to create a branch)
```
```bash
git checkout -b branchname // (short hand to create and shift to that created branch)
```
```bash
git merge branchname // (to merge the created branch with the master branch)
```
```bash
git reset --merge commit_name // (to merge the code with the given commit name)
```
```bash
git status -s // (tells small status for working tree)
```
```bash
touch .gitignore // (to make gitignore directory)
```
```bash
git branch -a // (to check how many branches are there)
```
```bash
git start filename // (to open any file)
```
```bash
git diff --staged //  (compares staging area with last commit)
```
```bash
git commit -a -m “msg” // (skip staging area and direct commit the changes)
```
```bash
git stash save "optional message" // (This command is used for tempory store your changes in stash file. For example: you are in master branch and made some little changes then you think you need to go to other branch but you cannot go until you commit the changes in master branch. Its not logical to commit for very little changes. So in order to temporary store your changes we use git stash. This command remove your changes and store them into the stash area. so that we can change the branches.
```
```bash
git stash pop //(The git stash pop command will take the content from the stash file and then apply those changes to our current working file) 
```

### How to upload projects on Git hub
click on plus sign on github
```bash
touch .gitignore //(if needed)
```
```bash
git init
```
```bash
git add .
```
```bash
git commit -m "initial commit"
```
```bash
git status
```

### For private files:
you will get an SSH link to make an origin for your repository
then past that link in git bash
```bash
git remote add origin paste SSH link
```
```bash
git push origin master (push my master repository to origin)
```

you will get and error
now you need an authentication 

here first generate you SSH key 
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
you have generated a new SSH key for your project, here you will get a path link in git bash terminal
then type:
```bash
cat (paste that path)
```
you will get you SSH key
now go to settings on github website then go to SSH and GPG keys
then give title and paste that generated key here

now go back to git bash terminal and again type
```bash
git push origin master
```
Congratulations you have successfully uploaded your first project


### Cloning and uploading a folder from system
**create a public repository in github**
then clone it using  HTTP using: $ git clone past_HTTP_Link
then paste your files in that created folder and then use:
```bash
$ git add .
```
```bash
$ git commit -m "initial commit"
```
```bash
$ git push origin master/main
```
then authentication will be requires as :
warning: could not find UI helper 'GitHub.UI'Select an authentication method for 'https://github.com/':1. Web browser (default)2. Device code3. Personal access tokenoption (enter for default): 
enter 1
then go to browers and give password for authentication access
Done!


Creating git repository from terminal
```bash
git init
```
```bash
git add README.md
```
```bash
git commit -m "first commit"
```
```bash
git remote add origin git@github.com:alexpchin/<reponame>.git
```
```bash
git push -u origin master
```

# 12 PUG setup
```bash
npm init
```
```bash
npm install express
```
```bash
npm install pug
```
create two folders namely static and views

// Starting template
```bash
// Importing requirements

const express = require('express');
const path = require('path');
const port = 8000;
const app = express();
// express stuff
app.use('/static',express.static('static'))
app.use(express.urlencoded())

// setting PUG stuff in this app
app.set('view engine', 'pug')
app.set('views', path.join(__dirname, 'views'))

// routing
app.get("/", (req,res)=> {
  params = {
    "Title" : 'Dance Academy',
    "Message": 'This is my first dance academy page'
  }
  res.status(200).render('index.pug', params)
})

// End 

app.listen(port , ()=> {
  console.log(`This app has been loaded successfully via port ${port}`)
})

```

# 13 JSON Server
```bash
npm install -g json-server
```

 for example your data folder have a file db.json
```bash
json-server -p 4000 -w ./data/db.json
```

This will create a database like url containig your json data in that url so can use it for performing operations on it
for example your data folder have a file db.json
```bash
{
  "careers": [
    {
      "id": 1,
      "title": "Senior React Developer",
      "salary": 50000,
      "location": "London, UK"
    },
    {
      "id": 2,
      "title": "Plumber",
      "salary": 40000,
      "location": "Bowser's Castle"
    },
    {
      "id": 3,
      "title": "Gym Leader",
      "salary": 75000,
      "location": "Kanto Region"
    },
    {
      "id": 4,
      "title": "Vue Developer",
      "salary": 40000,
      "location": "Liverpool, UK"
    },
    {
      "id": 5,
      "title": "Tutorial Maker",
      "salary": 35000,
      "location": "Manchester, UK"
    },
    {
      "id": 6,
      "title": "Website Manager",
      "salary": 50000,
      "location": "Berlin, Germany"
    },
    {
      "id": 7,
      "title": "Food Tester",
      "salary": 30000,
      "location": "London, UK"
    }
  ]
}

```
