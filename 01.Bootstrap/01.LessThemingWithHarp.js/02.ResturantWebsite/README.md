Building a Restaurant Website

-----------------------------------------------------------------------------------------------------------------------------------------------
version 0.0: 

1.Starting with Boilerplate

2.Update "_data.json"
{
	"index": {
	"pageTitle": "Home"
	},
	"menu": {
	"pageTitle": "Menu"
	},
	"about": {
	"pageTitle": "About"
	},
	"contact": {
	"pageTitle": "Contact"
	}
}

3.Expanding the layout-"_layout.ejs".

3.1.Adding Google Web Fonts.
	3.1.1.Import this line of code to the <head> tag of "_layout.ejs".

<link href='//fonts.googleapis.com/css?family=Raleway:400,300,700,900' rel='stylesheet' type='text/css'>

	3.1.2.Pop open the "_variables.less" in "Typography" section.

@body-copy: "Raleway", "Helvetica Neue", helvetica, arial, verdana, sans-serif;
@heading-copy: "Raleway", "Helvetica Neue", helvetica, arial, verdana, sans-serif;

3.2.Updating the Less variables.

	3.2.1.Backgrounds

// background colors
@primary-background: @off-white;
@secondary-background: @white;

	3.2.2.Links

// link colors
@primary-link-color: @red1;
@primary-link-color-hover: @red2;

4.Updating the header- Open up "_header.ejs".

<div class="header">
	<div class="container">
		<div class="row">
			<div class="col-lg-3">
			<h1>Public</h1>
			</div>

			<div class="col-lg-9 right">
				<div class="main-nav pull-right">
					<ul class="list-inline">

					<li><a href="index.html">Home</a></li>
					<li class="divider">/</li>
					<li><a href="menu.html">Menu</a></li>
					<li class="divider">/</li>
					<li><a href="about.html">About</a></li>
					<li class="divider">/</li>
					<li><a href="contact.html">Contact</a></li>
					<li><button type="button" class="btn btn-default" data-toggle="modal" data-target="#reservation-
					modal">Reservations</button></li>

					</ul>
				</div>
			</div>
		</div>
	</div>
</div>

4.1.Let's update "theme.less":

.header {
	padding: (@padding * 4) 0;
}

.header .container {
	background: @primary-background;
	padding-left: 0;
	padding-right: 0;
}


5.Setting up the page title.

5.1.Open a new file and save it to the css/ components folder with the filename as "_typography.less".

h1 {
	font-weight: 900;
	height: 36px;
	margin: 0;
	line-height: 1;
}

5.2.Import "_ typography.less" back into "theme.less".

@import "components/_typography.less";

6.Setting up the navigation- Let's update "theme.less".

.main-nav {
	line-height: 36px; // vertical center with logo
}

.main-nav ul {
	margin-bottom: 0;
}

.main-nav li.divider {
	color: @grey;
}

.main-nav a {
	text-decoration: none;
}

.main-nav a:hover {
	border-bottom: (@border-size * 5) @border-type @grey;
	transition: border-color 0.2s ease;
}

7.Setting up the reservations modal- Open up "index.ejs" insert the modal code at the botton:

<!-- reservation modal //-->
<div class="modal fade" id="reservation-modal">
	<div class="modal-dialog">
		<div class="modal-content">
			<div class="modal-header">
				<button type="button" class="close" data-dismiss="modal"
				aria-label="Close"><span aria-
				hidden="true">&times;</span></button>
				<h4 class="modal-title">Book Reservation</h4>
			</div>

			<div class="modal-body">
				<form>
					<div class="form-group">
						<label>Name</label>
						<input type="text" class="form-control" placeholder="Enter your name">
					</div>

					<div class="form-group">
						<label>Date</label>
						<input type="text" class="form-control" placeholder="Enter your date">
					</div>

					<div class="form-group">
						<label>Guests</label>
						<input type="text" class="form-control" placeholder="Enter the number of guests">
					</div>
				</form>
			</div>

			<div class="modal-footer">
				<button type="button" class="btn btn-default" data-dismiss="modal">Close</button>
				<button type="button" class="btn btn-primary">Submit</button>
			</div>
		</div><!-- /.modal-content -->
	</div><!-- /.modal-dialog -->
</div><!-- /.modal -->

6.Setting up the footer
6.1.Open up "_footer.ejs".

<div class="footer">
	<div class="container">
		<div class="col-lg-12">
			<h1>Public</h1>
			<p>1234 Street Name / Vancouver, BC / 604.123.1234</p>
			<p>Hours: Open 12pm to 9pm 7 days a week</p>

			<div class="social-media">
				<a href="#"><i class="fa fa-facebook"></i></a>
				<a href="#"><i class="fa fa-twitter"></i></a>
				<a href="#"><i class="fa fa-pinterest"></i></a>
				<a href="#"><i class="fa fa-instagram"></i></a>
			</div>

			<p>&copy; 2015 Public Restaurant</p>
		</div>
	</div>
</div>

6.2.Let's update "theme.less".
.footer {
	text-align: center;
	color: @inverse-text;
	padding-bottom: (@padding * 4);
}

.footer .container {
	background: @inverse-background;
	padding: (@padding * 4) 0;
}

// add padding around social media links
.social-media {
	padding: @padding 0;
}

// space out social media icons and change link color
.social-media a {
	padding: 0 (@padding - 0.5);
	color: @white;
}

// hover link color for social media icons
.social-media a:hover {
	color: @grey;
}

------------------------------------------------------------------------------------------------------------------------------------------------
version 0.1

1.Home page- In the next step, we'll work on customizing index.ejs.
