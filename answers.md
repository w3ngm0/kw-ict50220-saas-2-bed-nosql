---
updated: 2026-06-24T00:16
created: 2026-06-23T21:09
---
# Answers
### Step 2 : NoSQL Systems

**2.1 Defining Terms**
```text
Briefly explain what is meant by the terms database, collection, document and field in terms of MongoDB. 
- A Document is the smallest unit of data storage, represented in BSON (Binary JSON) format in MongoDB.
- A collection  is a group of related documents that correspond to an entity. 
- Database is a container for collections. A group of collections is housed in a database.
- Fields are the fundamental building blocks of MongoDB documents, similar to columns in relational databases. 
  They define the structure and data stored within a document. A field is represented as a key-value pair. 
```
**2.2 NoSQL Database Types**
```text
Briefly outline the key features and advantages for TWO of the following NoSQL database types:
* Document Database
* Key-Value Store 
* Wide-Column Oriented Database
* Graph Database 

1. Document Database

A document database stores data as flexible documents, typically in JSON or BSON format. 
Each document can have a different structure, making the database highly adaptable to changing requirements.

Advantages:

* Flexible schema allows easy handling of unstructured or semi-structured data.
* Scales horizontally across multiple servers.
* Stores complex objects in a single document, reducing the need for joins.
* Well suited for content management systems, e-commerce platforms, and web applications.

2. Graph Database

A graph database stores data as nodes (entities) and edges (relationships), making relationships a first-class component of the data model.

Advantages:

* Efficiently handles highly connected data.
* Enables fast traversal of complex relationships.
* Ideal for social networks, recommendation engines, fraud detection, and network analysis.
* Simplifies queries involving multiple relationships compared to relational databases.
```

**2.3 NoSQL Database Systems**
```text
Provide one example product (commercial or open source) for each of your NoSQL Database types.
You may **NOT** include _MongoDB_which is an example of a _Document Database_.

One example product for each of the NoSQL Database types:
- Document Database: Couchbase | [couch-base](https://docs.couchbase.com/home/index.html)
  Couchbase combines document-oriented and key-value data models, offering flexibility and high performance
  
- Graph Database: Neo4j | [neo4j](https://neo4j.com/product/neo4j-graph-database/)
  Neo4j is a native graph database designed to store, manage, and query connected data efficiently.

```

**2.4 NoSQL Database Users**
```text
Provide and example for each of your NoSQL database of the situation when your database types may provide a benefit when used.

The situations/application of the database types must be different. 

1. Document Database = Couchbase  
   Situation : Due to Couchbase's high performance and low latency it is suitable for a variety of use cases such as:
   - Real-Time Analytics: Couchbase is ideal for performing real-time analytics on a large data sets. 
   - E-Commerce and Customer Management: Couchbase is also used for E-commerce to manage transactions efficiently and 
     can manage high volumes of customer data.
     
2. Graph Database  
   Situation:  Due Neo4j's ability to manage large-scale, interconnected data it is well-suited for a variety of use cases such as:
   - Fraud Detection: Neo4j's graph model makes it easy to identify patterns and anomalies in these relationships, allowing 
     fraud analysts to quickly detect and prevent fraudulent activity. Neo4j can be used to build fraud detection systems for 
     industries like banking, insurance and e-commerce.    
   - Healthcare management systems: Healthcare involves managing and analyzing complex relationships between patients, medical professional, 
     medical records and treatments. Neo4j's graph-based model is well-suited to represent these relationships as a network of nodes and 
     relationships. Neo4j can be used to build healthcare management systems that allow doctors and healthcare professionals to navigate and analyze 
     medical data and patient records. 

```
### Step 3 : NoSQL Databases & Collections 
**3.1 Naming databases, collections and fields**
```text
There are many naming conventions for variable names, functions, database fields, tables, collections and so on. 
For the NoSQL database selected, which naming convention would you select for the database, collections and fields,
and why? 
```
> For the NoSQL database naming conventions I would select for each convention would be: 
> 
| MongoDB    | Recommended Style | Example                 |
|------------|-------------------|-------------------------|
| Database   | snake_case        | student_portal          |
| Collection | snake_case        | orders, user_profiles   |
| Field      | camelCase         | createdAt, emailAddress |
> -  Justification on why this naming convention was chosen.
> - Databases serve as the foundation for our collections. Naming them effectively will help clearly describe the data it contains. It should
> be descriptive and leave no confusion. Watch out for spaces at the beginning or end of database names. MongoDB use JavaScript or JSON-based formats.
> snake_case is clearer for database and collection names. 
> - Collections are like containers that holds related documents. Choosing right names for it should tell a detail of what kind of data
> they hold. Lowercase collection names are preferred. Choosing a camelCase of snake_case either is appropriate. However, they must be consistent.
> - Fields should be descriptive and simple, they should not leave any confusion. They should hold lower cases to keep things uniform
> and simple and stay the course with whatever naming convention we choose, hold with it. Using camelCase for field name helps with this. 

 
**3.2 Connecting**
```text
Connect to a running instance of MongoDB (preferred to be your MongoDB Atlas instance). 
- What was the connection string used to connect to your instance of MongoDB? 
Give the connection string and a complete CLI command using the MongoDB shell. 
Example: mongos mongodb://192.168.0.5:9999/foo 
```
![img.png](assets/images/step-3-002.png)
 
**3.2 Database Creation**
>Create and use a database named:
> * saas_bed_portfolio_2026S1
> 
> where YYYY is the Year and SN in the semester, for example S1
> * How did you create the database using the CLI?
> -> using : use saas_bed_portfolio_2026S1, from the CLI. 
> * Did you encounter any issues when creating the database? 
> -> Yes, I had MongoServerError: bad auth :authentication failed due to wrong password. 
> * If you did, how did you resolve them? 
> -> Inserted the correct credentials to connect to my MongoDB Atlas  

![img.png](assets/images/step-3-002.2.png)


**3.3 Schema Design for Collection**
> An example of the possible data that may be stored in this collection.
> 
| Data Item       | Suggested Data Type | Example Data              |
|-----------------|---------------------|---------------------------|
| title           | String              | Aliens                    |
| year            | Integer             | 2009                      |
| writers         | Array of strings    | Sean Bean, Isaac Newton   |
| franchise       | String              | Avatar                    |
| running time    | Integer (minutes)   | 162                       |
| budget          | Long integer (USD)  | 237000000                 |
| actors          | Array of strings    | Kiefer Sutherland, Rex    |
| directors       | Array of strings    | Patrick Stewart           |
| summary         | String              | Ipsum lorem exa dux       |
| random          | Integer (Double)    | 0.44                      |
| imdb id         | String              | tt0499549                 |
| imdb rating     | Integer             | 7.9                       |
| rotten tomatoes | Integer             | 34                        |
| genres          | Array of Strings    | Drama, Sci-Fi             |
| updated_at      | Date                | 2026-05-22T08:53:23.387Z  |

> What data type are you using for each field?
> The movie collection will store a variety of MongoDB data types. String data types will be used for 
> fields such as `title`, `franchise`, `summary`, and `imdb_id`. 
> Integer data types will be used for `year`, `running_time`, and `rotten_tomatoes`. 
> The budget field will use the Long data type to support large currency values.
> Arrays of strings will be used for `writers`, `actors`, `directors`, and `genres` because multiple values can be stored in a single field.
> The `random` field will use the Double data type to store decimal values.


> Identify the validation rules you wish to apply
> * title is required and must be a string.
> * year is required and must be an integer.
> * year should be between 1888 and 2100.
> * running_time must be a positive integer.
> * budget must be a long integer and cannot be negative.
> * writers, actors, directors, and genres must be arrays of strings.
> * imdb_id is required and must follow the IMDB format, such as tt0499549.
> * rotten_tomatoes must be an integer between 0 and 100.
> * random must be a double between 0 and 1.
> * updated_at must be date values.
> * box_office → Long / Int
> * imdb_rating → Double or Null
> * imdb_id → String or Null
> * rotten_tomatoes → Int or Null 
 

> Provide the schema validation code for the collection. 

```php

db.createCollection("films", {
  validator: {
    $jsonSchema: {
      bsonType: "object",
      required: ["title"],
      description: "Film collection documents",

      properties: {
        _id: {
          bsonType: "objectId",
          description: "Unique document identifier"
        },

        title: {
          bsonType: "string",
          description: "Movie title"
        },

        year: {
          bsonType: "int",
          description: "Year the film was released"
        },

        writers: {
          bsonType: "array",
          description: "List of writers",
          items: {
            bsonType: "string"
          }
        },

        franchise: {
          bsonType: "string",
          description: "Film franchise name if applicable"
        },

        running_time: {
          bsonType: "int",
          description: "Running time in minutes"
        },

        budget: {
          bsonType: ["int", "long", "null"],
          description: "Production budget"
        },

        box_office: {
          bsonType: ["int", "long", "null"],
          description: "Box office revenue"
        },

        actors: {
          bsonType: "array",
          description: "List of actors",
          items: {
            bsonType: "string"
          }
        },

        directors: {
          bsonType: "array",
          description: "List of directors",
          items: {
            bsonType: "string"
          }
        },

        summary: {
          bsonType: "string",
          description: "Brief plot summary"
        },

        random: {
          bsonType: ["double", "int"],
          description: "Random value used for sampling"
        },

        genres: {
          bsonType: "array",
          description: "List of genres",
          items: {
            bsonType: "string"
          }
        },

        imdb_id: {
          bsonType: ["string", "null"],
          description: "IMDb identifier"
        },

        imdb_rating: {
          bsonType: ["double", "int", "null"],
          description: "IMDb rating"
        },

        rotten_tomatoes: {
          bsonType: ["int", "null"],
          description: "Rotten Tomatoes score"
        },

        updated_at: {
          bsonType: "date",
          description: "Date the document was last updated"
        }
      }
    }
  }
});
```

**3.4 Collection Creation**

Using db.collections.insertOne()

```php
db.films.insertOne({
 title: "Star Trek: Nemesis",
 year: 2002,
 writers: ["John Logan", "Rick Berman", "Brent Spiner"],
 summary: "A clone of Picard, created by the Romulans, assassinates the Romulan Senate, assumes absolute power, and lures Picard and the Enterprise to Romulus under the false pretext of a peace overture.",
 franchise: "Star Trek",
 running_time: 117,
 budget: 60000000,
 box_office: 67300000
 })
```

![img.png](assets/images/step-3-004.png)

**4.1 Inserting Data**

```php
db.films.insertOne({
 title: "My Dearest Assassin",
 year: 2026,
 writers: ["Watthana Veerayawatthana"],
 actors:["Pimchanok Luevisadpaibul", "Tor Thanapob Leeratanakachorn", "Sivakorn Adulsuttikul"],
 running_time: 127,
 budget: 237000000,
 genres: ["Action", "Romance", "Thai", "Thriller", "Drama"]
 })
```

![img_1.png](assets/images/step-4-001.png)


**4.2 Inserting Data from File**
```text
film-data-json.txt
```

```php
$ mongoimport --uri "mongodb+srv://20070505_db_user:<MY_PASSWORD>@cluster0.wxkuth2.mongodb.net/saas_bed_portfolio_2026S1" --collection "
films" --type json --file "film-data-json.txt" --jsonArray
```

![step-4-002.png](assets/images/step-4-002.png)

**4.3 Inserting Data**

```php
db.films.insertMany([
{
title: "Pride",
year: 2014,
writers: ['Stephen Beesform'],
franchise: "",
running_time: 192,
imdb_rating: 7.8
},
{
title: "Pee Wee Herman's Big Adventure",
},
{
title: "A Fictional Tale as a Fake Film",
}
])
{
```

![img.png](assets/images/step-4-003.png)


## Software as a Service - Back-End Development

#

## Diploma of Information Technology (Advanced Programming)  

#

## Diploma of Information Technology (Back-End Development)

Replace GIVEN_NAME_HERE, FAMILY_NAME_HERE and STUDENT_ID_HERE entries with your details:

| Given Name | Family Name | Student ID  |
|------------|-------------|-------------|
| Anna       | Seed        | x1234567890 |
| Kelden     | Wangmo      | 20070505    |



# Declaration

I, THE ABOVE NAMED student, by submitting this assessment, I am acknowledging the following:

- The submission is completely my own work.
- I have not used AI in the formation of the answers within this assessment.
- I have acknowledged all sources of information used in this work (if required).
- I have kept a copy of this assessment (where practicable).
- I understand a copy of my assessment will be kept by TAFE for their records.
- I understand my assessment may be selected for use in the TAFEs validation and audit process to ensure student assessment meets requirements.

When submitting this assessment, I am accepting the above acknowledgement.


---

```table-of-contents
title: # Contents
style: nestedList
minLevel: 0
maxLevel: 3
includeLinks: true
```

---

# How to Answer Questions

Each time you answer a question, fill out the space provided for the answer to the question.

## Answer Requiring an Explanation

Answers to questions should be completed as "block quotes", replacing the `ANSWER_HERE` with the answer, and preceding each line with a greater than sign `>`. To add a new paragraph ensure you leave a `>` with no text after it.

Example:

```markdown
    

## Question Z - How many sofwarte developers does it take to change a lightbulb?
    
    > None. 
	> It is a hardware problem.
```

## Answer Requiring Code

When answering a question that requires code to be included, use a "code block", which starts with three back-ticks (/`) plus the language for the code (e.g. php, js, cpp, python, shell, text, et al).

Example:

```markdown
	

## Question X - Title

	Query Solution:

	```js
	db.collection_name.find();
	```
```

> Note: 
>
> The NoSQL code used to answer the question is contained in a code block,wich opens with three back-ticks (\`\`\`) followed by js, contains the code on the lines below, and ends with three back-ticks (\`\`\`) at the start of the next line after the code. An example is shown above.
> 
> It is important that code blocks start at the beginning of the line for formatting on GitHub, Obsidian or your preferred IDE render the code correctly.

## Answer Requiring Image(s) to Be Inserted

Images are to be saved in a folder called "`assets`" and are embedded into the Markdown document.

Images for this assessment MUST be named in the form `step-X-Ya.ext` where:

- `X` is the step number (e.g. for step 5 the number is `5`)
- `Y` is the question dot number (e.g. for question `2.3` the dot number is `3` )
- `a` is an optional letter to allow for multiple images for an answer.
- `ext` is the filename extension (e.g. `png`, `jpg`, `jpeg`, `svg`, et al)

To insert an image use the following syntax:

```markdown
![Short Image Title](./folder/filename.extension)
```

For example, the markdown code:

```markdown
![Embedding an Image Example](./assets/step-N-XXX.png)
```

Gives:

![Embedding an Image Example](assets/step-N-XXX.png)

---


# Step 1: Setting Up for Assessment

This step provides a checklist for yout to ensure you have set up the assessment requirements as needed.


## Checklist

Put an X between each of the pairs of `[ ]` when you have completed the task:

> - [ ] Create a new **empty** & **private** repository on GitHub (or the equivalent).
> - [ ] Repository is named `xxx-ICT50220-SaaS-2-BED-NoSQL` replacing `xxx` with your initials.
> - [ ] Cloned the repository to your local PC.
> - [ ] Created a new folder called `assets` inside your cloned repository.
> - [ ] Created an empty `ReadMe.md`.
> - [ ] Created an empty `.gitignore` file in the assets folder.
> - [ ] Downloaded the provided `sample.gitignore` file, moved it into the repository folder, and renamed it to `.gitignore`.
> - [ ] Placed a copy of the assessment's Word document into the repository folder.
> - [ ] Added all the new files and folders to the repository, commited them to version control, and pushed them to your private remote repository.

---

# Step 2: NoSQL Systems

This step verifies you understand concepts that includes, but is not limited to such as databases, collections, fields, documents and naming conventions.

## 2.1 Defining Terms

Briefly explain what is meant by the terms database, collection, document and field in terms of MongoDB.

> ANSWER_HERE
>
> 

## 2.2 NoSQL Database Types

Briefly outline the key features and advantages for TWO of the following NoSQL database types:

- Document Database
- Key-Value Store
- Wide-Column Oriented Database
- Graph Database

> #

## Database Type 1: NAME_HERE
>
>  ANSWER_HERE


> #

## Database Type 2: NAME_HERE
>
> ANSWER_HERE 


## 2.3 NoSQL Database Systems

Provide one example product (commercial or open source) for each of your NoSQL NoSQL Database types.

You may **NOT** include _MongoDB_ which is an example of a _Document Database_.

> #

## Database Type 1: NAME_HERE
>
> ANSWER_HERE


> #

## Database Type 2: NAME_HERE
>
> ANSWER_HERE


## 2.4 NoSQL Database Uses

Provide an example for each of your NoSQL database of the situation when your database types may provide a benefit when used.

The situations/application of the database types must be different.

> #

## Database Type 1: NAME_HERE
>
> ANSWER_HERE


> #

## Database Type 2: NAME_HERE
>
> ANSWER_HERE



# Step 3: NoSQL Databases & Collections

## 3.1 Naming Databases, Collections and Fields

What naming convention will you use for the database, collections and fields used in the assessment scenario?

> ANSWER_HERE
>
>

Justify why did you choose this naming convention?

> ANSWER_HERE
> 
>

## 3.2 Connecting

- Connect to a running instance of MongoDB (preferred to be your MongoDB Atlas instance).

Add the Connection String used to connect to your MongoDB Atlas instance:

> ```js
> 	MONGODB_CONNECTION_STRING_HERE
> ```


#

## 3.3 Database Creation

- Create and use a database named `saas_bed_portfolio_2025s2`.

> ```js
> 	CREATE_AND_USE_DATABASE_IN_MONGODB_ANSWER_HERE
> ```

Did you encounter any issues when creating the database? If you did, how did you resolve them?

> ANSWER_HERE
>


## 3.4 Schema Design for Collection

Using the sample data provided, identify the field types and suitable names for the data storage in a MongoDB database.

In the `notes` column, add any clarifying details (such as rules) that may be useful.

Replace `FIELD_NAME_HERE` and `DATA_TYPE_HERE` in the table below.

> | Item                | Field Name      | MongoDB Data Type | Notes / Rules         |
> |---------------------|-----------------|-------------------|-----------------------|
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> | Title               | FIELD_NAME_HERE | DATA_TYPE_HERE    | four digit year       |
> | Year                | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> | Writers             | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> | Summary             | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> | Franchise           | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> | Running Time        | FIELD_NAME_HERE | DATA_TYPE_HERE    | minutes               |
> | Budget              | FIELD_NAME_HERE | DATA_TYPE_HERE    | USD $                 |
> | Box Office Takings  | FIELD_NAME_HERE | DATA_TYPE_HERE    | USD $                 |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |
> |                     | FIELD_NAME_HERE | DATA_TYPE_HERE    |                       |


- Provide the schema validation code for the collection.

> ```js
> 	SCHEMA_VALIDATION_CODE_HERE
> ```



## 3.5 Collection Creation

- Create a new collection named _films_ and insert the provided data (full statement)

> ```js
> 	CREATE_COLLECTION_IN_MONGODB_ANSWER_HERE
> ```


Screen Shot:

![Step 3.5 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



# Step 4: CRUD - Create


## 4.1 Inserting Data

- Add the supplied sample data into the films collection using a **SINGLE** MongoDB Shell COMMAND in the order provided.

Query Solution:

```js
	db.collection_name.find();
```



## 4.2 Inserting Data

From the LMS, download the provided data files, and determine which one you will use to import data into the collection. 

The options are: `film-data-tsv.txt`, `film-data-csv.txt`, and `film-data-json.txt`.

Using the `mongoimport` CLI command, import the data from one of the files to your collection.

What was the complete command you used to perform the import of the provided sample data?

Query Solution:

```js
	db.collection_name.find();
```



## 4.3 Inserting Data

Add the provided additional sample data into the films collection in the order provided.

> You do not have to add any details to the answers.md for this question.


# Step 5: CRUD - Retrieve Queries


## 5.1 Retrieve all documents

- Get all documents from the films collection.

Query Solution:

```js
	db.collection_name.find();
```
	


## 5.2 Retrieve all films written by…

- Get all documents with `writer` set to "`Quentin Tarantino`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 5.3 Retrieve films with actor(s)…

- Get all documents where `actors` include "`Brad Pitt`"

Query Solution:

```js
	db.collection_name.find();
```
	


## 5.4 Retrieve films from a franchise…

- Get all documents with `franchise` set to "`The Hobbit`"

Query Solution:

```js
	db.collection_name.find();
```
	


## 5.5 Retrieve films released in range…

- Get all films released between `1980` and `2020`

Query Solution:

```js
	db.collection_name.find();
```
	
Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)


## 5.6 Retrieve films longer than…

- Get all films with a running time of over `120` minutes

Query Solution:

```js
	db.collection_name.find();
```


## 5.7 Retrieve films released in range…

- Get all films released after `2022`.

Query Solution:

```js
	db.collection_name.find();
```
	
Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



# Step 6: CRUD - Updates

## 6.1 Update document with a synopsis

- Using one or more queries, add the provided synopses to the indicated films.

Query Solution:

```js
	db.collection_name.find();
```
	


## 6.2 Update document with an actor

- Add the provided actors to the required films using one or more queries in the order provided...

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)


# Step 7: CRUD – Searches

Performing searches on collections.


## 7.1 Searching for titles with …

- Find all films with the `title` starting with "`T`".

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 7.2 Searching for synopses with …

- Find all films that have a `genre` that contains the letters "`th`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 7.3 Searching for synopses with… and not …

- Find all films that have a `synopsis` that contains the word "`Captain`" and not the word "`Pike`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 7.4 Searching for synopses with … or …

- Find all films that have a `synopsis` that contains the word "`London`" or "`Brooklyn`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 7.5 Searching for synopses with … and …

- Find all films that have a synopsis that contains the words "`team`" and "`search`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



# Step 8: CRUD - Deletions

This step requires you to remove films from the collection.


## 8.1 Removing a film using its title…

- Use the title to delete the film "`Pee Wee Herman's Big Adventure`"

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 8.2 Remove a film by ID…

Delete the film “`Fictionally Fake Film`” by:

- Writing a query to discover the film ID
- Then using the found ID to remove the film

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 8.3 Removing multiple films…

- Delete any films with the exact word “`Fictional`” in their title, ignoring case.

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



# Step 9: NoSQL Indexes

Using the films collection, create the indexes to match the following conditions:


## 9.1 Indexes for Sorting

- Create an index on the `title` field.

Query Solution:

```js
	db.collection_name.find();
```


- Create an index on the `year` and `title ` fields.

Query Solution:

```js
	db.collection_name.find();
```

- Create an index on the `franchise`, `title`, `actors`, `year` fields.
- The index must be in the order year, title, actors then franchise.

Query Solution:

```js
	db.collection_name.find();
```


## 9.2 Indexes for Full Text Search

- Create a text index on the `title ` and `summary` fields.

Query Solution:

```js
	db.collection_name.find();
```


## 9.3 Verifying Execution Plans

- Check the execution plan for a query that finds the films with a title containing “Star”. 
- Check if the created index is being used.

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 9.4 Differences in Indexes

- Briefly explain the differences between an index for sorting against an index for full text searches.
- Include in your answer when each is best suited for use.

> ANSWER_HERE
>
> 


# Step 10: Aggregation

In this step you will be aggregating data within a collection.


## 10.1 Counting documents

- Write an aggregation query to count the number of `Star Trek` films.

Query Solution:

```js
	db.collection_name.find();
```


## 10.2 Mean budget and box office takings…

- Write an aggregation query to calculate the average budget and box office takings.
- Display both values.

Query Solution:

```js
	db.collection_name.find();
```


## 10.3 Profit earnings

- Write an aggregation query to calculate the profit (box office – budget) for the films, showing just the film title and the profit.
- Films with no budget and/or no box office should NOT be included in the results.

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 10.4 Grouping data

- Write the query to group films by their franchise and count the number of films in each franchise.

Query Solution:

```js
	db.collection_name.find();
```



# Step 11: Triggers

Using the films collection, we are now going to create triggers to provide an audit trail for when data is added, updated or deleted.

## 11.1 Create trigger for inserted data

- Create a trigger that monitors the films collection for new data being added. 

Query Solution:

```js
	db.collection_name.find();
```



## 11.2 Testing the insert trigger works correctly

- Use the following data to check the trigger functions as expected:

Query Solution:

```js
	db.collection_name.find();
```



## 11.3 Create trigger for updated data

- Create a trigger that monitors the films collection for new data being added. 

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)



## 11.4 Testing the update trigger works correctly

- Use the following data to verify that the trigger functions as expected. Make sure that these updates are completed in more than one query:

Query Solution:

```js
	db.collection_name.find();
```



## 11.5 Create trigger for deleted data

- Create a trigger that monitors the films collection for new data being added. 

Query Solution:

```js
	db.collection_name.find();
```


## 11.6 Testing the delete trigger works correctly

- Use the following conditions to verify that the trigger functions as expected:

Query Solution:

```js
	db.collection_name.find();
```



## 11.7 Verify the log contains data…

- Write a query to show the data in the film audit log.

Query Solution:

```js
	db.collection_name.find();
```

Screen Shot:

![Step 3.3 Screenshot](assets/SCREENSHOT_FILENAME_HERE.png)




# Step 12: Submission

What is the URL for your GitHub (or equivalent) repository for this assessment?

```text
add url here
```

# END
