
# Database Schematics

This repo holds all the database communication files for working with the Supabase database.





## Tables & Attributes
1. users:
 {userID, firstName, lastName, email, password, tripID} 


2. userTrips
{tripID,restaurantID,dataVisited}


3. resturuants 
{restaurantID, visitorID, name, restaurantCategory}


4. favourites
 {userID, restaurantName, restaurantID}

5. history
{usierID, restaurantID, resturauntName}

## List of Dependencies
{Table1} --Primary Key --> {Table2}


{user Table} ---tripId --> {userTrips Table}


{userTrips Table} ---restaurantID --> {restaurantTable}


{restaurantTable} --visitorID-> {user table}


{userTable} ---userID--> {favouritesTable}

{userTable} ---userId--> {historyTable}


#### Screenshot:

![image alt](https://github.com/AhmadWali04/Restaurant-Roulette/blob/57dc1a99c5d701f35d58b60555cc596a00e9ea7d/Database/images/databaseDiagram.jpg)



### Explanation
The user goes to a restaurant such as McDonalds. The DB will store the tripID (let say #1).
The tripID will then correspond to one restaurant (Ex: McDonalds).
The restaurant stores its own ID, but also the customers that came (so it is reachable)
Add this to the userHistory table, if hte user likes it can then be added to the Favourites Table.
## Normalization
The database used was a relational database, with atleast 3NF normalization. This means that this database fullfils the properties:
1. All value are atomoic
2. There exist no transistive dependencies
3. Each non-key element is dependent on the primary key

The choice to use a relational database structure stems from the choice to give all users a unique ID, which acts perfectly as a primary key for our list of dependencies.



## Coding:
The program uses two java files to interact with the database, RestaurantDatabase.java and UserDatabase.java 

The program interacts using Java as we are able to directly push the object oriented attributes into the database. All queiries, to read from the database can be done with SQL on Supabase where the database is built.
