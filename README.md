# Website
Html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cinematic Photo Gallery</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}

body{
    background:#0a0a0a;
    color:white;
}

header{
    text-align:center;
    padding:40px 20px;
    background:linear-gradient(to bottom,#111,#000);
}

header h1{
    font-size:3rem;
    letter-spacing:3px;
}

header p{
    color:#bbb;
    margin-top:10px;
}

.gallery{
    width:90%;
    margin:40px auto;
    display:grid;
    grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
    gap:20px;
}

.gallery img{
    width:100%;
    height:400px;
    object-fit:cover;
    border-radius:15px;
    cursor:pointer;
    transition:.4s;
    box-shadow:0 10px 30px rgba(255,255,255,.08);
}

.gallery img:hover{
    transform:scale(1.04);
    box-shadow:0 15px 40px rgba(255,255,255,.15);
}

/* Lightbox */
.lightbox{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:100%;
    background:rgba(0,0,0,.95);
    display:none;
    justify-content:center;
    align-items:center;
    z-index:999;
}

.lightbox img{
    max-width:90%;
    max-height:90%;
    border-radius:15px;
}

.lightbox.active{
    display:flex;
}
</style>
</head>
<body>

<header>
    <h1>CINEMATIC GALLERY</h1>
    <p>Night Flash Editorial Photography</p>
</header>

<div class="gallery">
    <img src="https://images.unsplash.com/photo-1500648767791-00dcc994a43e" alt="">
    <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330" alt="">
    <img src="https://images.unsplash.com/photo-1506794778202-cad84cf45f1d" alt="">
    <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9" alt="">
    <img src="https://images.unsplash.com/photo-1504593811423-6dd665756598" alt="">
    <img src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1" alt="">
</div>

<div class="lightbox" id="lightbox">
    <img id="lightbox-img">
</div>

<script>
const images = document.querySelectorAll(".gallery img");
const lightbox = document.getElementById("lightbox");
const lightboxImg = document.getElementById("lightbox-img");

images.forEach(img=>{
    img.addEventListener("click",()=>{
        lightbox.classList.add("active");
        lightboxImg.src = img.src;
    });
});

lightbox.addEventListener("click",()=>{
    lightbox.classList.remove("active");
});
</script>

</body>
</html>