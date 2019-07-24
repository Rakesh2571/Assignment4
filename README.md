<?php
include dbconnect.php;
?>
<!DOCTYPE html>
<html>
	<head>
			<title>Registration</title>
			<link rel="Stylesheet" type="text/css" href="css/style.css">
	</head>
	<body>
		<header>
		<ul>
			<li><a href="index.html">Home</a></li>
		</ul>
		<div class="logo">
					<img src="logo.png">
			<form action="insertsection.php" method="POST">
				<table class="title">
					<tr>
					<td><h1>User Registration</h1></td>
					</tr>
					<tr>
						<td>Seller's Name:</td>
						<td><input type="text" name=sellername required></td>
					</tr>
					<tr>
						<td>Address:</td>
						<td><input type="text" name=Address required></td>
					</tr>
					<tr>
						<td>City:</td>
						<td>
							<input type="text" name=City required>
						</td>
					</tr>
					<tr>
						<td>Phone number:</td>
						<td>
							<input type="tel" id="phone" name="phone" pattern=[0-9]{3}-[0-9]{3}-[0-9]{4}  required>
							<small>eg:123-456-7891</small>
						</td>
					</tr>
					<tr>
						<td>Email</td>
						<td>
							<input type="email" name=Email pattern="[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"  required>
						</td>
					</tr>
					<tr>
						<td>Year</td>
						<td>
							<input type="text" name=Year pattern=[0-9]{4} title="Please enter valid year details" required>
						</td>
					</tr>
					<tr>
						<td>Make</td>
						<td>
							<input type="text" name=Make title="Please enter valid Make details" required>
						</td>
					</tr>
					<tr>
						<td>Model</td>
						<td>
							<input type="text" name=Model title="Please enter valid Model details" required>
						</td>
					</tr>
					<tr>
						<td>
							<input type="submit">
						</td>
					</tr>
				</table>
			</form>
		</header>
	</body>
</html>
