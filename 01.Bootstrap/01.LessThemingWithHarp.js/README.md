01.Harp.js Boilerplate

Harp.js – the static web server with built-in preprocessing

The title says it all, and it is taken from the official http://harpjs.com/ website. Harp is an open source project from some of the same people who brought us PhoneGap, and it is my tool of choice for any static website project I work on.

Why is Harp so great? Here are just a few reasons:

	•It includes automatic preprocessing of languages such as EJS, Jade, Markdown, CoffeeScript, Less, Sass, and Stylus.

	•Harp converts the aforementioned languages into vanilla HTML, CSS, and JavaScript and feeds it to the browser.

	•It allows powerful templating through the use of common layouts and partials or includes for PHP people.

	•It includes a lightweight web server that compiles your code in the background for quick and easy testing.

	•It passes in custom metadata through JSON to save your time.

	•It compiles all of your code into production-friendly files that you can deploy on your server.



02.Resturant Website

-----------------------------------------------------------------------------------------------------------------------------------------------
version 0.0- Create header and footer: 

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

3.2.Updating the "_variables.less".

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
			<p>1234 Bulgaria / Pernik / jk. "Tvardi Livadi"</p>
			<p>Designer: Georgi Dikov Georgiev</p>

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
version 0.1- Create Home page. In the next step, we'll work on customizing "index.ejs". The home page for the restaurant website will be split into four main parts:

1.Adding the primary header image.

1.1.Let's update "index.ejs".

<div class="public-banner">
	<div class="row">
		<div class="col-lg-12">
			<img src="img/banner.jpg" width="1170" height="500" alt="Public Restaurant Banner">
		</div>
	</div>
</div>

1.2.Let's update "theme.less".

// here - allows image to go right to the edge
.public-banner .col-lg-12 {
	padding-left: 0;
	padding-right: 0;
}

.public-banner img {
	width: 100%;
	height: auto;
}

1.3.Insert the actual image into our "layout.ejs".

<img src="img/banner.jpg" width="1170" height="500" alt="Public Restaurant Banner">

2.An "about the restaurant" statement.

2.1.Let's update "index.ejs".

<div class="home-about">
	<div class="row">
		<div class="col-lg-12">
			<div class="text-center">
				<h2>About</h2>
				<div class="row">
					<!-- I'd like the width of the text column to be half the width of the layout, so I'll use
					the .col-lg-6 grid class. To center the text column in the layout, I'll use the offset
					class .col-lg-offset-3 . Using the offset class, I can now center my paragraph
					in the layout.-->
					<div class="col-lg-6 col-lg-offset-3">
					<h4>Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis 						egestas.</h4>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

2.2.Let's update "theme.less".

// add some padding around the about headline
.home-about {
	padding: (@padding * 4) 0 (@padding * 6) 0;
}

3.A few food thumbnails that will link to our menu page.

3.1.Let's update "index.ejs".

<div class="home-food">
	<div class="row">
		<div class="col-lg-3">
			<a href="menu.html">
				<img src="img/food-feature1.jpg" height="250" alt="Food Feature
			</a>
			<h4>Sandwich</h4>
		</div>

		<div class="col-lg-3">
			<a href="menu.html">
				<img src="img/food-feature2.jpg" height="250" alt="Food Feature
			</a>
			<h4>Dessert</h4>
		</div>

		<div class="col-lg-3">
			<a href="menu.html">
				<img src="img/food-feature3.jpg" height="250" alt="Food Feature
			</a>
			<h4>Salad</h4>
		</div>

		<div class="col-lg-3">
			<a href="menu.html">
				<img src="img/food-feature4.jpg" height="250" alt="Food Feature
			</a>
			<h4>Coffee</h4>
		</div>
	</div>
</div>

3.2.Let's update "theme.less".

// center all items
.home-food {
	text-align: center;
}

// add a little extra padding under images
.home-food img {
	padding-bottom: @padding;
}

4.A Bootstrap reviews carousel.

4.1.Let's update "index.ejs".

<div class="reviews">
<div class="row">
<div class="col-lg-12">
<div class="text-center">
<h2>Reviews</h2>
<div id="carousel-reviews" class="carousel slide" data-
ride="carousel">
<!-- Indicators -->
<ol class="carousel-indicators">
<li data-target="#carousel-reviews" data-slide-
to="0" class="active"></li>
<li data-target="#carousel-reviews" data-slide-
to="1"></li>
<li data-target="#carousel-reviews" data-slide-
to="2"></li>
</ol>
<!-- Wrapper for slides -->
<div class="carousel-inner" role="listbox">
<div class="item active">
<p>This is the best sandwich I've ever had! I
Highly recommend trying the chicken sandwich
for lunch.</p>
</div>
<div class="item">
<p>The desserts are to die for. Make sure you
save enough room after you eat your dinner.</p>
</div>
<div class="item">
<p>They have some of the best locally brewed
coffee I have ever tasted. So fresh and eye
opening early in the morning.</p>
</div>
</div>
<!-- Controls -->
<a class="left carousel-control" href="#carousel-
reviews" role="button" data-slide="prev">
<span class="glyphicon glyphicon-chevron-left"
aria-hidden="true"></span>
<span class="sr-only">Previous</span>
</a>
<a class="right carousel-control" href="#carousel-
reviews" role="button" data-slide="next">
<span class="glyphicon glyphicon-chevron-right"
aria-hidden="true"></span>
<span class="sr-only">Next</span>
</a>
</div>
</div>
</div>
</div>
</div>

4.2.Let's update "theme.less".

// add review padding consistent with about
.reviews {
	padding: (@padding * 4) 0 (@padding * 6) 0;
}

4.3.Create a new Less file called "_carousel.less" and save it in the "css / components" directory.


