## Users 
* id primary key, integer
* first_name varchar
* last_name varchar
* login_id varchar

## Aspirations
* id primary key integer
* category varchar
* title varchar
* time_line varchar
* user_id foreign key, integer 
* description varchar
* budget varchar

## sample SQL queries
* selects first and last names of all users in the database.
```
SELECT first_name, last_name
FROM Users
 ```

* get a list of all the trips my wife wants to go on. 

```
SELECT *
FROM Aspirations
WHERE user_id = $ID_FOR_MY_WIFE 
AND category = "travel";
```

* search all the trips that either I or my wife want to go on.
```
SELECT *
FROM Aspirations
WHERE category = "travel"
AND (user_id = $ID_FOR_MY_WIFE
OR user_id = $ID_FOR_MYSELF);
```