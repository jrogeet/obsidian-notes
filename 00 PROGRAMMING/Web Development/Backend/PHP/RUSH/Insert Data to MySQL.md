```php
include("database.php");

$username = "Patrick";
$password = "rock3";
$hash = password_hash($password, PASSWORD_DEFAULT);

$sql = "INSERT INTO users (user, password)
		VALUES ('$username', '$hash')";

try{
	mysqli_query($conn, $sql);
	echo "User is now registered";
}
catch(mysqli_sql_exception) {
	echo "Could not register user";
}

mysqli_close($conn);
```

> [!warning]
>  Don't let the User Input be accepted as a query to the Database
> ![[Pasted image 20240409163259.png]]
> This would be bad for SQL Injection,
> because we are putting the user input directly to the query
> - The user could input a query that would delete the whole table or database
>? [!done]
>![[Pasted image 20240409163428.png]]
>or we could name it instead of just `?`:
>![[Pasted image 20240409163516.png]]

