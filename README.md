<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Invitación de Boda - Abril & Pablo</title>
<style>
  body, html {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(to bottom, #cce7ff, #1a3b6f);
    overflow-x: hidden;
    color: #fff;
  }

  /* Sección inicio */
  #inicio {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    position: relative;
    overflow: hidden;
    background: radial-gradient(circle, rgba(0,0,0,0.1), transparent 70%);
  }

  /* Partículas */
  .particle {
    position: absolute;
    border-radius: 50%;
    background: rgba(255,255,255,0.6);
    pointer-events: none;
    animation: float linear infinite;
    box-shadow: 0 0 5px #fff, 0 0 10px #aaddff;
  }
  @keyframes float {
    0% {transform: translateY(0px);}
    100% {transform: translateY(-1200px);}
  }

  /* Anillo animado */
  #anillo {
    width: 140px;
    height: 140px;
    border: 5px solid #fff;
    border-radius: 50%;
    position: relative;
    animation: girar 6s linear infinite, brillo 2s ease-in-out infinite alternate;
    cursor: pointer;
    box-shadow: 0 0 20px #fff, 0 0 40px #aaddff, 0 0 60px rgba(173,216,230,0.5);
    transition: transform 0.8s ease, opacity 0.8s ease;
  }
  @keyframes girar {from {transform: rotate(0deg);} to {transform: rotate(360deg);}}
  @keyframes brillo {
    from {box-shadow: 0 0 20px #fff, 0 0 40px #aaddff, 0 0 60px rgba(173,216,230,0.5);}
    to {box-shadow: 0 0 30px #fff, 0 0 50px #aaddff, 0 0 70px rgba(173,216,230,0.6);}
  }

  /* Secciones */
  section {
    padding: 60px 20px;
    text-align: center;
    opacity: 0;
    transform: translateY(30px);
    transition: all 1s ease;
  }
  section.visible {
    opacity: 1;
    transform: translateY(0);
  }

  h1,h2,h3,p { margin: 10px 0; }

  /* Fotos */
  .fotos {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
  }
  .fotos img {
    width: 250px;
    height: auto;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(255,255,255,0.5);
    transition: transform 0.5s;
  }
  .fotos img:hover { transform: scale(1.05); }

  /* Contador */
  #contador { font-size: 2rem; margin-top: 20px; letter-spacing: 1px; }

  /* WhatsApp */
  .whatsapp-buttons { display: flex; justify-content: center; gap: 20px; margin-top: 30px; }
  .whatsapp-buttons a {
    display: inline-block; background-color: #25D366; color: #fff; padding: 12px 20px;
    border-radius: 50px; text-decoration: none; font-weight: bold;
    box-shadow: 0 0 10px #25D366, 0 0 20px rgba(37,211,102,0.5);
    transition: transform 0.3s, box-shadow 0.3s;
  }
  .whatsapp-buttons a:hover { transform: scale(1.1); box-shadow: 0 0 15px #25D366, 0 0 30px rgba(37,211,102,0.7); }

  textarea {
    width: 80%; max-width: 600px; padding: 12px; border-radius: 12px;
    border: none; resize: none; font-size: 1rem;
  }

  /* Animación apertura tipo caja */
  .open {
    animation: abrirCaja 1s forwards;
  }
  @keyframes abrirCaja {
    0% { transform: scale(1) rotate(0deg); opacity:1; }
    50% { transform: scale(1.3) rotate(45deg); opacity:0.7; }
    100% { transform: scale(2) rotate(90deg); opacity:0; }
  }

</style>
</head>
<body>

<!-- Inicio -->
<section id="inicio">
  <div id="anillo" title="Haz clic para abrir la invitación"></div>
</section>

<!-- Datos Novios -->
<section id="novios">
  <h1>Abril Pérez Aguilar & Pablo Eliel Tinoco Hernández</h1>
  <h3>Padres de la novia: Eva Aguilar Rendón & Pedro Pérez Hernández</h3>
  <h3>Padres del novio: Saray Hernández Santana & Pablo Tinoco Carranza (finado)</h3>
  <p style="font-style: italic; font-size:1.2rem;">“Por tanto, lo que Dios ha unido, que no lo separe el hombre.” - Mateo 19:6</p>
</section>

<!-- Ceremonia -->
<section id="ceremonia">
  <h2>Ceremonia Religiosa</h2>
  <p>Jardín El Abuelo, Tlaquiltenango - 2:00 pm</p>
  <h2>Recepción</h2>
  <p>Jardín El Abuelo, Tlaquiltenango - 4:00 pm</p>
  <iframe src="https://www.bing.com/maps/embed?h=400&w=600&cp=18.8825~-99.2035&lvl=16&typ=d&sty=r&src=SHELL&FORM=MBEDV8" 
    width="600" height="400" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
</section>

<!-- Fotos -->
<section id="momentos">
  <h2>Nuestros hermosos momentos</h2>
  <p>“Tu amor es lo que he anhelado y el regalo que Dios me ha dado”</p>
  <div class="fotos">
    <img src="foto1.jpg" alt="Foto 1">
    <img src="foto2.jpg" alt="Foto 2">
    <img src="foto3.jpg" alt="Foto 3">
  </div>
</section>

<!-- Contador -->
<section id="contador-section">
  <h2>Faltan:</h2>
  <div id="contador"></div>
</section>

<!-- Comentarios y WhatsApp -->
<section id="contacto">
  <h2>Deja tus buenos deseos</h2>
  <textarea placeholder="Escribe tu mensaje..." rows="4" cols="50"></textarea>
  <div class="whatsapp-buttons">
    <a href="https://wa.me/527774914500" target="_blank">💬 Abril</a>
    <a href="https://wa.me/527341123645" target="_blank">💬 Pablo</a>
  </div>
</section>

<audio id="musica" loop>
  <source src="EternamenteEnamorados.mp3" type="audio/mpeg">
</audio>

<script>
  // Partículas explosivas
  for(let i=0;i<70;i++){
    let p = document.createElement('div');
    p.className='particle';
    p.style.width=p.style.height=Math.random()*6+3+'px';
    p.style.left=Math.random()*100+'%';
    p.style.animationDuration=(10+Math.random()*15)+'s';
    p.style.opacity=Math.random()*0.8+0.2;
    document.getElementById('inicio').appendChild(p);
  }

  const anillo=document.getElementById('anillo');
  const secciones=document.querySelectorAll('section:not(#inicio)');
  const musica=document.getElementById('musica');

  function abrirInvitacion(){
    // Animación caja
    anillo.classList.add('open');
    setTimeout(()=>{
      anillo.style.display='none';
      secciones.forEach(sec=>sec.classList.add('visible'));
      musica.play();
    },1000);
  }

  anillo.addEventListener('click',abrirInvitacion);
  setTimeout(abrirInvitacion,3000);

  // Contador
  const contador=document.getElementById('contador');
  const fechaBoda=new Date('December 28, 2025 14:00:00').getTime();
  setInterval(()=>{
    const ahora=new Date().getTime();
    const distancia=fechaBoda-ahora;
    const dias=Math.floor(distancia/(1000*60*60*24));
    const horas=Math.floor((distancia%(1000*60*60*24))/(1000*60*60));
    const minutos=Math.floor((distancia%(1000*60*60))/(1000*60));
    const segundos=Math.floor((distancia%(1000*60))/1000);
    contador.innerHTML=`${dias} días ${horas}h ${minutos}m ${segundos}s`;
  },1000);
</script>
</body>
</html>
[eternamente.mp3](https://github.com/user-attachments/files/22691184/eternamente.mp3)
![ring](https://github.com/user-attachments/assets/8ac80db3-2b5b-41eb-8138-52f819642b52)
![photo3](https://github.com/user-attachments/assets/64aab07b-3970-4e04-b761-cad1c6628362)
![photo2](https://github.com/user-attachments/assets/ae927fd2-d6c6-47a8-a567-5de0ed9a7131)
![photo1](https://github.com/user-attachments/assets/9d3c3e4d-746e-47b3-a7a2-1be72bbc25ee)
![momento3](https://github.com/user-attachments/assets/f4446ef3-fe30-4edd-a737-2a756bb46c40)
![momento2](https://github.com/user-attachments/assets/c7ebe05f-c1d7-4b9a-baf9-b64d5eae5990)
![momento1](https://github.com/user-attachments/assets/c40ca973-5da0-45dc-a7cf-4a1f8f1f6c48)
<img width="1200" height="1200" alt="flower3" src="https://github.com/user-attachments/assets/e961ce4f-5dcf-40ea-b4dd-661f318731ba" />
![flower2](https://github.com/user-attachments/assets/bf3d2360-210f-40d8-813e-f63cbc1f8da2)
![flower1](https://github.com/user-attachments/assets/37008d08-505f-4c6a-82f7-4950cf59750b)
 
