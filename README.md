# invitacion-boda
invitación boda
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Invitación de Boda - Abril & Pablo</title>
<style>
  /* Estilos generales */
  body, html {
    margin: 0;
    padding: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(to bottom, #cce7ff, #1a3b6f);
    overflow-x: hidden;
    color: #fff;
  }

  /* Sección de inicio (anillo animado) */
  #inicio {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    position: relative;
    overflow: hidden;
    background: radial-gradient(circle, rgba(0,0,0,0.1), transparent 70%);
  }

  /* Partículas de luz */
  .particle {
    position: absolute;
    border-radius: 50%;
    background: rgba(255,255,255,0.6);
    pointer-events: none;
    animation: float 15s linear infinite;
  }

  @keyframes float {
    0% {transform: translateY(0px);}
    100% {transform: translateY(-1000px);}
  }

  /* Anillo animado */
  #anillo {
    width: 120px;
    height: 120px;
    border: 5px solid #fff;
    border-radius: 50%;
    position: relative;
    animation: girar 6s linear infinite;
    cursor: pointer;
    box-shadow: 0 0 15px #fff, 0 0 30px #aaddff;
  }

  @keyframes girar {
    from {transform: rotate(0deg);}
    to {transform: rotate(360deg);}
  }

  /* Secciones */
  section {
    padding: 60px 20px;
    text-align: center;
  }

  h1, h2, h3, p {
    margin: 10px 0;
  }

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
    box-shadow: 0 0 15px rgba(255,255,255,0.5);
  }

  /* Contador */
  #contador {
    font-size: 2rem;
    margin-top: 20px;
  }

  /* Botones WhatsApp */
  .whatsapp-buttons {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin-top: 30px;
  }

  .whatsapp-buttons a {
    display: inline-block;
    background-color: #25D366;
    color: #fff;
    padding: 12px 20px;
    border-radius: 50px;
    text-decoration: none;
    font-weight: bold;
    box-shadow: 0 0 10px #25D366;
    transition: transform 0.2s;
  }

  .whatsapp-buttons a:hover {
    transform: scale(1.1);
  }

  /* Animación apertura de invitación */
  .visible { display: block; opacity: 1; transition: opacity 1s; }
  .oculto { display: none; opacity: 0; }
</style>
</head>
<body>

<!-- Sección Inicio -->
<section id="inicio">
  <div id="anillo" title="Haz clic para abrir la invitación"></div>
</section>

<!-- Sección Datos de los Novios y frase bíblica -->
<section id="novios" class="oculto">
  <h1>Abril Pérez Aguilar & Pablo Eliel Tinoco Hernández</h1>
  <h3>Padres de la novia: Eva Aguilar Rendón & Pedro Pérez Hernández</h3>
  <h3>Padres del novio: Saray Hernández Santana & Pablo Tinoco Carranza (finado)</h3>
  <p style="font-style: italic; font-size: 1.2rem;">“Por tanto, lo que Dios ha unido, que no lo separe el hombre.” - Mateo 19:6</p>
</section>

<!-- Sección Ceremonia y Recepción -->
<section id="ceremonia" class="oculto">
  <h2>Ceremonia Religiosa</h2>
  <p>Iglesia Cristiana "Palabra de Vida" - 2:00 pm</p>
  <h2>Recepción</h2>
  <p>Jardín El Abuelo - 4:00 pm</p>
  <iframe src="https://www.bing.com/maps/embed?h=400&w=600&cp=18.8825~-99.2035&lvl=16&typ=d&sty=r&src=SHELL&FORM=MBEDV8" 
    width="600" height="400" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
</section>

<!-- Sección Fotos -->
<section id="momentos" class="oculto">
  <h2>Nuestros hermosos momentos</h2>
  <p>“Tu amor es lo que he anhelado y el regalo que Dios me ha dado”</p>
  <div class="fotos">
    <img src="foto1.jpg" alt="Foto 1">
    <img src="foto2.jpg" alt="Foto 2">
    <img src="foto3.jpg" alt="Foto 3">
  </div>
</section>

<!-- Contador -->
<section id="contador-section" class="oculto">
  <h2>Faltan:</h2>
  <div id="contador"></div>
</section>

<!-- Sección Comentarios y WhatsApp -->
<section id="contacto" class="oculto">
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
  // Generar partículas
  for(let i=0;i<50;i++){
    let p = document.createElement('div');
    p.className = 'particle';
    p.style.width = p.style.height = Math.random()*5+2+'px';
    p.style.left = Math.random()*100+'%';
    p.style.animationDuration = (10+Math.random()*10)+'s';
    p.style.opacity = Math.random();
    document.getElementById('inicio').appendChild(p);
  }

  // Manejar animación y apertura
  const anillo = document.getElementById('anillo');
  const secciones = ['novios','ceremonia','momentos','contador-section','contacto'];
  const musica = document.getElementById('musica');

  function abrirInvitacion(){
    anillo.style.display='none';
    secciones.forEach(id => document.getElementById(id).classList.remove('oculto'));
    secciones.forEach(id => document.getElementById(id).classList.add('visible'));
    musica.play();
  }

  anillo.addEventListener('click', abrirInvitacion);

  // Apertura automática tras 3 segundos
  setTimeout(abrirInvitacion,3000);

  // Contador
  const contador = document.getElementById('contador');
  const fechaBoda = new Date('December 28, 2025 14:00:00').getTime();

  setInterval(()=>{
    const ahora = new Date().getTime();
    const distancia = fechaBoda - ahora;

    const dias = Math.floor(distancia / (1000*60*60*24));
    const horas = Math.floor((distancia % (1000*60*60*24))/(1000*60*60));
    const minutos = Math.floor((distancia % (1000*60*60))/(1000*60));
    const segundos = Math.floor((distancia % (1000*60))/1000);

    contador.innerHTML = `${dias} días ${horas}h ${minutos}m ${segundos}s`;
  },1000);
</script>
</body>
</html>
[eternamente.mp3](https://github.com/user-attachments/files/22691083/eternamente.mp3)
![ring](https://github.com/user-attachments/assets/7c103387-8c68-4136-9c21-a0e4caffc557)
![photo3](https://github.com/user-attachments/assets/88251ba4-836f-4baa-a527-d6b2ab1a15be)
![photo2](https://github.com/user-attachments/assets/64c146ea-b776-4c00-8130-4f5e320b8d77)
![photo1](https://github.com/user-attachments/assets/3671fd6d-f951-4734-ad51-15e82d51f879)
![momento3](https://github.com/user-attachments/assets/a4dfc32d-9538-4f2c-91f8-9e1d470605f1)
![momento2](https://github.com/user-attachments/assets/6d8f9a67-c9d5-4f08-a8d9-af78138561e5)
![momento1](https://github.com/user-attachments/assets/1d58b583-8979-47f0-b564-efbaad2c8aa1)
<img width="1200" height="1200" alt="flower3" src="https://github.com/user-attachments/assets/e2134c80-3b0a-4637-9baa-6ef7b5ff6705" />
![flower2](https://github.com/user-attachments/assets/61dcbe7c-327c-405d-ab45-44f10d02cf5b)
![flower1](https://github.com/user-attachments/assets/68fa3f5f-9196-4b37-b919-19d9b9bf2ec3)
 
