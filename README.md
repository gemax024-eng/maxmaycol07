<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MAXQUIWI | Nutrición Ancestral</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Cinzel:wght@500;700&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: #0c0c0c;
      color: #f5f5f5;
      overflow-x: hidden;
    }

    :root {
      --gold: #d4af37;
      --green: #1f4d38;
      --black: #111111;
      --light: #f5f5f5;
    }

    header {
      background: linear-gradient(rgba(0,0,0,.7), rgba(0,0,0,.8)),
      url('https://images.unsplash.com/photo-1502741338009-cac2772e18bc?q=80&w=1974&auto=format&fit=crop');
      background-size: cover;
      background-position: center;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 40px;
    }

    .hero {
      max-width: 900px;
    }

    .hero h1 {
      font-family: 'Cinzel', serif;
      font-size: 5rem;
      color: var(--gold);
      letter-spacing: 5px;
      margin-bottom: 20px;
    }

    .hero p {
      font-size: 1.2rem;
      line-height: 1.8;
      color: #ddd;
      margin-bottom: 30px;
    }

    .btn-main {
      background: var(--gold);
      color: black;
      border: none;
      padding: 15px 35px;
      border-radius: 40px;
      font-weight: 700;
      cursor: pointer;
      transition: .3s;
      text-decoration: none;
    }

    .btn-main:hover {
      background: #f1c94d;
      transform: scale(1.05);
    }

    section {
      padding: 90px 8%;
    }

    .section-title {
      text-align: center;
      margin-bottom: 60px;
    }

    .section-title h2 {
      font-size: 3rem;
      color: var(--gold);
      font-family: 'Cinzel', serif;
      margin-bottom: 15px;
    }

    .section-title p {
      color: #ccc;
      max-width: 700px;
      margin: auto;
      line-height: 1.7;
    }

    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 30px;
    }

    .card {
      background: linear-gradient(180deg, #151515, #0b0b0b);
      border: 1px solid rgba(212,175,55,.25);
      border-radius: 25px;
      overflow: hidden;
      transition: .4s;
      box-shadow: 0 10px 30px rgba(0,0,0,.4);
      position: relative;
    }

    .card:hover {
      transform: translateY(-10px);
      box-shadow: 0 15px 40px rgba(212,175,55,.2);
    }

    .card img {
      width: 100%;
      height: 260px;
      object-fit: cover;
    }

    .card-content {
      padding: 25px;
    }

    .card-content h3 {
      color: var(--gold);
      font-size: 1.7rem;
      margin-bottom: 15px;
    }

    .card-content p,
    .card-content li {
      color: #d7d7d7;
      line-height: 1.7;
      font-size: .95rem;
    }

    .card-content ul {
      margin: 15px 0 20px 18px;
    }

    .recipe {
      margin-top: 15px;
      background: rgba(31,77,56,.25);
      padding: 12px;
      border-left: 3px solid var(--gold);
      border-radius: 10px;
    }

    .buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 25px;
    }

    .buttons button,
    .buttons a {
      flex: 1;
      padding: 12px;
      border: none;
      border-radius: 12px;
      cursor: pointer;
      text-align: center;
      font-weight: 600;
      text-decoration: none;
      transition: .3s;
      font-size: .9rem;
    }

    .facebook {
      background: #1877f2;
      color: white;
    }

    .whatsapp {
      background: #25D366;
      color: black;
    }

    .pedido {
      background: var(--gold);
      color: black;
    }

    .buttons button:hover,
    .buttons a:hover {
      transform: scale(1.04);
    }

    .about {
      background: linear-gradient(135deg, #121212, #163827);
      border-radius: 30px;
      padding: 60px;
      box-shadow: 0 10px 40px rgba(0,0,0,.3);
    }

    .about h2 {
      color: var(--gold);
      font-size: 3rem;
      margin-bottom: 25px;
      font-family: 'Cinzel', serif;
    }

    .about p {
      line-height: 1.9;
      color: #ddd;
      margin-bottom: 15px;
    }

    footer {
      background: #080808;
      padding: 40px;
      text-align: center;
      border-top: 1px solid rgba(212,175,55,.2);
    }

    footer h3 {
      color: var(--gold);
      margin-bottom: 15px;
      font-size: 2rem;
    }

    footer p {
      color: #bbb;
      margin: 6px 0;
    }

    /* MODAL */
    .modal {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,.8);
      display: none;
      justify-content: center;
      align-items: center;
      z-index: 999;
      padding: 20px;
    }

    .modal-content {
      width: 100%;
      max-width: 600px;
      background: #111;
      border-radius: 25px;
      padding: 35px;
      border: 1px solid rgba(212,175,55,.3);
      position: relative;
      animation: fadeIn .4s ease;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: scale(.9);
      }
      to {
        opacity: 1;
        transform: scale(1);
      }
    }

    .modal-content h2 {
      color: var(--gold);
      margin-bottom: 20px;
      text-align: center;
    }

    .close {
      position: absolute;
      right: 20px;
      top: 15px;
      font-size: 1.8rem;
      cursor: pointer;
      color: white;
    }

    form {
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    input,
    textarea {
      padding: 14px;
      border-radius: 12px;
      border: 1px solid #333;
      background: #1a1a1a;
      color: white;
      outline: none;
    }

    input:focus,
    textarea:focus {
      border-color: var(--gold);
    }

    .submit-btn {
      background: var(--gold);
      color: black;
      font-weight: 700;
      border: none;
      padding: 15px;
      border-radius: 12px;
      cursor: pointer;
      transition: .3s;
    }

    .submit-btn:hover {
      background: #f5ca43;
    }

    @media(max-width:768px){
      .hero h1 {
        font-size: 3rem;
      }

      .section-title h2,
      .about h2 {
        font-size: 2.2rem;
      }

      .about {
        padding: 35px;
      }
    }
  </style>
</head>
<body>

  <header>
    <div class="hero">
      <h1>MAXQUIWI</h1>
      <p>
        Nutrición ancestral premium elaborada a base de quiwicha. Productos naturales,
        saludables y funcionales diseñados para una vida moderna con energía, bienestar y sabor.
      </p>
      <a href="#productos" class="btn-main">Explorar Productos</a>
    </div>
  </header>

  <section id="empresa">
    <div class="about">
      <h2>Sobre MAXQUIWI</h2>
      <p>
        MAXQUIWI es una empresa dedicada a transformar la quiwicha en productos innovadores,
        nutritivos y premium, manteniendo la esencia ancestral de los superfoods andinos.
      </p>

      <p>
        Nuestra línea gráfica combina negro mate, dorado y verde para transmitir elegancia,
        salud, exclusividad y conexión con la naturaleza.
      </p>

      <p>
        Trabajamos con ingredientes seleccionados para ofrecer una experiencia saludable,
        deliciosa y funcional para deportistas, familias y consumidores conscientes.
      </p>
    </div>
  </section>

  <section id="productos">
    <div class="section-title">
      <h2>Nuestros Productos</h2>
      <p>
        Descubre los derivados premium de quiwicha desarrollados por MAXQUIWI.
      </p>
    </div>

    <div class="products">

      <!-- PRODUCTO 1 -->
      <div class="card">
        <img src="https://images.unsplash.com/photo-1514996937319-344454492b37?q=80&w=1974&auto=format&fit=crop" alt="Grano de Quiwicha">
        <div class="card-content">
          <h3>Grano de Quiwicha</h3>

          <p>
            Grano natural rico en proteínas, fibra, calcio y aminoácidos esenciales.
          </p>

          <ul>
            <li>Alta energía natural</li>
            <li>Favorece la digestión</li>
            <li>Libre de gluten</li>
            <li>Ideal para deportistas</li>
          </ul>

          <div class="recipe">
            <strong>Receta sugerida:</strong>
            Bowl energético con frutas, yogur y granos de quiwicha tostada.
          </div>

          <div class="buttons">
            <a class="facebook" href="https://facebook.com" target="_blank">Facebook</a>
            <a class="whatsapp" href="https://wa.me/51940707151" target="_blank">WhatsApp</a>
            <button class="pedido" onclick="abrirModal('Grano de Quiwicha')">Pedir</button>
          </div>
        </div>
      </div>

      <!-- PRODUCTO 2 -->
      <div class="card">
        <img src="https://images.pexels.com/photos/6287295/pexels-photo-6287295.jpeg?auto=compress&cs=tinysrgb&w=1200" alt="Harina de Quiwicha">
        <div class="card-content">
          <h3>Harina de Quiwicha</h3>

          <p>
            Harina funcional ideal para preparaciones saludables y nutritivas.
          </p>

          <ul>
            <li>Rica en proteína vegetal</li>
            <li>Perfecta para repostería saludable</li>
            <li>Alto contenido de minerales</li>
            <li>Fuente natural de fibra</li>
          </ul>

          <div class="recipe">
            <strong>Receta sugerida:</strong>
            Panqueques integrales de quiwicha con miel y frutas.
          </div>

          <div class="buttons">
            <a class="facebook" href="https://facebook.com" target="_blank">Facebook</a>
            <a class="whatsapp" href="https://wa.me/51940707151" target="_blank">WhatsApp</a>
            <button class="pedido" onclick="abrirModal('Harina de Quiwicha')">Pedir</button>
          </div>
        </div>
      </div>

      <!-- PRODUCTO 3 -->
      <div class="card">
        <img src="https://images.unsplash.com/photo-1515003197210-e0cd71810b5f?q=80&w=1974&auto=format&fit=crop" alt="Hojuelas de Quiwicha">
        <div class="card-content">
          <h3>Hojuelas de Quiwicha</h3>

          <p>
            Hojuelas ligeras y nutritivas para desayunos saludables y snacks.
          </p>

          <ul>
            <li>Ideal para desayunos</li>
            <li>Fuente de energía diaria</li>
            <li>Ayuda al rendimiento físico</li>
            <li>Bajo contenido de grasas</li>
          </ul>

          <div class="recipe">
            <strong>Receta sugerida:</strong>
            Smoothie bowl con hojuelas de quiwicha y cacao.
          </div>

          <div class="buttons">
            <a class="facebook" href="https://facebook.com" target="_blank">Facebook</a>
            <a class="whatsapp" href="https://wa.me/51940707151" target="_blank">WhatsApp</a>
            <button class="pedido" onclick="abrirModal('Hojuelas de Quiwicha')">Pedir</button>
          </div>
        </div>
      </div>

      <!-- PRODUCTO 4 -->
      <div class="card">
        <img src="https://images.unsplash.com/photo-1585238342024-78d387f4a707?q=80&w=1200&auto=format&fit=crop" alt="Quiwicha Expandida">
        <div class="card-content">
          <h3>Quiwicha Expandida</h3>

          <p>
            Snack natural crocante y saludable elaborado con quiwicha expandida.
          </p>

          <ul>
            <li>Snack saludable</li>
            <li>Ideal para niños y adultos</li>
            <li>Rica en calcio y hierro</li>
            <li>Sabor ligero y natural</li>
          </ul>

          <div class="recipe">
            <strong>Receta sugerida:</strong>
            Barras energéticas con chocolate y quiwicha expandida.
          </div>

          <div class="buttons">
            <a class="facebook" href="https://facebook.com" target="_blank">Facebook</a>
            <a class="whatsapp" href="https://wa.me/51940707151" target="_blank">WhatsApp</a>
            <button class="pedido" onclick="abrirModal('Quiwicha Expandida')">Pedir</button>
          </div>
        </div>
      </div>

    </div>
  </section>

  <footer>
    <h3>MAXQUIWI</h3>
    <p>Nutrición Ancestral Premium</p>
    <p>Contacto: 940707151</p>
    <p>Email: gemax024@gmail.com</p>
  </footer>

  <!-- MODAL -->
  <div class="modal" id="modalPedido">
    <div class="modal-content">
      <span class="close" onclick="cerrarModal()">&times;</span>
      <h2>Formulario de Pedido</h2>

      <!-- IMPORTANTE -->
      <!-- Reemplaza YOUR_ACCESS_KEY por tu access key real de Web3Forms -->
      <!-- Puedes obtenerla gratis en: https://web3forms.com -->

      <form action="https://api.web3forms.com/submit" method="POST">

        <input type="hidden" name="access_key" value="fb5828af-e7db-44ee-b0aa-f8af972b463f">

        <input type="hidden" name="subject" value="Nuevo pedido desde MAXQUIWI">

        <input type="hidden" name="from_name" value="MAXQUIWI WEB">

        <input type="hidden" id="producto" name="Producto" value="">

        <input type="text" name="Nombres" placeholder="Nombres" required>

        <input type="text" name="Apellidos" placeholder="Apellidos" required>

        <input type="tel" name="Telefono" placeholder="Teléfono" required>

        <input type="text" name="Direccion" placeholder="Dirección" required>

        <input type="text" name="Codigo_de_Pago" placeholder="Código de Pago" required>

        <textarea name="Mensaje" rows="4" placeholder="Detalle adicional del pedido"></textarea>

        <button type="submit" class="submit-btn">Enviar Pedido</button>
      </form>
    </div>
  </div>

  <script>
    const modal = document.getElementById('modalPedido');

    function abrirModal(producto) {
      modal.style.display = 'flex';
      document.getElementById('producto').value = producto;
    }

    function cerrarModal() {
      modal.style.display = 'none';
    }

    window.onclick = function(e) {
      if (e.target === modal) {
        cerrarModal();
      }
    }
  </script>

</body>
</html>
