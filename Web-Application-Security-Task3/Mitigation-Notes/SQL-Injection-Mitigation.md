# SQL Injection Mitigation

## 1. Mitigation

The primary mitigation for SQL Injection is to use prepared statements or parameterized queries.

Prepared statements prevent user-controlled input from being interpreted as part of the SQL query structure.

---

## 2. Vulnerable Query

A vulnerable application may directly concatenate user input into an SQL query:

```sql
SELECT first_name, last_name FROM users WHERE user_id = '$id';

Directly inserting user input into the query can allow SQL Injection.

3. Secure Query

A parameterized query should be used instead:

SELECT first_name, last_name FROM users WHERE user_id = ?

The user input is supplied separately as a parameter.

4. Prepared Statement Implementation

Example implementation using PHP and MySQLi:

$query = "SELECT first_name, last_name FROM users WHERE user_id = ?";

$stmt = mysqli_prepare($GLOBALS["___mysqli_ston"], $query);

mysqli_stmt_bind_param($stmt, "s", $id);

mysqli_stmt_execute($stmt);

$result = mysqli_stmt_get_result($stmt);
5. Why It Works

Prepared statements separate SQL code from user-supplied data.

Therefore, SQL syntax included in user input is treated as data instead of being interpreted as part of the SQL command.

This prevents the input from modifying the intended SQL query structure.

6. Additional Security Controls

Additional security controls include:

Server-side input validation
Least-privilege database accounts
Secure error handling
Regular security testing
Avoiding direct SQL string concatenation
7. Validation

After applying the prepared-statement implementation, the same SQL Injection test payload should no longer modify the SQL query logic.

The application should process the input as data rather than SQL syntax.

8. Conclusion

Parameterized queries provide the primary defense against SQL Injection by separating SQL instructions from user-controlled data.

Prepared statements should be used whenever user input is included in database queries.


**File path:**

Mitigation-Notes/SQL-Injection-Mitigation.md