# SQL commands

## Login

In the terminal, type

```
mysql -u root
```

## Create database

```
create database <name>;
```
## List database
```
show databases;
```

## Switch to a database (make it active)
```
use <name>;
```

## Create a new table
```
create table parents (
    parent_id int unsigned auto_increment primary key,
    surname varchar(50) not null,
    proper_name varchar(50) not null
 ) engine=innodb;
 ```

 ## To see all tables
 ```
 show tables;
 ```

 ## To see all the columns of a table
 ```
 describe <table name>;
 ```

 ## To delete table, use:

 ```
 drop table <name>
 ```

# Change table using `alter table`

 
## Add in a new columns

```
alter table child add gender varchar(1) not null;
```

## Drop (aka. remove) a columns
```
alter table child drop gender;
```

## Rename a column
```
alter table child rename column proper_name to last_name;
```

## Add a new foreign key
```
// 1. create the new column
alter table sessions add coach_id int unsigned not null;

// 2. create the foregin key
alter table sessions add constraint fk_coach_id foreign key (coach_id) references coaches(coach_id);
```