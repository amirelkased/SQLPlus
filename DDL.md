# Create Schema

```sql
    SQL> create user 'username' identified by 'password';
    SQL> grant DBA to 'username';
    SQL> connect username/password;
```

## To Connect in DataGrip

1. Goto `Create Schema First`

2. Goto **DataGrip**

   1. create Database with `Username` And `password`

![Sec1](https://camo.githubusercontent.com/76109812f3127b0f86940373897b04ac8943cb3c0f057f90046444480f61bafd/68747470733a2f2f692e696d6775722e636f6d2f77617856496d762e706e67?utm_source=pocket_mylist)

### First Step -> Create Schema then Table

```sql
SQL> create table Table_Name_Capital
(
     'Name     Datatype   NULL/NOT  Default if exists'

    Attirbute1   int       NOT NULL  default =000000,
    Attirbute2   number(1) NOT NULL CHECK ( Semester > 0 AND Semester < 4 ),
    Attirbute3   char(2)   NOT NULL,

     'like flags the next line'

    constraint ATM_PK
        primary key (St_ID, C_ID, Pro_ID, Year, Semester)

     'if you have candidate keys you can use `Unique`'

    unique(attribute1,...);
);
```

### Second Step -> Add Foreign Keys

```sql
    SQL> Alter table 'Table Name'
        add foreign key ('PK in current Table') references 'PK_Table' ('PK_Name');
```

### Third Step -> Test DataBase And Constraints

1. **Insert**

```sql
    - 'Insert All Attriburte In one step'

        SQL> insert into 'Table Name' Values(,,,);

    - 'Insert Spacify Attribute if and only if the other att. is NULL'

        SQL> insert into 'Table Name'(att1,att2,...) values (,,...);
```

![Sec2](https://camo.githubusercontent.com/76109812f3127b0f86940373897b04ac8943cb3c0f057f90046444480f61bafd/68747470733a2f2f692e696d6775722e636f6d2f77617856496d762e706e67?utm_source=pocket_mylist)

### Create, Update and remove on table

```sql
    1. 'Create Table is mention above'

    2. 'To insert a missing attribute'

        SQL> alter table 'Table_name' add 'Attribute Name' 'DT:number'

    3. 'Remove a specify Atrribute'

        SQL> alter table 'Table_name' drop column 'Atrribute_Name'

    4. 'Remove Table'

        SQL> drop table 'Table_name'
```

![Sec3](https://camo.githubusercontent.com/76109812f3127b0f86940373897b04ac8943cb3c0f057f90046444480f61bafd/68747470733a2f2f692e696d6775722e636f6d2f77617856496d762e706e67?utm_source=pocket_mylist)

### Datetype

- STRING

  ```sql
      - 'VAR -> it is have fixed size'

          SQL> ATT_Name_Capital  VAR

      - 'VARCHAR(x) -> it is have variable size limited with x'

          SQL> ATT_Name_Capital  VARCHAR(max size)
  ```

- DATE

  ```SQL
      - 'DATE -> it is record Date not intersted When happend'

          SQL> ATT_Name_Capital DATE

      - 'DATETIME -> it is recorded date with time'

          SQL> ATT_Name_Capital DATETIME

      - 'TIMESTAMP -> it is recorded date with time for now is update or added'

          SQL> ATT_Name_Capital TIMESTAMP
  ```

- NUMBERS

  ```SQL
      - 'DECIMAL(Before dec point (int),After dec point (fraction) )'

        SQL> ATT_Name_Capital DECIMAL(X,Y)
  ```

![Sec4](https://camo.githubusercontent.com/76109812f3127b0f86940373897b04ac8943cb3c0f057f90046444480f61bafd/68747470733a2f2f692e696d6775722e636f6d2f77617856496d762e706e67?utm_source=pocket_mylist)

### Errors Section

1. **Date error**

   ```sql
    SQL> ALTER session set NLS_DATE_FORMAT=’DD/MM/YYYY’;
   ```

2. **timestamp erorr**

   ```sql
   SQL> alter session set NLS_TIMESTAMP_FORMAT='YYYY-MM-DD HH:MI:SS.FF';
   ```

3. **Forget User Or Pass Or Hot to determine users**

```sql
    - 'Open your SQL command line and type the following:'

        SQL> connect / as sysdba

    - 'Once connected,you can enter the following query to get details of username and password:'

        SQL> select username,password from dba_users;

    - 'This will list down the usernames,but passwords would not be visible.
       But you can identify the particular username and then change the password for that user.
       For changing the password,use the below query:'

        SQL> alter user username identified by password;

    - 'Here username is the name of user whose password you want to change and password is the new password.'

    - 'To Delete Users'

        SQL> drop user 'username' cascade;
```
