# mini-site-projeto-tcc-vitoria
/* ======== ESTILOS GERAIS ======== */
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f5f5f5;
            color: #222;
            transition: 0.3s;
        }


        .dark {
            background: #1b1b1b;
            color: #ddd;
        }


        header {
            background: #0077ff;
            color: white;
            padding: 15px;
        }


        nav ul {
            list-style: none;
            padding: 0;
            display: flex;
            gap: 20px;
        }


        nav a {
            color: white;
            text-decoration: none;
            font-weight: bold;
        }


        .container {
            max-width: 900px;
            margin: auto;
            padding: 20px;
        }


        h2 {
            text-align: center;
            margin-top: 40px;
            animation: fadeIn 1s ease;
        }


        /* ======== ANIMAÇÃO ======== */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to   { opacity: 1; transform: translateY(0); }
        }


        /* ======== CARDS ======== */
        .cards {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
            justify-content: center;
        }


        .card {
            background: white;
            width: 250px;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            box-shadow: 0 3px 8px rgba(0,0,0,0.2);
            transition: 0.3s;
        }


        .dark .card {
            background: #333;
        }


        .card:hover {
            transform: scale(1.05);
        }


        .card img {
            width: 100%;
            border-radius: 10px;
        }


        /* ======== FORMULÁRIO ======== */
        form {
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.2);
        }


        .dark form {
            background: #333;
        }


        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border: none;
            border-radius: 5px;
        }


        button {
            background: #0077ff;
            color: white;
            border: none;
            padding: 10px 20px;
            cursor: pointer;
            border-radius: 5px;
            margin-top: 10px;
        }


        button:hover {
            background: #005fcc;
        }


        /* ======== MODAL ======== */
        #modal {
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.7);
            display: none;
            justify-content: center;
            align-items: center;
        }


        #modal-content {
            background: white;
            padding: 30px;
            border-radius: 10px;
            width: 300px;
            text-align: center;
        }


        .dark #modal-content {
            background: #444;
        }


        /* ======== SLIDER ======== */
        .slider {
            width: 100%;
            max-width: 600px;
            margin: 30px auto;
            overflow: hidden;
            border-radius: 10px;
        }


        .slider img {
            width: 100%;
            display: none;
        }


        .slider img.active {
            display: block;
        }


<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Super Mini-Site</title>


    <link rel="stylesheet" href="staly.css">
 
</head>


<body>
    <header>
        <nav class="container">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#servicos">Serviços</a></li>
                <li><a href="#sobre">Sobre</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>


    <div class="container">


        <!-- ==== HOME ==== -->
        <section id="home">
            <h2>Bem-vindo ao Mini-Site</h2>
            <p>Este site demonstra HTML, CSS, JavaScript, animações, cards, formulário, modal, menu e muito mais!</p>
            <button onclick="alternarTema()">Alternar Tema</button>
            <button onclick="abrirModal()">Abrir Modal</button>


            <!-- SLIDER -->
            <div class="slider">
                <img src="https://picsum.photos/800/300?1" class="active">
                <img src="https://picsum.photos/800/300?2">
                <img src="https://picsum.photos/800/300?3">
            </div>
        </section>


        <!-- ==== SERVIÇOS ==== -->
        <section id="servicos">
            <h2>Nossos Serviços</h2>


            <div class="cards">
                <div class="card">
                    <img src="https://picsum.photos/200?4">
                    <h3>Web Design</h3>
                    <p>Sites modernos e responsivos.</p>
                </div>


                <div class="card">
                    <img src="https://picsum.photos/200?5">
                    <h3>Programação</h3>
                    <p>Desenvolvimento completo de sistemas.</p>
                </div>


                <div class="card">
                    <img src="https://picsum.photos/200?6">
                    <h3>Consultoria</h3>
                    <p>Ajudamos você a crescer digitalmente.</p>
                </div>
            </div>
        </section>


        <!-- ==== SOBRE ==== -->
        <section id="sobre">
            <h2>Sobre Nós</h2>
            <p>
                Somos um time apaixonado por tecnologia, focado em criar experiências digitais incríveis.
            </p>
        </section>


        <!-- ==== CONTATO ==== -->
        <section id="contato">
            <h2>Contato</h2>


            <form onsubmit="validarFormulario(event)">
                <input type="text" id="nome" placeholder="Seu nome">
                <input type="email" id="email" placeholder="Seu email">
                <textarea id="mensagem" rows="4" placeholder="Sua mensagem"></textarea>
                <button type="submit">Enviar</button>
            </form>
        </section>
    </div>


    <!-- MODAL -->
    <div id="modal">
        <div id="modal-content">  
            <h3>Modal Ativo!</h3>
            <p>Este é um exemplo de modal com JavaScript.</p>
            <button onclick="fecharModal()">Fechar</button>
        </div>
    </div>
    <script src="app.js"></script>
</body>
</html>

/* ====== MUDAR TEMA ====== */
        function alternarTema() {
            document.body.classList.toggle("dark");
        }


        /* ====== MODAL ====== */
        function abrirModal() {
            document.getElementById("modal").style.display = "flex";
        }


        function fecharModal() {
            document.getElementById("modal").style.display = "none";
        }


        /* ====== SLIDER ====== */
        let slideIndex = 0;
        const slides = document.querySelectorAll(".slider img");


        function trocarSlide() {
            slides[slideIndex].classList.remove("active");
            slideIndex = (slideIndex + 1) % slides.length;
            slides[slideIndex].classList.add("active");
        }


        setInterval(trocarSlide, 3000);


        /* ====== VALIDAÇÃO DO FORMULÁRIO ====== */
        function validarFormulario(e) {
            e.preventDefault();


            const nome = document.getElementById("nome").value.trim();
            const email = document.getElementById("email").value.trim();


            if (!nome || !email) {
                alert("Por favor, preencha nome e email.");
                return;
            }


            alert("Mensagem enviada com sucesso!");
        }


