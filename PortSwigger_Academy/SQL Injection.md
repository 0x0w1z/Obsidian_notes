What's SQL Injection -> It's a web vulnerability where the attackers can retrieve the data which cannot be gain normally through database like the credentials of user or admins.


![[Pasted image 20241013000412.png]]
![[Pasted image 20241013000627.png]]

#### Warning

Take care when injecting the condition `OR 1=1` into a SQL query. Even if it appears to be harmless in the context you're injecting into, it's common for applications to use data from a single request in multiple different queries. If your condition reaches an `UPDATE` or `DELETE` statement, for example, it can result in an accidental loss of data.

////////////////////////////////////////////////////////////////////////

The SQL injection payload `'+OR+1=1--` is a common example of a **logical SQL injection attack**. Here's a breakdown of how it works:

### Explanation of Each Part:

1. **`'` (Single Quote)**:
    
    - The single quote is used to close or terminate a string in the SQL query. For example, if the original query is:
        
        sql
        
        Copy code
        
        `SELECT * FROM users WHERE username = 'input';`
        
        If you provide `'` as part of the input, it prematurely closes the string, allowing you to manipulate the query further.
2. **`OR`**:
    
    - The `OR` operator is used to combine conditions in SQL. It means that if either of the conditions on either side of the `OR` is true, the whole condition will be true. By injecting `OR`, you can bypass the original condition.
3. **`1=1`**:
    
    - This is a tautology, a condition that is always true. Since `1=1` is always true, the injected condition forces the query to return results regardless of the actual query conditions. In other words, even if the original condition would normally restrict access, this ensures the query always evaluates to true.
4. **`--` (Comment)**:
    
    - The `--` sequence in SQL indicates a comment. Everything after `--` is ignored by the SQL engine, which effectively nullifies the rest of the original query. This prevents syntax errors that might occur due to the injection.

### How It Works in Practice:

Suppose the original query is something like:

sql

Copy code

`SELECT * FROM users WHERE username = 'input' AND password = 'password';`

If you inject `'+OR+1=1--`, the query becomes:

sql

Copy code

`SELECT * FROM users WHERE username = '' OR 1=1--' AND password = 'password';`

This does two things:

- The `username` condition (`username = ''`) is ignored because the `OR 1=1` part ensures that the condition always evaluates to true.
- The `--` makes everything after it a comment, so the `AND password = 'password'` part is ignored.

As a result, this query returns all users in the database because the condition `OR 1=1` is always true.

![[Pasted image 20241013003349.png]]

