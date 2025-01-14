<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Viñedos Don Dosco S.A.</title>
    <link href="https://www.youtube.com/watch?v=eap0G9ldKc0" rel="stylesheet">
    <style>
        :root {
            --primary-color: #8E44AD;
            --secondary-color: #2C3E50;
            --accent-color: #E74C3C;
            --text-color: #333;
            --light-bg: #ECF0F1;
        }
        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
            color: var(--text-color);
            scroll-behavior: smooth;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        /* Header y Navegación */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 10px 0;
            position: fixed;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        .logo {
            max-width: 100px;
            animation: fadeInDown 1s ease-in-out;
        }
        nav ul {
            list-style-type: none;
            padding: 0;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
        }
        nav ul li {
            margin: 5px 10px;
        }
        nav ul li a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s;
            font-size: 0.9em;
        }
        nav ul li a:hover {
            color: var(--accent-color);
        }
        /* Secciones */
        section {
            padding: 60px 0;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s, transform 0.8s;
        }
        section.visible {
            opacity: 1;
            transform: translateY(0);
        }
        h2 {
            color: var(--primary-color);
            text-align: center;
            margin-bottom: 30px;
            font-size: 2em;
        }
        /* Hero Section */
        #hero {
            background-image: url('/api/placeholder/1200/600');
            background-size: cover;
            background-position: center;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            position: relative;
        }
        #hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
        }
        #hero .container {
            position: relative;
            z-index: 1;
        }
        #hero h1 {
            font-size: 3em;
            margin-bottom: 20px;
            animation: fadeInUp 1s ease-in-out;
        }
        #hero p {
            font-size: 1.2em;
            margin-bottom: 30px;
            animation: fadeInUp 1.2s ease-in-out;
        }
        .cta-button {
            display: inline-block;
            background-color: var(--accent-color);
            color: white;
            padding: 12px 24px;
            text-decoration: none;
            border-radius: 5px;
            font-weight: bold;
            transition: background-color 0.3s;
            animation: fadeInUp 1.4s ease-in-out;
        }
        .cta-button:hover {
            background-color: #C0392B;
        }
        /* Historia */
        #historia {
            background-color: var(--light-bg);
        }
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        .timeline::after {
            content: '';
            position: absolute;
            width: 6px;
            background-color: var(--primary-color);
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -3px;
        }
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
        }
        .timeline-item::after {
            content: '';
            position: absolute;
            width: 25px;
            height: 25px;
            right: -17px;
            background-color: white;
            border: 4px solid var(--accent-color);
            top: 15px;
            border-radius: 50%;
            z-index: 1;
        }
        .left {
            left: 0;
        }
        .right {
            left: 50%;
        }
        .left::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 22px;
            width: 0;
            z-index: 1;
            right: 30px;
            border: medium solid var(--primary-color);
            border-width: 10px 0 10px 10px;
            border-color: transparent transparent transparent var(--primary-color);
        }
        .right::before {
            content: " ";
            height: 0;
            position: absolute;
            top: 22px;
            width: 0;
            z-index: 1;
            left: 30px;
            border: medium solid var(--primary-color);
            border-width: 10px 10px 10px 0;
            border-color: transparent var(--primary-color) transparent transparent;
        }
        .right::after {
            left: -16px;
        }
        .timeline-content {
            padding: 20px 30px;
            background-color: white;
            position: relative;
            border-radius: 6px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        /* Productos */
        .producto {
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
            margin-bottom: 30px;
            padding: 30px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .producto:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0,0,0,0.15);
        }
        .producto img {
            max-width: 100%;
            border-radius: 8px;
            margin-bottom: 20px;
        }
        .producto h3 {
            color: var(--secondary-color);
            margin-bottom: 15px;
        }
        /* Proceso de Producción */
        .proceso-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        .proceso-item {
            text-align: center;
            padding: 20px;
            background-color: white;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        .proceso-item:hover {
            transform: translateY(-5px);
        }
        .proceso-icon {
            font-size: 48px;
            color: var(--accent-color);
            margin-bottom: 15px;
        }
        /* Análisis Financiero */
        .chart-container {
            width: 100%;
            max-width: 800px;
            margin: 0 auto 40px;
        }
        .financial-summary {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        .financial-item {
            text-align: center;
            margin: 10px;
            flex: 1;
            min-width: 200px;
        }
        .financial-item h3 {
            color: var(--secondary-color);
            margin-bottom: 10px;
        }
        .financial-item p {
            font-size: 1.2em;
            font-weight: bold;
            color: var(--accent-color);
        }
        /* Logística */
        #logistica {
            background-color: var(--light-bg);
        }
        .logistica-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .logistica-item {
            background-color: white;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        }
        .logistica-item h3 {
            color: var(--secondary-color);
            margin-bottom: 15px;
        }
        /* Video Section */
        #video-section {
            background-color: var(--light-bg);
            padding: 40px 0;
            text-align: center;
        }
        #video-section iframe {
            max-width: 100%;
            height: 400px;
            border: none;
        }
        /* Contacto */
        #contacto {
            background-color: white;
            padding: 40px 20px;
            text-align: center;
        }
        #contacto form {
            max-width: 600px;
            margin: 0 auto;
        }
        #contacto input, #contacto textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: 1px solid var(--secondary-color);
            border-radius: 4px;
        }
        #contacto button {
            background-color: var(--accent-color);
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        #contacto button:hover {
            background-color: #C0392B;
        }
        /* Footer */
        footer {
            background-color: var(--primary-color);
            color: white;
            text-align: center;
            padding: 20px 0;
        }
        /* Animaciones */
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        /* Media Queries */
        @media (max-width: 768px) {
            header nav ul {
                flex-direction: column;
                align-items: center;
            }
        }
    </style>
</head>
<body>

<header>
    <div class="container">
        <img src="fotos/logo-removebg-preview.png" alt="Viñedos Don Dosco" class="logo">
        <nav>
            <ul>
                <li><a href="#hero">Inicio</a></li>
                <li><a href="#historia">Historia</a></li>
                <li><a href="#productos">Vinos</a></li>
                <li><a href="#proceso">Proceso de Producción</a></li>
                <li><a href="#finanzas">Análisis Financiero</a></li>
                <li><a href="#logistica">Logística</a></li>
                <li><a href="#organigrama">Organigrama</a></li> <!-- Cambiado -->
                <li><a href="#diagrama-procesos">Diagrama de Procesos</a></li> <!-- Añadido -->
                <li><a href="#layout">Layout</a></li> <!-- Añadido -->
                <li><a href="#video-section">Video</a></li>
                <li><a href="#contacto">Contacto</a></li>
            </ul>
        </nav>
    </div>
</header>

<section id="hero">
    <div class="container">
        <h1>Bienvenido a Viñedos Don Dosco</h1>
        <p>Descubre la tradición y calidad de nuestros vinos.</p>
        <a href="#productos" class="cta-button">Explora nuestros vinos</a>
    </div>
</section>

<section id="historia" class="visible">
    <div class="container">
        <h2>Nuestra Historia</h2>
        <div class="timeline">
            <div class="timeline-item left">
                <div class="timeline-content">
                    <h3>Año 2010</h3>
                    <p>Fundación de Viñedos Don Dosco en la Cordillera de los Andes.</p>
                </div>
            </div>
            <div class="timeline-item right">
                <div class="timeline-content">
                    <h3>Año 2015</h3>
                    <p>Lanzamiento de nuestra primera cosecha de vino tinto.</p>
                </div>
            </div>
            <div class="timeline-item left">
                <div class="timeline-content">
                    <h3>Año 2020</h3>
                    <p>Expansión de la producción y mejora de nuestros procesos.</p>
                </div>
            </div>
            <div class="timeline-item right">
                <div class="timeline-content">
                    <h3>Año 2024</h3>
                    <p>Incorporación de tecnologías de envejecimiento innovadoras.</p>
                </div>
            </div>
        </div>
    </div>
</section>

<section id="productos" class="visible">
    <div class="container">
        <h2>Nuestros Vinos</h2>
        <div class="producto">
            <img src="fotos/caja4.jpeg" alt="Vino Tinto">
            <h3>Vino Tinto Don Dosco</h3>
            <p>Un vino tinto de sabor intenso y aromas frutales.</p>
        </div>
        <div class="producto">
            <img src="fotos/caja2.jpeg" alt="Vino Tinto">
            <h3>Vino Tinto Reserva</h3>
            <p>Un vino de alta gama con notas de roble y frutos rojos.</p>
        </div>
        <div class="producto">
            <img src="fotos/caja.jpeg" alt="Vino Tinto">
            <h3>Vino Tinto Gran Reserva</h3>
            <p>Un vino exclusivo, ideal para ocasiones especiales.</p>
        </div>
    </div>
</section>

<section id="proceso" class="visible">
    <div class="container">
        <h2>Proceso de Producción</h2>
        <div class="proceso-grid">
            <div class="proceso-item">
                <div class="proceso-icon"><i class="fas fa-grape"></i></div>
                <h3>Recolección</h3>
                <p>Selección de uvas en su punto óptimo de maduración.</p>
            </div>
            <div class="proceso-item">
                <div class="proceso-icon"><i class="fas fa-wine-glass-alt"></i></div>
                <h3>Fermentación</h3>
                <p>Proceso natural de transformación del azúcar en alcohol.</p>
            </div>
            <div class="proceso-item">
                <div class="proceso-icon"><i class="fas fa-cask"></i></div>
                <h3>Envejecimiento</h3>
                <p>Uso de temperatura controlada y virutas de madera.</p>
            </div>
            <div class="proceso-item">
                <div class="proceso-icon"><i class="fas fa-bottle"></i></div>
                <h3>Embotellado</h3>
                <p>Envasado en cajas tipo tetrabrik para su distribución.</p>
            </div>
        </div>
    </div>
</section>

<section id="finanzas" class="visible">
    <div class="container">
        <h2>Análisis Financiero</h2>
        <div class="financial-summary">
            <div class="financial-item">
                <h3>Ingresos Anuales</h3>
                <p>$500,000</p>
            </div>
            <div class="financial-item">
                <h3>Costos de Producción</h3>
                <p>$200,000</p>
            </div>
            <div class="financial-item">
                <h3>Beneficio Neto</h3>
                <p>$300,000</p>
            </div>
        </div>
        <div class="chart-container">
            <!-- Aquí puedes incluir un gráfico de barras o líneas -->
        </div>
    </div>
</section>

<section id="logistica" class="visible">
    <div class="container">
        <h2>Logística y Distribución</h2>
        <div class="logistica-grid">
            <div class="logistica-item">
                <h3>Almacenamiento</h3>
                <p>Ubicación estratégica en la Cordillera de los Andes.</p>
            </div>
            <div class="logistica-item">
                <h3>Distribución</h3>
                <p>Red de transporte para garantizar la frescura del producto.</p>
            </div>
        </div>
    </div>
</section>

<section id="organigrama">
    <h2>Organigrama</h2>
    <img src="fotos/organigrama.jpg" alt="Organigrama de Viñedos Don Dosco">
    <p>
        El organigrama es una representación visual de la estructura organizativa de Viñedos Don Dosco. 
        Muestra las diferentes jerarquías, roles y relaciones dentro de la empresa. Este diagrama ayuda a 
        entender la organización del personal, facilitando la comunicación y la gestión de responsabilidades. 
        En nuestro caso, el organigrama incluye posiciones clave como el director general, el encargado de 
        producción, el departamento de ventas y marketing, y el área de logística.
    </p>
</section>

<section id="diagrama-procesos">
    <h2>Diagrama de Procesos</h2>
    <img src="fotos/diagrama de operaciones.png" alt="Diagrama del Proceso de Producción">
    <p>
        El diagrama de procesos es una representación gráfica que describe las etapas y actividades 
        involucradas en la producción de vino en Viñedos Don Dosco. Cada paso, desde la cosecha de las uvas 
        hasta el embotellado, se representa visualmente, permitiendo a todos los involucrados comprender el 
        flujo de trabajo y las interacciones entre las distintas etapas. Este diagrama es fundamental para 
        identificar áreas de mejora y optimización dentro del proceso de producción.
    </p>
</section>

<section id="layout">
    <h2>Sección de Layout</h2>
    <img src="fotos/Imagen1.png" alt="Diagrama del Proceso de Producción">
    <p>
        La sección de layout se refiere a la disposición física de los equipos, maquinarias y áreas de trabajo 
        dentro de la bodega de Viñedos Don Dosco. Un layout eficiente es crucial para maximizar la productividad 
        y minimizar el desperdicio de tiempo y recursos. En nuestro caso, el layout ha sido diseñado para facilitar 
        el flujo de trabajo, desde la recepción de materia prima hasta el almacenamiento del producto terminado, 
        asegurando que cada etapa del proceso de producción esté conectada de manera lógica y eficiente.
    </p>
</section>

<section id="video-section" class="visible">
    <div class="container">
        <h2>Conoce más sobre nosotros</h2>
        <iframe src="fotos/vine.mp4" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </div>
</section>

<section id="contacto">
    <h2>Contacto</h2>
    <p>Si tienes alguna pregunta, no dudes en ponerte en contacto con nosotros.</p>
    <p>Email: familiadondosco@gmail.com</p>
    <p>Teléfono: 1133768366</p>
</section>

<footer>
    <div class="container">
        <p>Para realizar tus compras, visita nuestra <a href="https://don-dosco.github.io/don-dosco/">Página de Compra</a>.</p> <!-- Cambia 'pagina-de-compra.html' por la URL de tu página de compra -->
    </div>
</footer>

<footer>
    <div class="container">
        <p>Para mas infomacion, visita nuestra <a href="https://don-dosco.github.io/web-de-informaci-n/">Página de informacion</a>.</p> <!-- Cambia 'pagina-de-compra.html' por la URL de tu página de compra -->
    </div>
</footer>

<footer>
    <p>&copy; 2024 Viñedos Don Dosco S.A. Todos los derechos reservados.</p>
</footer>

<script>
    // Mostrar secciones al hacer scroll
    const sections = document.querySelectorAll("section");
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.add("visible");
            } else {
                entry.target.classList.remove("visible");
            }
        });
    });

    sections.forEach(section => {
        observer.observe(section);
    });

    // Reproducción automática del video
    const videoIframe = document.querySelector("#video-section iframe");
    videoIframe.src += "?autoplay=1&loop=1";
</script>

</body>
</html>
