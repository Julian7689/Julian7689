<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Camilo – Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* HEADER */
        .header {
            text-align: center;
            margin-bottom: 60px;
            animation: slideDown 0.8s ease-out;
        }

        @keyframes slideDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 3.5em;
            background: linear-gradient(45deg, #00d4ff, #0099ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            font-weight: 800;
            letter-spacing: -1px;
        }

        .subtitle {
            font-size: 1.3em;
            color: #b0b0b0;
            margin-bottom: 20px;
            font-weight: 300;
        }

        .divider {
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, #00d4ff, #0099ff);
            margin: 0 auto 30px;
            border-radius: 2px;
            animation: expandWidth 0.8s ease-out;
        }

        @keyframes expandWidth {
            from { width: 0; }
            to { width: 100px; }
        }

        /* SECTION */
        .section {
            margin-bottom: 50px;
            animation: fadeInUp 0.8s ease-out backwards;
        }

        .section:nth-child(2) { animation-delay: 0.1s; }
        .section:nth-child(3) { animation-delay: 0.2s; }
        .section:nth-child(4) { animation-delay: 0.3s; }
        .section:nth-child(5) { animation-delay: 0.4s; }
        .section:nth-child(6) { animation-delay: 0.5s; }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section h2 {
            font-size: 1.8em;
            margin-bottom: 20px;
            color: #00d4ff;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .section h2::before {
            content: '';
            width: 4px;
            height: 25px;
            background: linear-gradient(180deg, #00d4ff, #0099ff);
            border-radius: 2px;
        }

        /* CARDS */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 12px;
            padding: 25px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(0, 212, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .card:hover {
            border-color: rgba(0, 212, 255, 0.6);
            background: rgba(0, 212, 255, 0.1);
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 212, 255, 0.2);
        }

        .card:hover::before {
            left: 100%;
        }

        .card h3 {
            color: #00d4ff;
            margin-bottom: 10px;
            font-size: 1.2em;
        }

        .card p {
            color: #b0b0b0;
            font-size: 0.95em;
        }

        .tech-tag {
            display: inline-block;
            background: rgba(0, 212, 255, 0.15);
            border: 1px solid rgba(0, 212, 255, 0.3);
            color: #00d4ff;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85em;
            margin-top: 10px;
            margin-right: 8px;
            transition: all 0.3s ease;
        }

        .tech-tag:hover {
            background: rgba(0, 212, 255, 0.3);
            transform: scale(1.05);
        }

        /* TECH LIST */
        .tech-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
        }

        .tech-item {
            background: rgba(0, 212, 255, 0.08);
            border-left: 3px solid #00d4ff;
            padding: 15px;
            border-radius: 8px;
            transition: all 0.3s ease;
        }

        .tech-item:hover {
            background: rgba(0, 212, 255, 0.15);
            padding-left: 20px;
        }

        .tech-item strong {
            color: #00d4ff;
        }

        /* PROJECTS */
        .project-item {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(0, 212, 255, 0.2);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 15px;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
        }

        .project-item:hover {
            border-color: #00d4ff;
            background: rgba(0, 212, 255, 0.1);
            transform: translateX(5px);
        }

        .project-item h3 {
            color: #00d4ff;
            margin-bottom: 8px;
            font-size: 1.15em;
        }

        .project-item p {
            color: #b0b0b0;
            margin-bottom: 10px;
        }

        /* FOOTER */
        .footer {
            text-align: center;
            padding-top: 40px;
            border-top: 1px solid rgba(0, 212, 255, 0.2);
            color: #808080;
            animation: fadeInUp 0.8s ease-out 0.6s backwards;
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            margin-bottom: 20px;
        }

        .social-link {
            color: #00d4ff;
            text-decoration: none;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .social-link:hover {
            color: #0099ff;
            transform: scale(1.1);
        }

        /* RESPONSIVE */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.2em;
            }

            .cards-grid {
                grid-template-columns: 1fr;
            }

            .tech-list {
                grid-template-columns: 1fr;
            }
        }

        /* STATS COUNTER */
        .stat {
            text-align: center;
            padding: 15px;
        }

        .stat-number {
            font-size: 2em;
            color: #00d4ff;
            font-weight: 800;
        }

        .stat-label {
            color: #808080;
            font-size: 0.9em;
            margin-top: 5px;
        }

        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- HEADER -->
        <div class="header">
            <h1>Camilo</h1>
            <p class="subtitle">Full Stack Developer</p>
            <div class="divider"></div>
            <p class="subtitle" style="font-size: 1.1em; margin-top: 15px;">
                Construyendo soluciones empresariales escalables y experiencias de usuario excepcionales
            </p>
        </div>

        <!-- PROFESSIONAL PROFILE -->
        <div class="section">
            <h2>🧩 Perfil Profesional</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🚀 Backend</h3>
                    <p>Experiencia en <strong>Java (Spring Boot)</strong>, <strong>Node.js</strong>, y arquitecturas modulares con <strong>GraphQL (DGS)</strong>.</p>
                </div>
                <div class="card">
                    <h3>🎨 Frontend</h3>
                    <p>Desarrollo orientado a UX/UI con <strong>React</strong>, <strong>Next.js</strong>, <strong>TailwindCSS</strong> y <strong>Redux Toolkit</strong>.</p>
                </div>
                <div class="card">
                    <h3>📱 Mobile</h3>
                    <p>Aplicaciones móviles nativas con <strong>Flutter</strong> y arquitectura CRUD completa.</p>
                </div>
                <div class="card">
                    <h3>🔒 Seguridad</h3>
                    <p>Implementación de <strong>JWT authentication</strong>, control de permisos y políticas de seguridad avanzadas.</p>
                </div>
                <div class="card">
                    <h3>💻 Desktop</h3>
                    <p>Desarrollo de aplicaciones de escritorio con <strong>C# + SQL Server</strong> y validación robusta.</p>
                </div>
                <div class="card">
                    <h3>🐳 DevOps</h3>
                    <p>Containerización con <strong>Docker</strong> y primeros pasos en infraestructura cloud.</p>
                </div>
            </div>
        </div>

        <!-- TECHNOLOGIES -->
        <div class="section">
            <h2>🛠️ Stack Tecnológico</h2>
            <div class="tech-list">
                <div class="tech-item">
                    <strong>Backend:</strong> Java/Spring Boot, Node.js, GraphQL, REST APIs
                </div>
                <div class="tech-item">
                    <strong>Frontend:</strong> React, Next.js, TailwindCSS, Redux Toolkit, TypeScript
                </div>
                <div class="tech-item">
                    <strong>Mobile:</strong> Flutter, Dart
                </div>
                <div class="tech-item">
                    <strong>Bases de Datos:</strong> PostgreSQL, SQL Server, MySQL
                </div>
                <div class="tech-item">
                    <strong>Herramientas:</strong> Docker, Git, WebSockets, JWT, Apollo Client
                </div>
                <div class="tech-item">
                    <strong>Otros:</strong> C#, GraphQL DGS, Windows Forms, Real-time Communication
                </div>
            </div>
        </div>

        <!-- PROJECTS -->
        <div class="section">
            <h2>📂 Proyectos Destacados</h2>
            <div class="project-item">
                <h3>🔹 Sistema Empresarial Modular</h3>
                <p>Plataforma completa incluyendo gestión de usuarios, personal, proyectos, novedades, reportes PDF y notificaciones por email.</p>
                <span class="tech-tag">Spring Boot</span>
                <span class="tech-tag">GraphQL</span>
                <span class="tech-tag">JWT</span>
                <span class="tech-tag">React</span>
            </div>

            <div class="project-item">
                <h3>🔹 Chat Flotante con IA (Next.js + WebSockets)</h3>
                <p>Widget de chat personalizado conectado a API de IA con almacenamiento de mensajes e interacción en tiempo real.</p>
                <span class="tech-tag">Next.js</span>
                <span class="tech-tag">WebSockets</span>
                <span class="tech-tag">TypeScript</span>
                <span class="tech-tag">AI API</span>
            </div>

            <div class="project-item">
                <h3>🔹 Gestor de Novedades y Notificaciones (Spring Boot)</h3>
                <p>Lógica de negocio para crear, actualizar, paginar y enviar notificaciones por email con validaciones avanzadas.</p>
                <span class="tech-tag">Spring Boot</span>
                <span class="tech-tag">Email Service</span>
                <span class="tech-tag">PostgreSQL</span>
            </div>

            <div class="project-item">
                <h3>🔹 Aplicación de Notas en Flutter</h3>
                <p>App CRUD completa con autenticación y datos de prueba para testing eficiente.</p>
                <span class="tech-tag">Flutter</span>
                <span class="tech-tag">Dart</span>
                <span class="tech-tag">SQLite</span>
            </div>

            <div class="project-item">
                <h3>🔹 Gestor de Disponibilidad de Voluntarios</h3>
                <p>Módulo de franjas horarias con reglas de negocio estrictas, validaciones y listas editables.</p>
                <span class="tech-tag">React</span>
                <span class="tech-tag">Validation</span>
                <span class="tech-tag">Estado complejo</span>
            </div>

            <div class="project-item">
                <h3>🔹 Árbol N-ario – Implementación Java MVC</h3>
                <p>Implementación en capas diseñada para uso académico y empresarial con patrones de arquitectura.</p>
                <span class="tech-tag">Java</span>
                <span class="tech-tag">MVC</span>
                <span class="tech-tag">Estructuras de Datos</span>
            </div>

            <div class="project-item">
                <h3>🔹 Aplicación Desktop (C# + SQL Server)</h3>
                <p>Desarrollado para competencia regional con validación robusta y lógica de registro compleja.</p>
                <span class="tech-tag">C#</span>
                <span class="tech-tag">SQL Server</span>
                <span class="tech-tag">Windows Forms</span>
            </div>
        </div>

        <!-- LEARNING -->
        <div class="section">
            <h2>📈 Actualmente Aprendiendo</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🤖 IA Aplicada</h3>
                    <p>Machine Learning y IA para desarrollo práctico e integración en soluciones reales.</p>
                </div>
                <div class="card">
                    <h3>☁️ Cloud & DevOps</h3>
                    <p>Fundamentos de infraestructura cloud, CI/CD y deployment automatizado.</p>
                </div>
                <div class="card">
                    <h3>📊 Data Analytics</h3>
                    <p>Análisis de datos y visualización para insights empresariales.</p>
                </div>
            </div>
        </div>

        <!-- FOOTER -->
        <div class="footer">
            <h2 style="color: #00d4ff; margin-bottom: 20px;">📬 Contacto</h2>
            <div class="social-links">
                <a href="#" class="social-link">📧 Email</a>
                <a href="#" class="social-link">💼 LinkedIn</a>
                <a href="#" class="social-link">🔗 Portfolio</a>
                <a href="#" class="social-link">🐙 GitHub</a>
            </div>
            <p>Siempre abierto a nuevos desafíos y colaboraciones 🚀</p>
        </div>
    </div>
</body>
</html>
