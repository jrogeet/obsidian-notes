---
topic: php
---


Tags/Topics: #php
∗:[[0 PHP|PHP]]

---
# Design

--- 


- [x] Include/require all other files to `index.php`
- [x] Main Code in App Directory


---
## Videos to go back to:

39.  COMPOSER: https://www.youtube.com/watch?v=rqzYdHdyMH0&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=39&ab_channel=ProgramWithGio




### Concepts:

- ENCAPSULATION & ABSTRACTION: https://www.youtube.com/watch?v=kA9BTNPFObo&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=43&ab_channel=ProgramWithGio
- ABSTRACT CLASSES & METHODS (ITS USES, LOOK FOR EXAMPLES)
- VARIABLE STORAGE & OBJECT COMPARISON https://www.youtube.com/watch?v=zCGmZb3z-r8&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=51&ab_channel=ProgramWithGio
- DOCBLOCKS https://www.youtube.com/watch?v=hdDD0SNJ-pk&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=52&t=26s&ab_channel=ProgramWithGio
- DateTime (NOTFINISHED): https://youtu.be/hkTQkaFzEEo?list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&t=840
- Object Iterators & Iterable Types: https://www.youtube.com/watch?v=QFPP9B-Q3zM&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=58&ab_channel=ProgramWithGio
- OUTPUT BUFFERING https://youtu.be/6vM-9ou1ARo?list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&t=53
- MVC https://www.youtube.com/watch?v=QiO0uUwOiBg&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=65&t=137s&ab_channel=ProgramWithGio
- HTTP HEADER: https://www.youtube.com/watch?v=W7tj0Qlk3rE&list=PLr3d3QYzkw2xabQRUpcZ_IBk9W50M9pe-&index=63&ab_channel=ProgramWithGio
- 








---

### Generate __UNIQUE__ Random Code for the `ROOMS`
**Here's the PHP code that generates a unique 6-digit number and stores it in a MySQL column, ensuring it doesn't already exist:**

PHP

```
<?php
// Establish a connection to your MySQL database
$conn = mysqli_connect("your_hostname", "your_username", "your_password", "your_database_name");

if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}

function generateUniqueNumber($conn) {
    while (true) {
        // Generate a random 6-digit number with potential leading zeros
        $randomNumber = str_pad(rand(0, 999999), 6, '0', STR_PAD_LEFT);

        // Query the database to check if the number already exists
        $query = "SELECT COUNT(*) FROM your_table WHERE your_column = $randomNumber";
        $result = mysqli_query($conn, $query);
        $count = mysqli_fetch_row($result)[0];

        // If the count is 0, the number is unique and can be used
        if ($count === 0) {
            return $randomNumber;
        }
    }
}

// Generate a unique 6-digit number
$uniqueNumber = generateUniqueNumber($conn);

// Insert the unique number into your MySQL table
$query = "INSERT INTO your_table (your_column) VALUES ($uniqueNumber)";
mysqli_query($conn, $query);

// Close the database connection
mysqli_close($conn);

echo "Generated unique number: $uniqueNumber";
?>
```

**Explanation:**

1. **Database connection:** The code first establishes a connection to your MySQL database using your credentials.
2. **`generateUniqueNumber` function:**
    - It generates a random 6-digit number with potential leading zeros using `str_pad(rand(0, 999999), 6, '0', STR_PAD_LEFT)`.
    - It queries the database to check if the number already exists in the specified column.
    - If the count is 0 (meaning it's unique), it returns the number.
3. **Main code:**
    - It calls the `generateUniqueNumber` function to get a unique number.
    - It inserts the unique number into your MySQL table using an INSERT query.
    - It closes the database connection.
    - It prints the generated unique number.

**Important:**

- Replace `your_hostname`, `your_username`, `your_password`, `your_database_name`, `your_table`, and `your_column` with your actual database credentials and table/column names.
- Ensure that the column specified for storing the numbers is of a suitable data type (e.g., INT, VARCHAR).

---

