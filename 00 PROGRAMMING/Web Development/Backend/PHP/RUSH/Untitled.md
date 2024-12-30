
Navbar styling:
- Active tab
![[Pasted image 20240407173728.png]]




#### What rooms the user can view / what rooms they are a member of
https://www.youtube.com/watch?v=N4PIFGviVJw&list=PL3VM-unCzF8ipG50KDjnzhugceoSG3RTC&index=25&ab_channel=Laracasts
```php
$config = require '../app/model/config.php';
$db = new Rooms($config['database']);

$room_id = $_GET['room_id'];

$query = "select * from rooms where room_id = ?";

  
$rooms = $db->query($query, [
    ':id' => $room_id
])->fetch();

if (! $rooms) {
	abort();
}

$currentUserId = 1;
$forbidden = 403;

if ($rooms['room_id'] !== $currentUserId) {
	abort($forbidden);
}

dd($rooms);
```


>[!tip] `extract()`
> - Turns an `Associative Array` into a __Variable__ using the ___key___ as the __Variable name__ 
> ```php
> $aarray = [ 'header' => 'home']
> 
> extract($aarray);
> echo $header;
> ```

### Deleting "Something" like Rooms
https://youtu.be/Org1A2288XA?list=PL3VM-unCzF8ipG50KDjnzhugceoSG3RTC&t=770


> [!danger] Some things i don't fully understand:
> - https://www.youtube.com/watch?v=xXj1l8nbWpU&list=PL3VM-unCzF8ipG50KDjnzhugceoSG3RTC&index=35&ab_channel=Laracasts
> - 