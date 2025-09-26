<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CTP Ing. Carlos Pascua Zúñiga</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    :root {
      --primary: #1e40af;
      --primary-light: #3b82f6;
      --primary-dark: #1e3a8a;
      --secondary: #64748b;
      --background: #f8fafc;
      --surface: #ffffff;
      --text: #1e293b;
      --text-light: #64748b;
      --accent: #10b981;
      --border: #e2e8f0;
      --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
      --shadow-lg: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
    }

    body {
      font-family: 'Inter', 'Segoe UI', sans-serif;
      background: var(--background);
      color: var(--text);
      line-height: 1.6;
      overflow-x: hidden;
    }

    /* Header moderno con gradiente dinámico */
    header {
      background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-light) 100%);
      position: relative;
      overflow: hidden;
      padding: 3rem 1rem;
      text-align: center;
      color: white;
    }

    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.05'%3E%3Ccircle cx='30' cy='30' r='4'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
      animation: float 20s infinite linear;
    }

    @keyframes float {
      0% { transform: translateX(0) translateY(0); }
      100% { transform: translateX(-60px) translateY(-60px); }
    }

    .header-content {
      position: relative;
      z-index: 2;
      max-width: 1200px;
      margin: 0 auto;
    }

    header h1 {
      font-size: clamp(1.8rem, 5vw, 3rem);
      font-weight: 800;
      margin-bottom: 0.5rem;
      text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
    }

    header p {
      font-size: clamp(1rem, 3vw, 1.2rem);
      opacity: 0.95;
      max-width: 600px;
      margin: 0 auto;
      font-weight: 300;
    }

    /* Navegación móvil amigable */
    .nav-container {
      background: rgba(30, 41, 59, 0.95);
      backdrop-filter: blur(10px);
      position: sticky;
      top: 0;
      z-index: 1000;
      padding: 0.5rem 1rem;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }

    nav {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      gap: 0.5rem;
      overflow-x: auto;
      padding: 0.5rem 0;
      scrollbar-width: none;
      -ms-overflow-style: none;
    }

    nav::-webkit-scrollbar {
      display: none;
    }

    nav button {
      background: linear-gradient(135deg, var(--primary-light), var(--primary));
      border: none;
      color: white;
      padding: 0.8rem 1.2rem;
      border-radius: 12px;
      cursor: pointer;
      font-weight: 600;
      font-size: 0.9rem;
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      white-space: nowrap;
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
    }

    nav button::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transition: left 0.5s;
    }

    nav button:hover::before {
      left: 100%;
    }

    nav button:hover {
      transform: translateY(-2px);
      box-shadow: var(--shadow-lg);
    }

    nav button.active {
      background: linear-gradient(135deg, var(--accent), #059669);
      transform: translateY(-2px);
      box-shadow: var(--shadow-lg);
    }

    /* Contenido principal */
    .main-container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 1rem;
    }

    section {
      display: none;
      padding: 2rem 0;
      animation: slideIn 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    }

    section.active {
      display: block;
    }

    @keyframes slideIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .section-header {
      text-align: center;
      margin-bottom: 3rem;
    }

    .section-header h2 {
      color: var(--primary-dark);
      font-size: clamp(2rem, 5vw, 3rem);
      font-weight: 800;
      margin-bottom: 1rem;
      position: relative;
      display: inline-block;
    }

    .section-header h2::after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 50%;
      transform: translateX(-50%);
      width: 80px;
      height: 4px;
      background: linear-gradient(90deg, var(--primary-light), var(--accent));
      border-radius: 2px;
    }

    /* Cards modernos y responsivos */
    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
      margin-top: 2rem;
    }

    .card {
      background: var(--surface);
      border-radius: 20px;
      padding: 2rem;
      box-shadow: var(--shadow);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      border: 1px solid var(--border);
      position: relative;
      overflow: hidden;
    }

    .card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 4px;
      background: linear-gradient(90deg, var(--primary-light), var(--accent));
    }

    .card:hover {
      transform: translateY(-8px);
      box-shadow: var(--shadow-lg);
    }

    .card h3 {
      color: var(--primary-dark);
      font-size: 1.3rem;
      font-weight: 700;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .card p {
      color: var(--text-light);
      line-height: 1.7;
      margin: 0;
    }

    /* Especialidades con íconos mejorados */
    .specialty-card {
      background: var(--surface);
      border-radius: 20px;
      padding: 2rem;
      border-left: 6px solid var(--primary-light);
      box-shadow: var(--shadow);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      position: relative;
      overflow: hidden;
    }

    .specialty-card::before {
      content: '';
      position: absolute;
      top: 0;
      right: 0;
      width: 100px;
      height: 100px;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      opacity: 0.05;
      border-radius: 0 20px 0 50%;
    }

    .specialty-card:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow-lg);
      border-left-color: var(--accent);
    }

    .specialty-card h3 {
      color: var(--primary-dark);
      font-size: 1.2rem;
      font-weight: 700;
      margin-bottom: 1rem;
      display: flex;
      align-items: center;
      gap: 0.8rem;
    }

    /* Galería moderna */
    .gallery {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 1.5rem;
      margin-top: 2rem;
    }

    .gallery-item {
      position: relative;
      border-radius: 16px;
      overflow: hidden;
      aspect-ratio: 1;
      box-shadow: var(--shadow);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .gallery-item:hover {
      transform: scale(1.05);
      box-shadow: var(--shadow-lg);
    }

    .gallery img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .gallery-item:hover img {
      transform: scale(1.1);
    }

    /* Horarios responsivos */
    .schedule-tabs {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      margin-bottom: 2rem;
      justify-content: center;
    }

    .schedule-tabs button {
      padding: 1rem 1.5rem;
      border: 2px solid var(--border);
      border-radius: 12px;
      background: var(--surface);
      cursor: pointer;
      font-weight: 600;
      color: var(--text);
      transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
      font-size: 0.9rem;
    }

    .schedule-tabs button:hover {
      border-color: var(--primary-light);
      color: var(--primary-light);
    }

    .schedule-tabs button.active {
      background: var(--primary-light);
      color: white;
      border-color: var(--primary-light);
      box-shadow: var(--shadow);
    }

    .schedule-content {
      display: none;
      background: var(--surface);
      border-radius: 16px;
      overflow: hidden;
      box-shadow: var(--shadow);
    }

    .schedule-content.active {
      display: block;
      animation: fadeIn 0.4s ease-in-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    .table-container {
      overflow-x: auto;
      border-radius: 16px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 600px;
      font-size: 0.9rem;
    }

    th, td {
      padding: 1rem;
      text-align: center;
      border-bottom: 1px solid var(--border);
    }

    th {
      background: var(--primary-dark);
      color: white;
      font-weight: 600;
      position: sticky;
      top: 0;
    }

    td {
      background: var(--surface);
      transition: background-color 0.2s;
    }

    tr:hover td {
      background: rgba(59, 130, 246, 0.05);
    }

    /* Información de contacto moderna */
    .contact-info {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1.5rem;
      margin-top: 2rem;
    }

    .contact-card {
      background: var(--surface);
      padding: 2rem;
      border-radius: 20px;
      text-align: center;
      box-shadow: var(--shadow);
      transition: transform 0.3s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .contact-card:hover {
      transform: translateY(-5px);
    }

    .contact-icon {
      width: 60px;
      height: 60px;
      background: linear-gradient(135deg, var(--primary-light), var(--accent));
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 0 auto 1rem;
      font-size: 1.5rem;
    }

    /* Footer moderno */
    footer {
      background: linear-gradient(135deg, var(--text) 0%, #0f172a 100%);
      color: white;
      padding: 3rem 1rem 1.5rem;
      margin-top: 4rem;
      position: relative;
      overflow: hidden;
    }

    footer::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 4px;
      background: linear-gradient(90deg, var(--primary-light), var(--accent));
    }

    .footer-content {
      max-width: 1200px;
      margin: 0 auto;
      text-align: center;
    }

    footer p {
      margin: 0.5rem 0;
      opacity: 0.9;
    }

    /* Animación de entrada */
    .fade-in {
      opacity: 0;
      animation: fadeInUp 0.6s ease-out forwards;
    }

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

    /* Responsive mejorado */
    @media (max-width: 768px) {
      header {
        padding: 2rem 1rem;
      }

      .nav-container {
        padding: 0.5rem;
      }

      nav {
        gap: 0.3rem;
      }

      nav button {
        padding: 0.6rem 1rem;
        font-size: 0.8rem;
      }

      section {
        padding: 1.5rem 0;
      }

      .section-header {
        margin-bottom: 2rem;
      }

      .card-grid {
        grid-template-columns: 1fr;
        gap: 1rem;
      }

      .card {
        padding: 1.5rem;
      }

      .gallery {
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        gap: 1rem;
      }

      .schedule-tabs {
        gap: 0.5rem;
      }

      .schedule-tabs button {
        padding: 0.8rem 1rem;
        font-size: 0.8rem;
      }

      th, td {
        padding: 0.8rem 0.5rem;
        font-size: 0.8rem;
      }
    }

    @media (max-width: 480px) {
      .main-container {
        padding: 0 0.5rem;
      }

      header {
        padding: 1.5rem 0.5rem;
      }

      .card {
        padding: 1rem;
      }

      .specialty-card {
        padding: 1rem;
      }

      .contact-card {
        padding: 1.5rem;
      }
    }

    /* Indicador de carga suave */
    .loading {
      opacity: 0.5;
      transition: opacity 0.3s ease;
    }

    /* Mejoras de accesibilidad */
    @media (prefers-reduced-motion: reduce) {
      * {
        animation-duration: 0.01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: 0.01ms !important;
      }
    }

    /* Focus states para accesibilidad */
    button:focus,
    nav button:focus {
      outline: 3px solid var(--accent);
      outline-offset: 2px;
    }

    /* Scrollbar personalizada */
    ::-webkit-scrollbar {
      width: 8px;
    }

    ::-webkit-scrollbar-track {
      background: var(--background);
    }

    ::-webkit-scrollbar-thumb {
      background: var(--primary-light);
      border-radius: 4px;
    }

    ::-webkit-scrollbar-thumb:hover {
      background: var(--primary-dark);
    }
  </style>
</head>
<body>
  <header>
    <div class="header-content fade-in">
      <h1>🏫 Colegio Técnico Profesional<br>Ing. Carlos Pascua Zúñiga</h1>
      <p>✨ Excelencia académica y formación técnica integral en San Rafael, Costa Rica</p>
    </div>
  </header>

  <div class="nav-container">
    <nav>
      <button onclick="showSection('presentacion')" class="active">🏫 Inicio</button>
      <button onclick="showSection('valores')">🌟 Valores</button>
      <button onclick="showSection('mision')">🎯 Misión</button>
      <button onclick="showSection('especialidades')">📚 Carreras</button>
      <button onclick="showSection('horarios')">⏰ Horarios</button>
      <button onclick="showSection('galeria')">🖼️ Galería</button>
      <button onclick="showSection('contacto')">📞 Contacto</button>
    </nav>
  </div>

  <div class="main-container">
    <!-- Presentación -->
    <section id="presentacion" class="active">
      <div class="section-header">
        <h2>Bienvenidos a Nuestro Colegio</h2>
      </div>
      
      <div class="card-grid">
        <div class="card fade-in">
          <h3>🎓 Institución de Excelencia</h3>
          <p>El Colegio Técnico Profesional Ing. Carlos Pascua Zúñiga es una institución educativa pública que contribuye a la formación y desarrollo integral de nuestros estudiantes en un ambiente de inclusión y responsabilidad ambiental.</p>
        </div>
        
        <div class="card fade-in">
          <h3>🌱 Formación Integral</h3>
          <p>Nos enfocamos en desarrollar las competencias técnicas, valores morales y habilidades sociales que nuestros estudiantes necesitan para ser ciudadanos exitosos y comprometidos con el país.</p>
        </div>
        
        <div class="card fade-in">
          <h3>💼 Preparación Profesional</h3>
          <p>Ofrecemos especialidades técnicas de alta calidad que preparan a nuestros graduados para ingresar al mundo laboral con las mejores herramientas y conocimientos.</p>
        </div>
      </div>
    </section>

    <!-- Valores -->
    <section id="valores">
      <div class="section-header">
        <h2>Nuestros Valores Institucionales</h2>
      </div>
      
      <div class="card-grid">
        <div class="card fade-in">
          <h3>📚 Formativos</h3>
          <p>Cultivamos la disciplina, compromiso, orden, responsabilidad, puntualidad, esfuerzo y constancia como pilares fundamentales del crecimiento personal y académico.</p>
        </div>
        
        <div class="card fade-in">
          <h3>💎 Morales</h3>
          <p>Promovemos el honor, sinceridad, honestidad, verdad y respeto como valores esenciales para la formación de ciudadanos íntegros.</p>
        </div>
        
        <div class="card fade-in">
          <h3>🙏 Espirituales</h3>
          <p>Fomentamos la justicia, amor, perdón y fe como elementos que enriquecen el espíritu y fortalecen el carácter de nuestros estudiantes.</p>
        </div>
        
        <div class="card fade-in">
          <h3>🤝 Sociales</h3>
          <p>Desarrollamos la solidaridad, cooperación, tolerancia, cortesía, equidad, igualdad, convivencia e inclusión para una sociedad mejor.</p>
        </div>
        
        <div class="card fade-in">
          <h3>🌍 Ambientales</h3>
          <p>Promovemos la protección, reciclaje, equilibrio y uso racional de los recursos naturales para un futuro sostenible.</p>
        </div>
      </div>
    </section>

    <!-- Misión & Visión -->
    <section id="mision">
      <div class="section-header">
        <h2>Nuestra Identidad Institucional</h2>
      </div>
      
      <div class="card-grid">
        <div class="card fade-in">
          <h3>🎯 Misión</h3>
          <p>Somos una institución educativa académica pública comprometida con la formación y desarrollo moral, espiritual, intelectual, cultural, social y laboral de nuestros estudiantes, en un espacio de responsabilidad ambiental e inclusión de la diversidad.</p>
        </div>
        
        <div class="card fade-in">
          <h3>🌟 Visión</h3>
          <p>Aspiramos a ser reconocidos como una institución educativa inclusiva y comprometida, enfocada en la formación integral y el desarrollo completo de nuestros estudiantes, formando ciudadanos críticos, comprometidos con el país y profesionalmente exitosos.</p>
        </div>
      </div>
    </section>

    <!-- Especialidades -->
    <section id="especialidades">
      <div class="section-header">
        <h2>Nuestras Especialidades Técnicas</h2>
      </div>
      
      <div class="card-grid">
        <div class="specialty-card fade-in">
          <h3>💻 Desarrollo Web</h3>
          <p>Formación completa en diseño y programación web, incluyendo frontend, backend, bases de datos y desarrollo de aplicaciones modernas. Preparamos desarrolladores listos para la industria tecnológica.</p>
        </div>
        
        <div class="specialty-card fade-in">
          <h3>🏦 Banca y Finanzas</h3>
          <p>Preparación integral en operaciones bancarias, productos financieros, servicios contables y gestión de riesgos financieros para el sector bancario y financiero nacional.</p>
        </div>
        
        <div class="specialty-card fade-in">
          <h3>📊 Contabilidad</h3>
          <p>Capacitación completa en registros contables, elaboración de estados financieros, auditoría y análisis financiero para empresas de todos los sectores.</p>
        </div>
        
        <div class="specialty-card fade-in">
          <h3>🏗️ Construcción Civil</h3>
          <p>Formación en dibujo técnico, topografía, planificación y supervisión de proyectos de construcción, incluyendo conocimientos de materiales y técnicas constructivas.</p>
        </div>
        
        <div class="specialty-card fade-in">
          <h3>📐 Dibujo Técnico</h3>
          <p>Desarrollo de habilidades en elaboración de planos técnicos y diseño asistido por computadora para proyectos de ingeniería y arquitectura.</p>
        </div>
        
        <div class="specialty-card fade-in">
          <h3>⚙️ Gestión de Calidad</h3>
          <p>Enfoque especializado en procesos de mejora continua, implementación de normativas de calidad internacional y control de producción en diversos sectores industriales.</p>
        </div>
      </div>
    </section>

    <!-- Horarios -->
    <section id="horarios">
      <div class="section-header">
        <h2>Horarios Tecnicos</h2>
      </div>
      
      <div class="schedule-tabs">
        <button onclick="showSchedule('web')" class="active">Desarrollo Web</button>
        <button onclick="showSchedule('banca')">Banca y Finanzas</button>
        <button onclick="showSchedule('conta')">Contabilidad</button>
        <button onclick="showSchedule('civil')">Construcción Civil</button>
        <button onclick="showSchedule('dibujo')">Dibujo Técnico</button>
        <button onclick="showSchedule('calidad')">Gestión de Calidad</button>
      </div>

      <div id="web" class="schedule-content active">
        <div class="table-container">
          <table>
            <thead>
              <tr>
                <th>⏰ Hora</th>
                <th>🅻 Lunes</th>
                <th>🅼 Martes</th>
                <th>🅼 Miércoles</th>
                <th>🅹 Jueves</th>
                <th>🆅 Viernes</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td><strong>7:00 - 9:00</strong></td>
                <td>Programación</td>
                <td>Matemáticas</td>
                <td>HTML/CSS</td>
                <td>JavaScript</td>
                <td>Base de Datos</td>
              </tr>
              <tr>
                <td><strong>9:00 - 11:00</strong></td>
                <td>Diseño Web</td>
                <td>Inglés Técnico</td>
                <td>Frameworks</td>
                <td>Proyecto Final</td>
                <td>Testing</td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>

      <div id="banca" class="schedule-content">
        <div class="card">
          <h3>📅 Horario de Banca y Finanzas</h3>
          <p>Los horarios detallados para la especialidad de Banca y Finanzas estarán disponibles próximamente. Contáctanos para más información sobre esta carrera técnica.</p>
        </div>
      </div>

      <div id="conta" class="schedule-content">
        <div class="card">
          <h3>📅 Horario de Contabilidad</h3>
          <p>Los horarios detallados para la especialidad de Contabilidad estarán disponibles próximamente. Contáctanos para más información sobre esta carrera técnica.</p>
        </div>
      </div>

      <div id="civil" class="schedule-content">
        <div class="card">
          <h3>📅 Horario de Construcción Civil</h3>
          <p>Los horarios detallados para la especialidad de Construcción Civil estarán disponibles próximamente. Contáctanos para más información sobre esta carrera técnica.</p>
        </div>
      </div>

      <div id="dibujo" class="schedule-content">
        <div class="card">
          <h3>📅 Horario de Dibujo Técnico</h3>
          <p>Los horarios detallados para la especialidad de Dibujo Técnico estarán disponibles próximamente. Contáctanos para más información sobre esta carrera técnica.</p>
        </div>
      </div>

      <div id="calidad" class="schedule-content">
        <div class="card">
          <h3>📅 Horario de Gestión de Calidad</h3>
          <p>Los horarios detallados para la especialidad de Gestión de Calidad estarán disponibles próximamente. Contáctanos para más información sobre esta carrera técnica.</p>
        </div>
      </div>
    </section>

    <!-- Sección Formulario de Matrícula -->
        <section id="formulario-matricula" class="section">
            <h2 class="section-title">FORMULARIO DE MATRÍCULA</h2>
            
            <div class="enrollment-center">
                <h3 id="selected-specialty-title">Selecciona una especialidad</h3>
                <p class="intro-text" id="selected-specialty-desc">
                    Completa el formulario para aplicar a la especialidad seleccionada.
                </p>
                
                <form class="enrollment-form" id="enrollment-form">
                    <div class="form-section">
                        <h4>📋 Datos Personales</h4>
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="nombre">Nombre completo *</label>
                                <input type="text" id="nombre" name="nombre" required>
                            </div>
                            <div class="form-group">
                                <label for="cedula">Cédula de identidad *</label>
                                <input type="text" id="cedula" name="cedula" required>
                            </div>
                            <div class="form-group">
                                <label for="fecha_nacimiento">Fecha de nacimiento *</label>
                                <input type="date" id="fecha_nacimiento" name="fecha_nacimiento" required>
                            </div>
                            <div class="form-group">
                                <label for="telefono">Teléfono *</label>
                                <input type="tel" id="telefono" name="telefono" required>
                            </div>
                            <div class="form-group">
                                <label for="email">Correo electrónico *</label>
                                <input type="email" id="email" name="email" required>
                            </div>
                            <div class="form-group">
                                <label for="direccion">Dirección completa *</label>
                                <textarea id="direccion" name="direccion" rows="3" required></textarea>
                            </div>
                        </div>
                    </div>

                    <div class="form-section">
                        <h4>🎓 Datos Académicos</h4>
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="colegio_anterior">Colegio de procedencia *</label>
                                <input type="text" id="colegio_anterior" name="colegio_anterior" required>
                            </div>
                            <div class="form-group">
                                <label for="promedio">Promedio del año anterior *</label>
                                <input type="number" id="promedio" name="promedio" min="0" max="100" step="0.01" required>
                            </div>
                            <div class="form-group">
                                <label for="especialidad_interes">Especialidad de interés *</label>
                                <select id="especialidad_interes" name="especialidad_interes" required>
                                    <option value="">Selecciona una especialidad</option>
                                    <option value="desarrollo-web">💻 Desarrollo Web</option>
                                    <option value="banca-finanzas">🏦 Banca y Finanzas</option>
                                    <option value="contabilidad">📊 Contabilidad</option>
                                    <option value="gestion-administrativa">📋 Gestión Administrativa</option>
                                    <option value="construccion-civil">🏗 Construcción Civil</option>
                                </select>
                            </div>
                            <div class="form-group">
                                <label for="experiencia_tecnica">Experiencia técnica previa</label>
                                <textarea id="experiencia_tecnica" name="experiencia_tecnica" rows="3" placeholder="Describe cualquier experiencia técnica o cursos relacionados"></textarea>
                            </div>
                        </div>
                    </div>

                    <div class="form-section">
                        <h4>👨‍👩‍👧‍👦 Datos de Emergencia</h4>
                        <div class="form-grid">
                            <div class="form-group">
                                <label for="contacto_emergencia">Nombre del contacto de emergencia *</label>
                                <input type="text" id="contacto_emergencia" name="contacto_emergencia" required>
                            </div>
                            <div class="form-group">
                                <label for="telefono_emergencia">Teléfono de emergencia *</label>
                                <input type="tel" id="telefono_emergencia" name="telefono_emergencia" required>
                            </div>
                            <div class="form-group">
                                <label for="parentesco">Parentesco *</label>
                                <select id="parentesco" name="parentesco" required>
                                    <option value="">Selecciona parentesco</option>
                                    <option value="padre">Padre</option>
                                    <option value="madre">Madre</option>
                                    <option value="tutor">Tutor legal</option>
                                    <option value="otro">Otro</option>
                                </select>
                            </div>
                        </div>
                    </div>

                    <div class="form-section">
                        <h4>📄 Documentos Requeridos</h4>
                        <div class="documents-checklist">
                            <label class="checkbox-item">
                                <input type="checkbox" name="documentos[]" value="cedula" required>
                                <span>Cédula de identidad (original y copia)</span>
                            </label>
                            <label class="checkbox-item">
                                <input type="checkbox" name="documentos[]" value="certificado" required>
                                <span>Certificado de notas del año anterior</span>
                            </label>
                            <label class="checkbox-item">
                                <input type="checkbox" name="documentos[]" value="domicilio" required>
                                <span>Comprobante de domicilio</span>
                            </label>
                            <label class="checkbox-item">
                                <input type="checkbox" name="documentos[]" value="foto" required>
                                <span>Fotografía tamaño pasaporte</span>
                            </label>
                        </div>
                    </div>

                    <div class="form-actions">
                        <button type="button" class="btn-secondary" onclick="showSection('matriculas')">← Volver a Matrículas</button>
                        <button type="submit" class="btn-primary">Enviar Solicitud de Matrícula</button>
                    </div>
                </form>
            </div>
        </section>

    <!-- Galería -->
    <section id="galeria">
      <div class="section-header">
        <h2>Nuestra Galería Institucional</h2>
      </div>
      
      <div class="gallery">
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSZFiE-WaQw2nx6APUusCX6JX2wC3aY0-2AxtUnQiQ&usqp=CAU" alt="Instalaciones educativas del colegio">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTjNkIBGJWMyylEUc-UydK7hJUBAiF46qpOjQ&s" alt="Fachada principal del colegio">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRucxTXYdGyk1p5h9CxeZ6TF6Lx6Bp4HjQaaA&s" alt="Laboratorio de computación">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSDL6M_4SQjsumGJv3_Z851aiO5QYuOP3f73DySX1E&usqp=CAU" alt="Aulas modernas y equipadas">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSIQnGRW54BItdXCLvxqi_HMI1e1qQsAnIlBw&s" alt="Estudiantes en actividades académicas">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTth86FYes52DKYphZ1Q3JcqQ_tc_b5SPtyZg&s" alt="Talleres de especialidades técnicas">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSrpB2hTOFhJI3QfWmXQEJAPVehBnRz8vkEuxmMQwY&usqp=CAU" alt="Actividades estudiantiles y culturales">
        </div>
        <div class="gallery-item fade-in">
          <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRq0Mur_mHmN_GQIfxXNbvF-Yrx6eY-wqfxE-V19qs&usqp=CAU" alt="Espacios de aprendizaje colaborativo">
        </div>
      </div>
    </section>

    <!-- Contacto -->
    <section id="contacto">
      <div class="section-header">
        <h2>Contáctanos</h2>
      </div>
      
      <div class="contact-info">
        <div class="contact-card fade-in">
          <div class="contact-icon">🏢</div>
          <h3>Ubicación</h3>
          <p>San Rafael, Costa Rica</p>
          <p>Colegio Técnico Profesional<br>Ing. Carlos Pascua Zúñiga</p>
        </div>
        
        <div class="contact-card fade-in">
          <div class="contact-icon">📞</div>
          <h3>Teléfono</h3>
          <p><strong>2237 2710</strong></p>
          <p>Horario de atención:<br>Lunes a Viernes<br>7:00 AM - 4:00 PM</p>
        </div>
        
        <div class="contact-card fade-in">
          <div class="contact-icon">📧</div>
          <h3>Email</h3>
          <p><strong>lic.ingcarlospascua@mep.go.cr</strong></p>
          <p>Para consultas académicas<br>y administrativas</p>
        </div>
      </div>
    </section>
  </div>

  <footer>
    <div class="footer-content">
      <p><strong>&copy; 2025 Colegio Técnico Profesional Ing. Carlos Pascua Zúñiga</strong></p>
      <p>🏫 San Rafael, Costa Rica | 📞 2237 2710 | 📧 lic.ingcarlospascua@mep.go.cr</p>
      <p>✨ Formando el futuro de Costa Rica con excelencia técnica y valores sólidos</p>
    </div>
  </footer>

  <script>
    // Función para mostrar secciones
    function showSection(sectionId) {
      // Ocultar todas las secciones
      document.querySelectorAll('section').forEach(section => {
        section.classList.remove('active');
      });
      
      // Mostrar la sección seleccionada
      document.getElementById(sectionId).classList.add('active');
      
      // Actualizar botones de navegación
      document.querySelectorAll('nav button').forEach(button => {
        button.classList.remove('active');
      });
      
      // Marcar el botón activo
      event.target.classList.add('active');
      
      // Scroll suave al inicio de la sección
      document.querySelector('.main-container').scrollIntoView({
        behavior: 'smooth',
        block: 'start'
      });
    }

    // Función para mostrar horarios
    function showSchedule(scheduleId) {
      // Ocultar todos los horarios
      document.querySelectorAll('.schedule-content').forEach(content => {
        content.classList.remove('active');
      });
      
      // Mostrar el horario seleccionado
      document.getElementById(scheduleId).classList.add('active');
      
      // Actualizar botones de horarios
      document.querySelectorAll('.schedule-tabs button').forEach(button => {
        button.classList.remove('active');
      });
      
      // Marcar el botón activo
      event.target.classList.add('active');
    }

    // Animaciones al cargar la página
    document.addEventListener('DOMContentLoaded', function() {
      // Agregar clase fade-in a elementos con retraso
      const fadeElements = document.querySelectorAll('.fade-in');
      fadeElements.forEach((element, index) => {
        element.style.animationDelay = `${index * 0.1}s`;
      });

      // Smooth scrolling para la navegación
      const navButtons = document.querySelectorAll('nav button');
      navButtons.forEach(button => {
        button.addEventListener('click', function(e) {
          e.preventDefault();
          
          // Agregar efecto de carga suave
          button.classList.add('loading');
          setTimeout(() => {
            button.classList.remove('loading');
          }, 300);
        });
      });

      // Mejorar la experiencia táctil en móviles
      if ('ontouchstart' in window) {
        document.body.classList.add('touch-device');
      }
    });

    // Función para mejorar la navegación por teclado (accesibilidad)
    document.addEventListener('keydown', function(e) {
      if (e.key === 'Enter' && e.target.tagName === 'BUTTON') {
        e.target.click();
      }
    });

    // Lazy loading para imágenes (mejora el rendimiento)
    if ('IntersectionObserver' in window) {
      const imageObserver = new IntersectionObserver((entries, observer) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            const img = entry.target;
            img.style.opacity = '1';
            observer.unobserve(img);
          }
        });
      });

      document.querySelectorAll('.gallery img').forEach(img => {
        img.style.opacity = '0';
        img.style.transition = 'opacity 0.3s ease';
        imageObserver.observe(img);
      });
    }

    // Agregar efecto parallax sutil al header (opcional)
    window.addEventListener('scroll', function() {
      const scrolled = window.pageYOffset;
      const rate = scrolled * -0.5;
      const header = document.querySelector('header::before');
      
      if (header) {
        header.style.transform = `translate3d(0, ${rate}px, 0)`;
      }
    });

    // Función para detectar si el usuario prefiere menos movimiento
    const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
    
    if (prefersReducedMotion) {
      // Desactivar animaciones complejas para usuarios que prefieren menos movimiento
      document.documentElement.style.setProperty('--animation-duration', '0.01ms');
    }
  </script>
</body>
</html>
