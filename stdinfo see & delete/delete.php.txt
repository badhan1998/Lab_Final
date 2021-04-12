<?php
include_once 'database.php';
$result = mysqli_query($conn,"SELECT * FROM stdinfo");
?>

<!DOCTYPE html>
<html>
<head>
<title>Delete student info data</title>
</head>
<body>
<table>
	<tr>
	<td>Student ID</td>
	<td>First Name</td>
	<td>Last Name</td>
	<td>Email</td>
	<td>Action</td>
	</tr>
	<?php
	$i=0;
	while($row = mysqli_fetch_array($result)) {
	?>
	<tr class="<?php if(isset($classname)) echo $classname;?>">
	<td><?php echo $row["userid"]; ?></td>
	<td><?php echo $row["first_name"]; ?></td>
	<td><?php echo $row["last_name"]; ?></td>
	<td><?php echo $row["email"]; ?></td>
	<td><a href="delete-process.php?userid=<?php echo $row["userid"]; ?>">Delete</a></td>
	</tr>
	<?php
	$i++;
	}
	?>
</table>
</body>
</html>