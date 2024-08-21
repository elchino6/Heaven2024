<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Heaven - Simulador de Armado de PC en VR</title>
    <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css">
    <style>
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            background-color: #121212;
            color: #F5F5F5;
            margin: 0;
        }

        header {
            background-color: #1F1F1F;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }

        h1 {
            color: #BB86FC;
            text-align: center;
            font-size: 36px;
            margin: 0;
        }

        nav ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            color: #F5F5F5;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        nav a:hover {
            color: #BB86FC;
        }

        #hero {
            background-image: url('https://example.com/hero-bg.jpg');
            background-size: cover;
            background-position: center;
            min-height: 600px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 0 20px;
        }

        #hero h2 {
            color: #BB86FC;
            font-size: 48px;
            margin-bottom: 20px;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        #hero p {
            color: #F5F5F5;
            font-size: 24px;
            line-height: 1.5;
            max-width: 800px;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
        }

        #hero img {
            margin-top: 50px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.7);
        }

        section {
            padding: 60px 20px;
            max-width: 1000px;
            margin: 0 auto;
        }

        h2 {
            color: #BB86FC;
            text-align: center;
            margin-bottom: 30px;
            font-size: 36px;
        }

        ul {
            list-style: none;
            padding: 0;
        }

        li {
            background-color: #1F1F1F;
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s ease;
        }

        li:hover {
            background-color: #2A2A2A;
        }

        .button {
            background-color: #03DAC5;
            color: #121212;
            padding: 15px 30px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .button:hover {
            background-color: #00B3A1;
        }

        footer {
            background-color: #1F1F1F;
            padding: 20px;
            text-align: center;
        }

        footer p {
            margin: 0;
            color: #F5F5F5;
        }

        footer ul {
            list-style: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            margin-top: 10px;
        }

        footer li {
            margin: 0 10px;
        }

        footer a {
            color: #F5F5F5;
            text-decoration: none;
            font-size: 24px;
        }

        footer a:hover {
            color: #BB86FC;
        }

        /* Nuevas reglas para resaltar enlaces */
        #components a {
            color: #F5F5F5;
            text-decoration: none;
            font-weight: bold;
            display: block;
        }

        #components a:hover {
            color: #BB86FC;
            background-color: #333;
            padding: 15px;
            border-radius: 5px;
        }

        .tab-buttons {
            text-align: center;
            margin-bottom: 20px;
        }

        .tab-button {
            background-color: #1F1F1F;
            color: #F5F5F5;
            border: none;
            padding: 10px 20px;
            margin: 0 5px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .tab-button.active {
            background-color: #BB86FC;
        }

        .tab-content {
            display: none;
            text-align: center;
        }

        .tab-content.active {
            display: block;
        }

        .tab-content img {
            max-width: 100%;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.7);
        }
        .sketchfab-embed-wrapper {
            text-align: center;
            margin: 40px 0;
        }

        .sketchfab-embed-wrapper iframe {
            width: 80vw; /* Ajusta el tamaño del iframe */
            height: 450px; /* Ajusta la altura del iframe */
            border: 0;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
        }

        .sketchfab-embed-wrapper p {
            font-size: 18px;
            margin: 10px 0 0;
            color: #F5F5F5;
        }

        .sketchfab-embed-wrapper a {
            color: #03DAC5;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        .sketchfab-embed-wrapper a:hover {
            color: #BB86FC;
        }
       /* Estilo para los botones de la guía de armado */
       .step-menu .step-button {
            background-color: #1F1F1F;
            color: #F5F5F5;
            border: none;
            padding: 15px;
            margin: 5px 0;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease, color 0.3s ease;
            text-align: left;
            display: block;
            font-weight: bold;
            font-size: 16px;
        }

        .step-menu .step-button:hover {
            background-color: #BB86FC;
            color: #121212;
        }

        /* Estilo para el contenido de los pasos */
        .step-content {
            display: none;
            padding: 15px;
            background-color: #1F1F1F;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            margin-top: 10px;
            max-width: 100%;
        }

        .step-content.active {
            display: block;
        }

        /* Menu de pasos de guía */
        .steps-container {
            display: flex;
        }

        .step-menu {
            flex: 1;
            max-width: 250px;
            margin: 20px;
        }

        .step-button {
            background-color: #1F1F1F;
            color: #F5F5F5;
            border: none;
            padding: 10px;
            margin: 5px 0;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease, color 0.3s ease;
            text-align: left;
        }

        .step-button:hover {
            background-color: #BB86FC;
            color: #121212;
        }

        .step-content {
            flex: 3;
            display: none;
            padding: 15px;
            background-color: #1F1F1F;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            margin-left: 20px;
            max-width: calc(100% - 250px); /* Ajusta el ancho máximo restando el ancho del menú */
        }

        .step-content.active {
            display: block;
        }

        .steps-container {
            display: flex;
            flex-wrap: wrap;
        }

        .step-menu {
            flex: 1;
            max-width: 250px;
            margin: 20px;
        }

        .step-content {
            flex: 3;
            display: none;
            padding: 15px;
            background-color: #1F1F1F;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            margin-left: 20px;
        }

        .step-content.active {
            display: block;
        }

        /* Estilo para el contenedor del video */
.video-container {
    text-align: center;
    margin: 40px 0;
}

.video-container iframe {
    width: 80vw; /* Ajusta el tamaño del iframe */
    height: 450px; /* Ajusta la altura del iframe */
    border: 0;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
}

.video-container p {
    font-size: 18px;
    margin: 10px 0 0;
    color: #F5F5F5;
}

.video-container a {
    color: #03DAC5;
    text-decoration: none;
    font-weight: bold;
    transition: color 0.3s ease;
}

.video-container a:hover {
    color: #BB86FC;
}

    </style>
</head>
<body>
    <header>
        <h1>Heaven</h1>
        <nav>
            <ul>
                <li><a href="#about">Sobre nosotros</a></li>
                <li><a href="#features">Características</a></li>
                <li><a href="#benefits">Beneficios</a></li>
                <li><a href="#assembly-guide">Guía de Armado</a></li>
                <li><a href="#download">Descargar</a></li>
                <li><a href="#components">Componentes del PC</a></li>
                <li><a href="#faq">FAQ</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="hero">
            <div class="container">
                <h2>Heaven: Domina el arte de ensamblar PCs</h2>
                <p>Sumérgete en una experiencia de realidad virtual única y aprende a construir tu propia computadora paso a paso.</p>
                <div class="sketchfab-embed-wrapper"> 
                    <iframe title="Computer Parts (Built PC)" frameborder="0" allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered web-share src="https://sketchfab.com/models/bd6fb0ed93f3475b890a099fedecf351/embed"> </iframe> 
                    <p>
                        <a href="https://sketchfab.com/3d-models/computer-parts-built-pc-bd6fb0ed93f3475b890a099fedecf351?utm_medium=embed&utm_campaign=share-popup&utm_content=bd6fb0ed93f3475b890a099fedecf351" target="_blank" rel="nofollow"> 
                            Computer Parts (Built PC) 
                        </a> by 
                        <a href="https://sketchfab.com/DanielCardonaArt?utm_medium=embed&utm_campaign=share-popup&utm_content=bd6fb0ed93f3475b890a099fedecf351" target="_blank" rel="nofollow"> 
                            Daniel Cardona 
                        </a> on 
                        <a href="https://sketchfab.com?utm_medium=embed&utm_campaign=share-popup&utm_content=bd6fb0ed93f3475b890a099fedecf351" target="_blank" rel="nofollow">
                            Sketchfab
                        </a>
                    </p>
                </div>
            </div>
        </section>

        <section id="about">
            <h2>Sobre Heaven</h2>
            <p>Heaven es un simulador de realidad virtual que te permite aprender a ensamblar una computadora desde cero. Con una guía paso a paso y componentes interactivos, podrás dominar el arte de armar tu propio PC de manera divertida y efectiva.</p>
        </section>

        <section id="features">
            <h2>Características</h2>
            <ul>
                <li>Guía paso a paso para ensamblar una PC.</li>
                <li>Interacción en realidad virtual con componentes reales.</li>
                <li>Simulación precisa del proceso de armado.</li>
                <li>Compatible con una amplia gama de hardware.</li>
                <li>Experiencia educativa inmersiva.</li>
            </ul>
        </section>

        <section id="benefits">
            <h2>Beneficios</h2>
            <ul>
                <li>Aprende a armar una PC sin riesgo de dañar componentes.</li>
                <li>Familiarízate con el hardware y las herramientas necesarias.</li>
                <li>Mejora tus habilidades técnicas y de resolución de problemas.</li>
                <li>Experiencia Realista.</li>
                <li>Flexibilidad de Aprendizaje</li>
            </ul>
        </section>

        <!-- Nueva sección de guía de armado -->
       
        <section id="assembly-guide">
            <h2>Guía de Armado</h2>
            <div class="steps-container">
                <div class="step-menu">
                    <button class="step-button" onclick="showStepContent(0)">0. Introducción</button>
                    <button class="step-button" onclick="showStepContent(1)">1. Instalación de la CPU</button>
                    <button class="step-button" onclick="showStepContent(2)">2. Colocación de la Memoria RAM</button>
                    <button class="step-button" onclick="showStepContent(3)">3. Montaje de la Placa Madre</button>
                    <button class="step-button" onclick="showStepContent(4)">4. Instalación del Sistema de Refrigeración</button>
                    <button class="step-button" onclick="showStepContent(5)">5. Montaje de la Tarjeta Gráfica</button>
                    <button class="step-button" onclick="showStepContent(6)">6. Conexión de la Fuente de Poder</button>
                    <button class="step-button" onclick="showStepContent(7)">7. Instalación del Almacenamiento</button>
                    <button class="step-button" onclick="showStepContent(8)">8. Cableado y Conexiones</button>
                    <button class="step-button" onclick="showStepContent(9)">9. Encendido y Pruebas</button>
                    <button class="step-button" onclick="showStepContent(10)">10. Consejos Finales</button>
                </div>
                <div class="step-content" id="step-content-0">
                    <h3>0. Preparación</h3>
                    <p>Bienvenido a la guía de armado de Heaven. Aquí te guiaremos paso a paso en el proceso de armar tu PC. Comencemos desde lo más básico hasta lo más avanzado.</p>
                    
                        <li>Un destornillador magnético.</li>
                        <li>Bridas o tiras de velcro, y unas tijeras.</li>
                        <li>Una superficie limpia y no conductora para montar el PC.</li>
                        <li>Respira hondo, lee primero los manuales y ¡en marcha!</li>
                    
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/kactLxX_Xqs" title="Step 0: Preparation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-1">
                    <h3>1. Instalación de la CPU</h3>
                    <p>Iniciaremos con la instalación del procesador en la placa madre. Asegúrate de alinear correctamente los pines y aplicar la pasta térmica.</p>
                    
                        <li>Destapaa el socket de la CPU</li>
                        <li>Alinea la muesca de la CPU con las muescas de guía del socket e introdúcela con cuidado en el socket.</li>
                        <li>Asegúrate de que la CPU está bien colocada y, a continuación, vuelve a taparla y fíjala en el procesador.</li>
                    
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/T_Aujb23txM" title="Step 1: CPU Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-2">
                    <h3>2. Colocación de la Memoria RAM</h3>
                    <p>En este paso, instalaremos los módulos de memoria RAM en las ranuras correspondientes de la placa madre.</p>
                    <li> Presiona hacia abajo las pestañas de bloqueo/desbloqueo que se encuentran en los extremos de los sockets de la memoria.</li>
                    <li>Consulta en el manual de la placa base para saber en qué orden deben instalarse los módulos de memoria y asegúrate de cuáles son los sockets que se recomienda insertar primero.</li>
                    <li>Empuja los módulos hacia abajo hasta oír un "clic", que indica que las pestañas de retención se han accionado y el módulo ha quedado fijado.</li>
                    
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/GcSmFEB3QiE" title="Step 2: Memory Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-3">
                    <h3>3. Instalar la unidad M.2</h3>
                    <p>Colocaremos la placa madre en el gabinete y aseguraremos que esté bien fija con los tornillos.</p>
                    <li>Mueve y aprieta los tornillos de los separadores de la M.2.</li>
                    <li>Coge la unidad de disco e introdúcela suavemente en el conector en un ángulo de 45 grados.</li>
                    <li>Presiona hacia el separador y fíjala con el pequeño tornillo.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/0OiUOfCJd7s" title="Step 3: M.2 Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-4">
                    <h3>4. Instalación del Sistema de Refrigeración</h3>
                    <p>Ahora instalaremos el sistema de refrigeración, ya sea un disipador de aire o un sistema de refrigeración líquida.</p>
                    <li>Coloca la placa trasera en la parte posterior de la placa base (si tienes alguna).</li>
                    <li>Aplica una gota de pasta térmica en la superficie del procesador.</li>
                    <li>Conecta el cable del ventilador de la CPU al cabezal del ventilador de la CPU en la placa base.</li>
                    <li>Baja el sistema de refrigeración en vertical y colócalo sobre la CPU. Fíjalo uniformemente apretando los tornillos opuestos poco a poco.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/X2gkdatETmY" title="Step 4: CPU Cooler Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-5">
                    <h3>5.Instalar la placa base</h3>
                    <li>Instala la placa de E/S en la parte posterior de la caja.</li>
                    <li>Coge la placa base e introdúcela con cuidado en un ángulo de 45 grados dentro de la caja.</li>
                    <li>Haz coincidir los agujeros de montaje de la placa base con los separadores de la caja.</li>
                    <li>Fija la placa con cada uno de los tornillos suministrados.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/GIL81qWnqDQ" title="Step 5: Motherboard Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-6">
                    <h3>6.Instalar el almacenamiento</h3>
                    <p>Colocaremos las unidades de almacenamiento, ya sean SSD o HDD, en sus respectivas bahías.</p>
                    <li>Conecta un extremo del cable SATA a los puertos SATA de la placa base y el otro a los dispositivos de almacenamiento (2,5''/3,5'') propiamente dichos.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/mYePiRzT4ws" title="Step 6: Storage Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-7">
                    <h3>7.Instalar la tarjeta gráfica</h3>
                    <p>Precaución:
                        Algunas tarjetas de gama alta son más largas o requieren más espacio en la ranura PCI. Asegúrate de comprobarlo de antemano para elegir una caja en la que quepa la tarjeta gráfica.</p>
                        <li> Quita el soporte PCI-e trasero de la caja.
                        <li>Desbloquea la ranura PCI-e empujando hacia atrás el pequeño cierre de plástico situado en su parte trasera.</li>
                        <li>Sujeta la tarjeta con las dos manos, introduce la tarjeta gráfica dentro de la caja e instálala en la ranura PCI-e de la placa base.</li>
                        <li>Fija la tarjeta gráfica a la parte posterior del chasis con los tornillos necesarios.</li>
                        <iframe width="700" height="465" src="https://www.youtube.com/embed/1vsaWVKdJ4I" title="Step 7: Graphics Card Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                
                    </div>
                <div class="step-content" id="step-content-8">
                    <h3>8.Instalar la fuente de alimentación</h3>
                    
                    <li>Monta la fuente de alimentación (PSU) en el chasis y fíjala con todos los tornillos.</li>
                    <li>Conecta el conector de alimentación de 24 pines al socket de la placa base.</li>
                    <li>Conecta el conector de alimentación de 8 pines de la CPU a la placa base.</li>
                    <li>Conecta el cable PCI-E de 6+2 pines a la tarjeta gráfica (puede variar según la tarjeta gráfica)</li>
                    <li>Conecta el conector de alimentación SATA al disco duro</li>
                    <li>Conecta los otros conectores Molex (con 4 pines horizontales) a los dispositivos adicionales (por ejemplo, unidades ópticas de DVD/CD)</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/pNU09htvjcw" title="Step 8: Power Supply Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-9">
                    <h3>9.Conectar el panel frontal y organizar los cables</h3>
                    <li>Conecta el cable del interruptor de encendido/interruptor de reinicio/LED de encendido/LED del disco duro al cabezal de pines JFP1 de la placa base.
                    <li>Conecta los cables USB frontales a los cabezales de pines USB de la placa base.</li>
                    <li>Conecta el cable USB 3.0/USB 2.0 al cabezal de pines USB 3.0/USB 2.0.</li>
                    <li>Conecta el cable USB de tipo C frontal al cabezal de pines USB de tipo C frontales.</li>
                    <li>Connect the Audio(Speaker) Cable to the motherboard JAUD1 Pin header.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/QzhY1EnkDKQ" title="Step 9: Front panel connection and cable management | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
                <div class="step-content" id="step-content-10">
                    <h3>10. Instalar el sistema operativo </h3>
                    <li>Prepara una unidad USB3 de 8 GB como mínimo.</li>
                    <li>En un ordenador con Internet, busca "herramienta de medios de instalación de Windows 10*". Descárgala y ejecútala. Elige crear la imagen en el USB. El programa formateará la unidad o borrará su contenido.</li>
                    <li>Conecta el USB de instalación en un puerto USB trasero de la placa base, elige un puerto USB3 rápido con entrada roja o un USB3 normal con entrada azul. Enciende el ordenador. Normalmente, en el primer arranque se cargará la BIOS. Puedes guardar y salir, y el PC se reiniciará. El USB debería cargarse para empezar con la instalación.</li>
                    <iframe width="700" height="465" src="https://www.youtube.com/embed/dxiXkmtdjEY" title="Step 10: Operation System Installation | #YesWeBuild | MSI" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
            </div>
        </section>


        <section id="download">
            <h2>Descargar Heaven</h2>
            <p>Descarga ahora el simulador de armado de PCs en realidad virtual y comienza a aprender hoy mismo.(Próximamente)</p>
            <button class="button">Descargar</button>
        </section>

        <section id="components">
            <h2>Componentes del PC</h2>
            <p>Explora los diferentes componentes que puedes utilizar en el simulador para armar tu computadora:</p>
            <ul>
                <li><a href="placa_base.html">Placa base</a></li>
                <li><a href="cpu.html">Procesador (CPU)</a></li>
                <li><a href="ram.html">Memoria RAM</a></li>
                <li><a href="GPU.html">Tarjeta gráfica (GPU)</a></li>
                <li><a href="almacenamiento.html">Almacenamiento (HDD/SSD)</a></li>
                <li><a href="Fuente_de_poder.html">Fuente de alimentación</a></li>
                <li><a href="disipador.html">Sistema de refrigeración</a></li>
                <li><a href="Chasis.html">Chasis o torre</a></li>
            </ul>
        </section>

        <section id="faq">
            <h2>Preguntas frecuentes (FAQ)</h2>
            <ul>
                <li><strong>¿Necesito experiencia previa para usar Heaven?</strong> No, Heaven está diseñado tanto para principiantes como para expertos.</li>
                <li><strong>¿Es necesario un casco de realidad virtual?</strong> Sí, para la experiencia completa de Heaven se recomienda utilizar un casco de realidad virtual.</li>
                <li><strong>¿Puedo elegir diferentes componentes para armar mi PC?</strong> Sí, Heaven te permite seleccionar entre una variedad de componentes para personalizar tu computadora.</li>
            </ul>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Heaven. Todos los derechos reservados.</p>
        <ul>
            <li><a href="#"><i class="fab fa-facebook"></i></a></li>
            <li><a href="#"><i class="fab fa-twitter"></i></a></li>
            <li><a href="#"><i class="fab fa-instagram"></i></a></li>
            <li><a href="#"><i class="fab fa-linkedin"></i></a></li>
        </ul>
    </footer>

    <script>
        function showStep(step) {
            const contents = document.querySelectorAll('.step-content');
            const stepText = document.getElementById('step-text');
            contents.forEach(content => content.classList.remove('active'));
            stepText.textContent = `Detalles del Paso ${step}: ...`; // Agrega contenido real aquí
            document.getElementById('step-content').classList.add('active');
        }
    </script>
    <script>
        function showStepContent(step) {
            // Oculta todos los contenidos de los pasos
            const contents = document.querySelectorAll('.step-content');
            contents.forEach(content => content.classList.remove('active'));
    
            // Muestra el contenido del paso seleccionado
            const stepContent = document.getElementById(`step-content-${step}`);
            if (stepContent) {
                stepContent.classList.add('active');
            }
        }
    </script>
    
</body>
</html>
