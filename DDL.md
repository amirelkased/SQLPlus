# Create Schema

```sql
    create user 'username' identified by 'password';
    grant DBA to 'username';
    connect username/password;
```

## To Connect int DataGrip

1. Goto `Create Schema First`

2. Goto **DataGrip**

   1. create Database with `Username` And `password`

### First Step -> Create Schema then Table

```sql
create table Table_Name_Capital
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
Alter table 'Table Name'
    add foreign key ('PK in current Table') references 'PK_Table' ('PK_Name');
```

### Third Step -> Test DataBase And Constraints

1. **Insert**

   ```sql
       - 'Insert All Attriburte In one step'
           insert into 'Table Name' Values(,,,);
       - 'Insert Spacify Attribute if and only if the other att. is NULL'
           insert into 'Table Name'(att1,att2,...)
               values (,,...);
   ```

### Errors

1. **Date error**

   ```sql
    ALTER session set NLS_DATE_FORMAT=’DD/MM/YYYY’;
   ```

2. **timestamp erorr**

   ```sql
   alter session set NLS_TIMESTAMP_FORMAT='YYYY-MM-DD HH:MI:SS.FF';
   ```
