<template>
<div class="wrapper">
        <!-- Sidebar  -->
        <nav id="sidebar">
            <div class="sidebar-header">
                <h4>IconBuy</h4>
            </div>

            <ul class="list-unstyled components">
                <p>STYLE</p>
                <li>
                    <a href="#">Line</a>
                </li>
                <li>
                    <a href="#">Line Color</a>
                </li>
                <li>
                    <a href="#">Solid</a>
                </li>
                <li>
                    <a href="#">Solid Color</a>
                </li>
                <li>
                    <a href="#">Multi Color</a>
                </li>
            </ul>

            <ul class="list-unstyled CTAs">
                <p>Size</p>
                <li>
                  <div class="radio">
                    <input label="16" type="radio" id="male" name="gender" value="16" checked @change="sizeChange($event)">
                    <input label="24" type="radio" id="female" name="gender" value="24" @change="sizeChange($event)">
                    <input label="32" type="radio" id="other" name="gender" value="32" @change="sizeChange($event)">
                    <input label="48" type="radio" id="other" name="gender" value="48" @change="sizeChange($event)">
                    <input label="64" type="radio" id="other" name="gender" value="64" @change="sizeChange($event)">
                    <input label="96" type="radio" id="other" name="gender" value="96" @change="sizeChange($event)">
                  </div>
                </li>
                <p>Stroke</p>
                <li>
                  <div class="radio">
                    <input label="0.5" type="radio" id="male" name="stroke" value="0.5" checked @change="strokeChange($event)">
                    <input label="1" type="radio" id="female" name="stroke" value="1" @change="strokeChange($event)">
                    <input label="1.5" type="radio" id="other" name="stroke" value="1.5" @change="strokeChange($event)">
                    <input label="2" type="radio" id="other" name="stroke" value="2" @change="strokeChange($event)">
                    <input label="2.5" type="radio" id="other" name="stroke" value="2.5" @change="strokeChange($event)">
                    <input label="3" type="radio" id="other" name="stroke" value="3" @change="strokeChange($event)">
                  </div>
                </li>
                <p>Colors</p>
                <li>
                  <div id="cp2" class="input-group" title="Using input value">
                    <input type="text" class="form-control input-lg" value="#DD0F20FF"/>
                    <span class="input-group-append">
                      <span class="input-group-text colorpicker-input-addon"><i></i></span>
                    </span>
                  </div>
                </li>
                <br>
                <li>
                  <div id="cp2" class="input-group" title="Using input value">
                    <input type="text" class="form-control input-lg" value="#DD0F20FF"/>
                    <span class="input-group-append">
                      <span class="input-group-text colorpicker-input-addon"><i></i></span>
                    </span>
                  </div>
                </li>
                <br>
                <li>
                  <div id="cp2" class="input-group" title="Using input value">
                    <input type="text" class="form-control input-lg" value="#DD0F20FF"/>
                    <span class="input-group-append">
                      <span class="input-group-text colorpicker-input-addon"><i></i></span>
                    </span>
                  </div>
                </li>
                <!-- <li>
                    <a href="https://bootstrapious.com/tutorial/files/sidebar.zip" class="download">Download source</a>
                </li>
                <li>
                    <a href="https://bootstrapious.com/p/bootstrap-sidebar" class="article">Back to article</a>
                </li> -->
            </ul>
        </nav>

        <!-- Page Content  -->
        <div id="content">

            <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <div class="container-fluid">

                    <div class="collapse navbar-collapse" id="navbarSupportedContent">
                        <ul class="nav navbar-nav ml-auto">
                            <li class="nav-item active">
                                <a class="nav-link" href="#">Page</a>
                            </li>
                            <li class="nav-item">
                                <a class="nav-link" href="#">Page</a>
                            </li>
                            <li class="nav-item">
                                <a class="nav-link" href="#">Page</a>
                            </li>
                            <li class="nav-item">
                                <a class="nav-link" href="#">Page</a>
                            </li>
                        </ul>
                    </div>
                </div>
            </nav>

            <div class="row">
              <div class="col">
                 <select class="form-control" id="exampleFormControlSelect1" v-model="kategori">
                     <option value="all">All</option>
                    <option value="1">1</option>
                    <option value="2">2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                  </select>
              </div>
              <div class="col">
                <input type="text" class="form-control" placeholder="Cari" v-model="cari">
              </div>
            </div>

            <br>
            <div class="row">
                <ul class="row row-cols-3 row-cols-sm-12 row-cols-lg-6 row-cols-xl-8 list-unstyled list">
                    <li class="col mb-1" data-tags="numbers" data-categories="typography" v-for="item in filterImage" :key="item.id">
                        <a class="d-block text-dark text-decoration-none" href="#">
                         <div class="p-3 py-4 mb-2 bg-light text-center rounded">
                             <!-- <svg class="bi" width="1em" height="1em" fill="currentColor">
                        <use xlink:href="" />
                        </svg> -->
                        {{ item.filename }}
                        </div>
                        
                        <div class="name text-muted text-decoration-none text-center pt-1">{{ item.name }} {{ item.kategori }}</div>
                    </a></li>
                </ul>
            </div>

          </div>
    </div>
</template>

<script>
import Axios from 'axios'
export default {
   name: 'Home',
   data () {
        return {
            cari: "",
            images: [],
            kategori: ""
        }
    },
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
      
      // $('#cp2, #cp3a, #cp3b').colorpicker();
    },
    mounted() {
        Axios.get('https://sicons.herokuapp.com/image')
            .then((response) => (this.images = response.data))
    },
    computed: {
        filterImage() {
            return this.images.filter((item) => {
                return item.name.toLowerCase().includes(this.cari.toLowerCase())
            })

            // if(this.kategori === ''){
            //     return this.images;
            // } else {
            //     const category = this.kategori;
            //     return this.images.filter((gambar) => gambar.attributes === category)
            // }
        },
        
    }
}
</script>

<style>
@import "https://fonts.googleapis.com/css?family=Poppins:300,400,500,600,700";
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

/* template */
body {
    font-family: 'Poppins', sans-serif;
    background: #fafafa;
}

p {
    font-family: 'Poppins', sans-serif;
    font-size: 1.1em;
    font-weight: 300;
    line-height: 1.7em;
    color: #999;
}

a,
a:hover,
a:focus {
    color: inherit;
    text-decoration: none;
    transition: all 0.3s;
}

.navbar {
    padding: 15px 10px;
    background: #fff;
    border: none;
    border-radius: 0;
    margin-bottom: 40px;
    box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
}

.navbar-btn {
    box-shadow: none;
    outline: none !important;
    border: none;
}

.line {
    width: 100%;
    height: 1px;
    border-bottom: 1px dashed #ddd;
    margin: 40px 0;
}

/* ---------------------------------------------------
    SIDEBAR STYLE
----------------------------------------------------- */

.wrapper {
    display: flex;
    width: 100%;
    align-items: stretch;
}

#sidebar {
    min-width: 250px;
    max-width: 250px;
    background: #7386D5;
    color: #fff;
    transition: all 0.3s;
}

#sidebar.active {
    margin-left: -250px;
}

#sidebar .sidebar-header {
    padding: 5px;
    background: #6d7fcc;
}

#sidebar ul.components {
    padding: 20px 0;
    border-bottom: 1px solid #47748b;
}

#sidebar ul p {
    color: #fff;
    padding: 5px;
}

#sidebar ul li a {
    padding: 5px;
    font-size: 1.1em;
    display: block;
}

#sidebar ul li a:hover {
    color: #7386D5;
    background: #fff;
}

#sidebar ul li.active>a,
a[aria-expanded="true"] {
    color: #fff;
    background: #6d7fcc;
}

a[data-toggle="collapse"] {
    position: relative;
}

.dropdown-toggle::after {
    display: block;
    position: absolute;
    top: 50%;
    right: 20px;
    transform: translateY(-50%);
}

ul ul a {
    font-size: 0.9em !important;
    padding-left: 30px !important;
    background: #6d7fcc;
}

ul.CTAs {
    padding: 20px;
}

ul.CTAs a {
    text-align: center;
    font-size: 0.9em !important;
    display: block;
    border-radius: 5px;
    margin-bottom: 5px;
}

a.download {
    background: #fff;
    color: #7386D5;
}

a.article,
a.article:hover {
    background: #6d7fcc !important;
    color: #fff !important;
}

/* ---------------------------------------------------
    CONTENT STYLE
----------------------------------------------------- */

#content {
    width: 100%;
    padding: 20px;
    min-height: 100vh;
    transition: all 0.3s;
}

/* ---------------------------------------------------
    MEDIAQUERIES
----------------------------------------------------- */

@media (max-width: 768px) {
    #sidebar {
        margin-left: -250px;
    }
    #sidebar.active {
        margin-left: 0;
    }
    #sidebarCollapse span {
        display: none;
    }
}
</style>