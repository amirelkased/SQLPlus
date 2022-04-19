# Create Schema

```sql
    SQL> create user 'username' identified by 'password';
    SQL> grant DBA to 'username';
    SQL> connect username/password;
```

## To Connect int DataGrip

1. Goto `Create Schema First`

2. Goto **DataGrip**

   1. create Database with `Username` And `password`

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
           SQL> insert into 'Table Name'(att1,att2,...)
               values (,,...);
   ```

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
```
