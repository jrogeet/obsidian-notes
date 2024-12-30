---
topic: php
---


Tags/Topics: #php #controlstructure
∗:[[0 PHP|PHP]]

---
# Design

--- 
This works but __NOT READABLE__:
```php
<html>
	<head>
	</head>
	
	<body>
		<?php
		$score = 95;
		
		if ($score >= 90) { ?>
		<strong>A</strong>
		<?php } elseif ($score >= 80) { ?>
	</body>
</html>
```

#### Replace  Curly Braces`{ }` with Colons `:`:
```php
<html>
	<head>
	</head>
	
	<body>
		<?php $score = 95; ?>
		
		<?php if ($score >= 90): ?>
			<strong style="color: green;">A</strong>
		<?php elseif ($score >= 80): ?>
			<strong>B</strong>
		<?php elseif ($score >= 70): ?>
			<strong>C</strong>
		<?php elseif ($score >= 60): ?>
			<strong>D</strong>
		<?php else: ?>
			<strong style="color: red;">F</strong>
		<?php endif ?>
	</body>
</html>
```