<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
  <!-- <body> -->

    <div class="topnav" id="myTopnav">
  <a href="#home" class="active">Home</a>
  <a href="#news">News</a>
  <a href="#contact">Contact</a>
  <a href="#about">About</a>
  <a href="javascript:void(0);" class="icon" onclick="myFunction()">
    <i class="fa fa-bars"></i>
  </a>
</div>

<div class="sidebar">
  <h2>IconBuy</h2>
  <h4>TYPE</h4>
  
  <a href="#home">Line</a>
  <a href="#news">Line Color</a>
  <a href="#contact">Solid</a>
  <a href="#about">Solid Color</a>
  <a href="">Multi Color</a>

  <h5>Size</h5>
  <div class="radio">
    <input label="16" type="radio" id="male" name="gender" value="16" checked @change="sizeChange($event)">
    <input label="24" type="radio" id="female" name="gender" value="24" @change="sizeChange($event)">
    <input label="32" type="radio" id="other" name="gender" value="32" @change="sizeChange($event)">
    <input label="48" type="radio" id="other" name="gender" value="48" @change="sizeChange($event)">
    <input label="64" type="radio" id="other" name="gender" value="64" @change="sizeChange($event)">
    <input label="96" type="radio" id="other" name="gender" value="96" @change="sizeChange($event)">
  </div>

  <h5>Stroke</h5>
  <div class="radio">
    <input label="0.5" type="radio" id="male" name="stroke" value="0.5" checked @change="strokeChange($event)">
    <input label="1" type="radio" id="female" name="stroke" value="1" @change="strokeChange($event)">
    <input label="1.5" type="radio" id="other" name="stroke" value="1.5" @change="strokeChange($event)">
    <input label="2" type="radio" id="other" name="stroke" value="2" @change="strokeChange($event)">
    <input label="2.5" type="radio" id="other" name="stroke" value="2.5" @change="strokeChange($event)">
    <input label="3" type="radio" id="other" name="stroke" value="3" @change="strokeChange($event)">
  </div>

  <h5>Colors</h5>

</div>

<div class="content">
  <h2>Test</h2>
  <!-- <h2>Responsive Sidebar Example</h2>
  <p>This example use media queries to transform the sidebar to a top navigation bar when the screen size is 700px or less.</p>
  <p>We have also added a media query for screens that are 400px or less, which will vertically stack and center the navigation links.</p>
  <h3>Resize the browser window to see the effect.</h3> -->
  <div class="row">
    <div class="column" v-for="item in 100" :key="item">
      <img src="../assets/Buy.svg" alt="Nature" style="width:30%" onclick="myFunction(this);">
    </div>
    
  </div>

</div>

<!-- </body> -->
</template>

<script>

export default {
    name: 'Home',
    methods: {
      sizeChange(event) {
        var size = event.target.value;
        console.log(size);
      },
      strokeChange(event) {
        var stroke = event.target.value;
        console.log(stroke);
      },
      myFunction() {
        var x = document.getElementById("myTopnav");
        if (x.className === "topnav") {
          x.className += " responsive";
        } else {
          x.className = "topnav";
        }
      }
    }
}
</script>

<style>
body {
  margin: 0;
  font-family: "Lato", sans-serif;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* The grid: Four equal columns that floats next to each other */
.column {
  float: left;
  margin-left: 5px;
  width: 10%;
  /* padding: 5px; */
}

/* Style the images inside the grid */
.column img {
  opacity: 0.8; 
  cursor: pointer; 
}

.column img:hover {
  opacity: 1;
}

/* The expanding image container */
.container {
  position: relative;
  display: none;
}

.radio {
	background: #454857;
	padding: 3px;
  margin-left: 5px;
  margin-right: 5px;
	border-radius: 2px;
	box-shadow: inset 0 0 0 3px rgba(35, 33, 45, 0.3),
		0 0 0 3px rgba(185, 185, 185, 0.3);
	position: relative;
}

.radio input {
	width: auto;
	height: 100%;
	appearance: none;
	outline: none;
	cursor: pointer;
	border-radius: 2px;
	padding: 2px 4px;
	background: #454857;
	color: #bdbdbdbd;
	font-size: 14px;
	font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
		"Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
		"Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
	transition: all 100ms linear;
}

.radio input:checked {
	background-image: linear-gradient(180deg, #95d891, #74bbad);
	color: #fff;
	box-shadow: 0 1px 1px #0000002e;
	text-shadow: 0 1px 0px #79485f7a;
}

.radio input:before {
	content: attr(label);
	display: inline-block;
	text-align: center;
	width: 100%;
}

.topnav {
  margin-left: 250px;
  overflow: hidden;
  background-color: #333;
}

.topnav a {
  float: left;
  display: block;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: #ddd;
  color: black;
}

.topnav a.active {
  background-color: #04AA6D;
  color: white;
}

.topnav .icon {
  display: none;
}

.sidebar {
  margin: 0;
  padding: 5;
  width: 250px;
  background-color: #f1f1f1;
  position: fixed;
  height: 100%;
  overflow: auto;
}

.sidebar a {
  display: block;
  color: black;
  padding: 16px;
  text-decoration: none;
}
 
.sidebar a.active {
  background-color: #04AA6D;
  color: white;
}

.sidebar a:hover:not(.active) {
  background-color: #555;
  color: white;
}

div.content {
  margin-left: 200px;
  margin-top: 50px;
  padding: 1px 16px;
  height: 1000px;
}

@media screen and (max-width: 700px) {
  .sidebar {
    width: 100%;
    height: auto;
    position: relative;
  }

  .topnav.responsive {position: relative;}
  .topnav.responsive .icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: left;
  }

  .sidebar a {float: left;}
  div.content {margin-left: 0;}
}

@media screen and (max-width: 400px) {
  .sidebar a {
    text-align: center;
    float: none;
  }
}
</style>
