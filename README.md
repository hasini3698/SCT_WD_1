# SCT_WD_1
Responsive Landing Page
Create an interactive navigation menu that changes color or style when scrolled or when hovering over a menu item
<!DOCTYPE html>
<html>
<head>
    <title>JS Only Navbar</title>
</head>
<body>

<nav id="navbar">
    <ul id="menu">
        <li>Home</li>
        <li>About</li>
        <li>Services</li>
        <li>Contact</li>
    </ul>
</nav>

<section style="height:1000px; padding-top:100px;">
    <h1>Scroll Down</h1>
</section>

<script>

const navbar = document.getElementById("navbar");
const menu = document.getElementById("menu");
const items = menu.getElementsByTagName("li");

document.body.style.margin = "0";

navbar.style.position = "fixed";
navbar.style.top = "0";
navbar.style.width = "100%";
navbar.style.padding = "15px 0";
navbar.style.transition = "0.3s ease";
navbar.style.backgroundColor = "transparent";

menu.style.display = "flex";
menu.style.justifyContent = "center";
menu.style.listStyle = "none";
menu.style.margin = "0";
menu.style.padding = "0";

for (let i = 0; i < items.length; i++) {
    items[i].style.margin = "0 20px";
    items[i].style.cursor = "pointer";
    items[i].style.fontSize = "18px";
    items[i].style.color = "black";
    items[i].style.transition = "0.3s";

    items[i].addEventListener("mouseover", function() {
        this.style.color = "white";
        this.style.backgroundColor = "#007BFF";
        this.style.padding = "8px 12px";
        this.style.borderRadius = "5px";
    });

    items[i].addEventListener("mouseout", function() {
        this.style.color = "black";
        this.style.backgroundColor = "transparent";
    });
}

window.addEventListener("scroll", function() {
    if (window.scrollY > 50) {
        navbar.style.backgroundColor = "#222";
        navbar.style.boxShadow = "0 4px 8px rgba(0,0,0,0.3)";
       
        for (let i = 0; i < items.length; i++) {
            items[i].style.color = "white";
        }
    } else {
        navbar.style.backgroundColor = "transparent";
        navbar.style.boxShadow = "none";
        
        for (let i = 0; i < items.length; i++) {
            items[i].style.color = "black";
        }
    }
});

</script>

</body>
</html>

