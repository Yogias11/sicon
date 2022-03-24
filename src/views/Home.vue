<template>
  <!-- <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div> -->
  <body>

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
    <input label="16" type="radio" id="male" name="gender" value="male" checked>
    <input label="24" type="radio" id="female" name="gender" value="female">
    <input label="32" type="radio" id="other" name="gender" value="other">
    <input label="48" type="radio" id="other" name="gender" value="other">
    <input label="64" type="radio" id="other" name="gender" value="other">
    <input label="96" type="radio" id="other" name="gender" value="other">
  </div>

  <h5>Stroke</h5>
  <div class="radio">
    <input label="16" type="radio" id="male" name="stroke" value="male" checked>
    <input label="24" type="radio" id="female" name="stroke" value="female">
    <input label="32" type="radio" id="other" name="stroke" value="other">
    <input label="48" type="radio" id="other" name="stroke" value="other">
    <input label="64" type="radio" id="other" name="stroke" value="other">
    <input label="96" type="radio" id="other" name="stroke" value="other">
  </div>
</div>

<div class="content">
  <h2>Responsive Sidebar Example</h2>
  <p>This example use media queries to transform the sidebar to a top navigation bar when the screen size is 700px or less.</p>
  <p>We have also added a media query for screens that are 400px or less, which will vertically stack and center the navigation links.</p>
  <h3>Resize the browser window to see the effect.</h3>
</div>

</body>
</template>

<script>

export default {
  
}
</script>

<style>
body {
  margin: 0;
  font-family: "Lato", sans-serif;
}

.radio {
	background: #454857;
	padding: 4px;
	border-radius: 3px;
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
	padding: 4px 8px;
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
  padding: 1px 16px;
  height: 1000px;
}

@media screen and (max-width: 700px) {
  .sidebar {
    width: 100%;
    height: auto;
    position: relative;
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
