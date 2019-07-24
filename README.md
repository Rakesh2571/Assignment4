<?php
	$servername = "localhost";
	$username = "root";
	$password = "";
	$database = 'classic_autostore';

	// Create a connection

	$connection = mysqli_connect($servername, $username, $password, $database);

// Check the connection

if ($connection->connect_error)
	{
		die("The Connection failed: " . $connection->connect_error);
	}
?>
<!DOCTYPE html>
<html>
	<head>
		<link rel="Stylesheet" type="text/css" href="css/style.css">
	</head>
	<body>
		<header>
		<ul>
			<li><a href="register.html">New</a></li>
		</ul>
		<ul>
			<li><a href="index.html">Home</a></li>
		</ul>
		<div class="logo">
					<img src="logo.png">
				<?php
			$sql = "SELECT * FROM classic_table";
			$res = $connection->query($sql);
		?>
		<ul>
		<table class="title" cellpadding="30">
			<thead>
			<tr><th><h1 align="center" style="color:burlywood">Used Vehicles</h1></th></tr>
				<tr>
					<th><h2>Seller's Name</h2></th>
					<th><h2>Address(mailing)</h2></th>
					<th><h2>City</h2></th>
					<th><h2>Phone Number</h2></th>
					<th><h2>Email Id</h2></th>
					<th><h2>Year</h2></th>
					<th><h2>Make</h2></th>
					<th><h2>Model</h></th>
				</tr>
			</thead>
		
		<tbody>
			<?php
				while($row= $res->fetch_assoc())
					{
						echo "<tr><td>{$row['seller_name']}</td><td>{$row['address']}</td><td>{$row['city']}</td><td>{$row['phone_number']}</td><td>{$row['email']}</td><td>{$row['year']}</td><td>{$row['make']}</td><td>{$row['model']}</td></tr>";
					}
			?>
		</tbody>
	</table>
		</header>
	</body>
</html>
<?php mysqli_close($connection) ?>

	
	

		
