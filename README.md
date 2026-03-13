<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Tulips Organic Care</title>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">

<style>

*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
scroll-behavior:smooth;
}

body{
background:#ffffff;
color:#0a8f3d;
}

/* LOADER */

#loader{
position:fixed;
width:100%;
height:100%;
background:white;
display:flex;
align-items:center;
justify-content:center;
z-index:9999;
}

.loader-circle{
width:50px;
height:50px;
border-radius:50%;
border:6px solid #bdf5c8;
border-top:6px solid #0a8f3d;
animation:spin 1s linear infinite;
}

@keyframes spin{
0%{transform:rotate(0deg)}
100%{transform:rotate(360deg)}
}

/* HEADER */

header{
position:sticky;
top:0;
background:white;
display:flex;
justify-content:space-between;
align-items:center;
padding:15px 40px;
box-shadow:0 3px 12px rgba(10,143,61,0.15);
z-index:1000;
}

.logo{
display:flex;
align-items:center;
gap:10px;
}

.logo img{
width:40px;
}

.logo h1{
font-size:22px;
color:#0a8f3d;
}

nav a{
margin-left:25px;
text-decoration:none;
font-weight:500;
color:#0a8f3d;
}

.cart-icon{
cursor:pointer;
}

/* HERO */

.hero{
height:75vh;
background:linear-gradient(rgba(10,143,61,0.6),rgba(10,143,61,0.6)),
url("https://images.unsplash.com/photo-1615486362493-1bfe9a55012a");
background-size:cover;
background-position:center;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
text-align:center;
color:white;
}

.hero h2{
font-size:42px;
margin-bottom:10px;
}

.hero button{
margin-top:20px;
padding:14px 30px;
background:white;
color:#0a8f3d;
border:none;
border-radius:30px;
font-weight:600;
cursor:pointer;
}

/* BENEFITS */

.benefits{
padding:60px;
display:grid;
grid-template-columns:repeat(auto-fit,minmax(200px,1fr));
gap:30px;
}

.benefit{
background:white;
border-radius:12px;
padding:30px;
text-align:center;
box-shadow:0 4px 14px rgba(10,143,61,0.15);
}

/* PRODUCTS */

.products{
padding:60px;
max-width:1200px;
margin:auto;
display:grid;
grid-template-columns:repeat(auto-fit,minmax(260px,1fr));
gap:30px;
}

.card{
background:white;
border-radius:14px;
overflow:hidden;
box-shadow:0 6px 20px rgba(10,143,61,0.15);
transition:0.3s;
}

.card:hover{
transform:translateY(-6px);
}

.card img{
width:100%;
height:240px;
object-fit:cover;
transition:0.4s;
}

.card:hover img{
transform:scale(1.08);
}

.card-content{
padding:20px;
}

.card-content h3{
margin-bottom:8px;
}

.desc{
font-size:13px;
margin-bottom:10px;
}

.price{
font-size:20px;
font-weight:600;
margin-bottom:10px;
}

.qty{
width:60px;
padding:6px;
margin-bottom:10px;
border:1px solid #0a8f3d;
}

button.add{
background:#0a8f3d;
color:white;
border:none;
padding:10px 16px;
border-radius:6px;
cursor:pointer;
}

/* STAR RATING */

.stars{
display:flex;
gap:4px;
margin-bottom:8px;
}

.stars svg{
width:16px;
fill:#0a8f3d;
}

/* CART DRAWER */

.cart-drawer{
position:fixed;
right:-360px;
top:0;
width:360px;
height:100%;
background:white;
box-shadow:-6px 0 20px rgba(10,143,61,0.2);
padding:25px;
transition:0.4s;
overflow:auto;
z-index:2000;
}

.cart-drawer.active{
right:0;
}

.cart-item{
display:flex;
justify-content:space-between;
margin-bottom:12px;
}

/* REVIEWS */

.reviews{
padding:60px;
background:#eaffef;
text-align:center;
}

.review-grid{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(240px,1fr));
gap:30px;
margin-top:30px;
}

.review{
background:white;
padding:25px;
border-radius:12px;
box-shadow:0 4px 14px rgba(10,143,61,0.15);
}

/* ABOUT */

.about{
padding:70px;
text-align:center;
max-width:900px;
margin:auto;
}

/* FOOTER */

footer{
background:#0a8f3d;
color:white;
padding:40px;
text-align:center;
margin-top:40px;
}

/* FLOAT BUTTONS */

.whatsapp-btn{
position:fixed;
right:20px;
bottom:80px;
background:#0a8f3d;
color:white;
padding:12px 18px;
border-radius:30px;
cursor:pointer;
}

.top-btn{
position:fixed;
right:20px;
bottom:20px;
background:#0a8f3d;
color:white;
padding:10px 16px;
border-radius:30px;
cursor:pointer;
}

/* MOBILE */

@media(max-width:768px){

header{
padding:15px 20px;
}

.hero h2{
font-size:30px;
}

.products{
padding:30px;
}

}

</style>
</head>

<body>

<div id="loader"><div class="loader-circle"></div></div>

<header>

<div class="logo">
<img src="logo.jpg">
<h1>Tulips Organic Care</h1>
</div>

<nav>
<a href="#">Home</a>
<a href="#products">Products</a>
<a href="#reviews">Reviews</a>
<a href="#about">About</a>
</nav>

<div class="cart-icon" onclick="toggleCart()">
<svg width="28" viewBox="0 0 24 24" fill="#0a8f3d">
<path d="M7 4h-2l-1 2v2h2l3.6 7.59-1.35 2.45c-.16.28-.25.61-.25.96
0 1.1.9 2 2 2h12v-2h-11.42c-.14 0-.25-.11-.25-.25
0-.04.01-.08.03-.11l.9-1.64h7.45
c.75 0 1.41-.41 1.75-1.03l3.58-6.49
-1.74-1-3.58 6.49h-8.33l-3-6h14v-2h-16z"/>
</svg>
</div>

</header>

<section class="hero">

<h2>Natural Hair Care Products</h2>
<p>Healthy Hair Starts With Tulips Organic Care</p>

<button onclick="document.getElementById('products').scrollIntoView()">Shop Now</button>

</section>

<section class="benefits">

<div class="benefit">100% Organic Products</div>
<div class="benefit">No Chemicals</div>
<div class="benefit">Hair Growth Support</div>
<div class="benefit">Made in Pakistan</div>

</section>

<section id="products" class="products"></section>

<div class="cart-drawer" id="cartDrawer">

<h2>Your Cart</h2>

<div id="cartItems"></div>

<h3>Total: Rs <span id="total">0</span></h3>

<input type="text" id="name" placeholder="Your Name">
<input type="text" id="address" placeholder="Address">

<button class="add" onclick="sendOrder()">Order on WhatsApp</button>

</div>

<section id="reviews" class="reviews">

<h2>Customer Reviews</h2>

<div class="review-grid">

<div class="review">
<div class="stars">
<svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21 16.54 13.97 22 9.24 14.81
8.63 12 2 9.19 8.63 2 9.24 7.46 13.97 5.82 21z"/></svg>
</div>
<p>Excellent natural shampoo. Hair feels stronger and healthier.</p>
</div>

<div class="review">
<div class="stars">
<svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21 16.54 13.97 22 9.24 14.81
8.63 12 2 9.19 8.63 2 9.24 7.46 13.97 5.82 21z"/></svg>
</div>
<p>The oil has improved hair thickness noticeably.</p>
</div>

<div class="review">
<div class="stars">
<svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21 16.54 13.97 22 9.24 14.81
8.63 12 2 9.19 8.63 2 9.24 7.46 13.97 5.82 21z"/></svg>
</div>
<p>Natural soaps with excellent fragrance and quality.</p>
</div>

</div>

</section>

<section id="about" class="about">

<h2>About Tulips Organic Care</h2>

<p>
Tulips Organic Care is a Pakistani brand focused on creating natural
hair and skincare products using herbal ingredients. Our goal is to
provide pure organic solutions for healthier hair and skin.
</p>

</section>

<footer>

<p>Tulips Organic Care</p>

</footer>

<div class="whatsapp-btn" onclick="window.open('https://wa.me/923338232104')">WhatsApp</div>
<div class="top-btn" onclick="window.scrollTo({top:0,behavior:'smooth'})">Top</div>

<script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>

<script>

AOS.init()

window.onload=()=>{document.getElementById("loader").style.display="none"}

let products=[
{name:"Tulips Amla Shampoo",price:800,img:"shampoo.jpeg"},
{name:"Tulips Hair Growth Oil",price:1000,img:"oil.jpeg"},
{name:"Coffee Soap",price:350,img:"coffe.jpg"},
{name:"Saffron Soap",price:350,img:"saffornn.jpg"},
{name:"Marigold Soap",price:450,img:"marigold.jpg"},
{name:"Ubtan Soap",price:350,img:"ubtan.jpg"}
]

let cart=[]

const container=document.getElementById("products")

products.forEach((p,i)=>{

container.innerHTML+=`

<div class="card">

<img src="${p.img}">

<div class="card-content">

<h3>${p.name}</h3>

<div class="stars">
<svg viewBox="0 0 24 24"><path d="M12 17.27L18.18 21 16.54 13.97 22 9.24 14.81
8.63 12 2 9.19 8.63 2 9.24 7.46 13.97 5.82 21z"/></svg>
</div>

<p class="desc">Organic herbal formula for healthy hair and skin.</p>

<div class="price">Rs ${p.price}</div>

<input type="number" id="q${i}" value="1" min="1" class="qty">

<br>

<button class="add" onclick="addToCart('${p.name}',${p.price},'q${i}')">Add to Cart</button>

</div>

</div>

`

})

function addToCart(name,price,qtyId){

let qty=parseInt(document.getElementById(qtyId).value)

cart.push({name,price,qty})

renderCart()

}

function renderCart(){

let items=document.getElementById("cartItems")

items.innerHTML=""

let total=0

cart.forEach((item,i)=>{

total+=item.price*item.qty

items.innerHTML+=`

<div class="cart-item">

<span>${item.name} x ${item.qty}</span>

<button onclick="removeItem(${i})">Remove</button>

</div>

`

})

document.getElementById("total").innerText=total

}

function removeItem(i){

cart.splice(i,1)

renderCart()

}

function toggleCart(){

document.getElementById("cartDrawer").classList.toggle("active")

}

function sendOrder(){

let name=document.getElementById("name").value
let address=document.getElementById("address").value

let message="Order Details:%0A"

let total=0

cart.forEach(item=>{

message+=item.name+" x "+item.qty+" = Rs "+(item.price*item.qty)+"%0A"
total+=item.price*item.qty

})

message+="Total: Rs "+total+"%0A"
message+="Name: "+name+"%0A"
message+="Address: "+address

window.open("https://wa.me/923338232104?text="+message)

}

</script>

</body>
</html>
