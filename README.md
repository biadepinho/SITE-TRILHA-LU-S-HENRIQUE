# SITE-ESPORTE-ATIVIDADE-FISICA-EXERCICIO-FISICO
Sobre esporte X atividade física X exercício físico


<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Movimento & Vida - Esporte, Atividade Física e Exercício</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;600;700&display=swap');
        
        :root {
            --gold: #FFD700;
            --dark-gold: #B8860B;
            --black: #000000;
            --dark-gray: #1a1a1a;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #000000 0%, #1a1a1a 100%);
            color: white;
            overflow-x: hidden;
        }

        .orbitron {
            font-family: 'Orbitron', monospace;
        }

        .gold-glow {
            color: var(--gold);
            text-shadow: 0 0 20px var(--gold), 0 0 40px var(--gold);
            animation: pulse-gold 2s ease-in-out infinite alternate;
        }

        @keyframes pulse-gold {
            0% { text-shadow: 0 0 20px var(--gold), 0 0 40px var(--gold); }
            100% { text-shadow: 0 0 30px var(--gold), 0 0 60px var(--gold), 0 0 80px var(--gold); }
        }

        .page {
            min-height: 100vh;
            display: none;
            opacity: 0;
            transform: translateY(50px);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }

        .page.active {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }

        .sport-transition {
            animation: sportBounce 0.8s ease-out;
        }

        @keyframes sportBounce {
            0% { transform: scale(0.8) rotate(-5deg); }
            50% { transform: scale(1.1) rotate(2deg); }
            100% { transform: scale(1) rotate(0deg); }
        }

        .activity-transition {
            animation: activityFlow 0.8s ease-out;
        }

        @keyframes activityFlow {
            0% { transform: translateX(-100%) skewX(-10deg); }
            100% { transform: translateX(0) skewX(0deg); }
        }

        .exercise-transition {
            animation: exercisePump 0.8s ease-out;
        }

        @keyframes exercisePump {
            0%, 20%, 40%, 60%, 80% { transform: scaleY(0.8); }
            10%, 30%, 50%, 70%, 90% { transform: scaleY(1.2); }
            100% { transform: scaleY(1); }
        }

        .nav-button {
            background: linear-gradient(45deg, transparent, var(--gold));
            border: 2px solid var(--gold);
            color: var(--gold);
            padding: 15px 30px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .nav-button:hover {
            background: var(--gold);
            color: black;
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.3);
        }

        .nav-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .nav-button:hover::before {
            left: 100%;
        }

        .hero-section {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            background: radial-gradient(circle at center, rgba(255,215,0,0.1) 0%, transparent 70%);
        }

        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        .floating-element {
            position: absolute;
            opacity: 0.1;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(180deg); }
        }

        .section-card {
            background: rgba(26, 26, 26, 0.8);
            border: 1px solid var(--gold);
            border-radius: 20px;
            padding: 40px;
            margin: 20px 0;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        .section-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(255, 215, 0, 0.2);
            border-color: var(--gold);
        }

        .timeline {
            position: relative;
            padding: 20px 0;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(to bottom, var(--gold), transparent);
        }

        .timeline-item {
            position: relative;
            margin: 40px 0;
            padding: 20px;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 20px;
            width: 20px;
            height: 20px;
            background: var(--gold);
            border-radius: 50%;
            transform: translateX(-50%);
            box-shadow: 0 0 20px var(--gold);
        }

        .back-button {
            position: fixed;
            top: 30px;
            left: 30px;
            z-index: 1000;
            background: rgba(0,0,0,0.8);
            border: 2px solid var(--gold);
            color: var(--gold);
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .back-button:hover {
            background: var(--gold);
            color: black;
        }

        .inspiration-card {
            background: linear-gradient(135deg, rgba(255,215,0,0.1), rgba(0,0,0,0.8));
            border: 2px solid var(--gold);
            border-radius: 15px;
            padding: 30px;
            margin: 20px 0;
            text-align: center;
            transition: all 0.3s ease;
        }

        .inspiration-card:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 30px rgba(255,215,0,0.3);
        }

        .difference-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin: 40px 0;
        }

        .difference-card {
            background: rgba(26,26,26,0.9);
            border: 2px solid var(--gold);
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .difference-card:hover {
            transform: translateY(-5px);
            border-color: var(--gold);
            box-shadow: 0 10px 25px rgba(255,215,0,0.2);
        }

        .steps-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }

        .step-card {
            background: rgba(26,26,26,0.8);
            border-left: 4px solid var(--gold);
            padding: 20px;
            border-radius: 10px;
            transition: all 0.3s ease;
        }

        .step-card:hover {
            background: rgba(255,215,0,0.1);
            transform: translateX(10px);
        }

        @media (max-width: 768px) {
            .nav-button {
                padding: 12px 20px;
                font-size: 14px;
            }
            
            .section-card {
                padding: 20px;
                margin: 10px;
            }
            
            .timeline::before {
                left: 20px;
            }
            
            .timeline-item::before {
                left: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Página Principal -->
    <div id="home" class="page active">
        <div class="floating-elements">
            <div class="floating-element" style="top: 10%; left: 10%; font-size: 60px;">⚽</div>
            <div class="floating-element" style="top: 20%; right: 15%; font-size: 50px; animation-delay: -2s;">🏃‍♂️</div>
            <div class="floating-element" style="top: 60%; left: 20%; font-size: 40px; animation-delay: -4s;">🏋️‍♀️</div>
            <div class="floating-element" style="top: 70%; right: 10%; font-size: 55px; animation-delay: -1s;">🏀</div>
            <div class="floating-element" style="top: 40%; right: 30%; font-size: 45px; animation-delay: -3s;">🎾</div>
        </div>

        <div class="hero-section">
            <div class="max-w-6xl mx-auto px-6">
                <h1 class="orbitron text-6xl md:text-8xl font-black gold-glow mb-8">
                    MOVIMENTO & VIDA
                </h1>
                <p class="text-xl md:text-2xl mb-12 max-w-4xl mx-auto leading-relaxed">
                    Descubra o poder transformador do <span class="gold-glow">esporte</span>, 
                    da <span class="gold-glow">atividade física</span> e do <span class="gold-glow">exercício físico</span> 
                    em sua jornada de superação
                </p>
                
                <div class="flex flex-wrap justify-center gap-6">
                    <button onclick="showPage('sport')" class="nav-button sport-btn">
                        🏆 ESPORTE
                    </button>
                    <button onclick="showPage('activity')" class="nav-button activity-btn">
                        🏃‍♂️ ATIVIDADE FÍSICA
                    </button>
                    <button onclick="showPage('exercise')" class="nav-button exercise-btn">
                        💪 EXERCÍCIO FÍSICO
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Página Esporte -->
    <div id="sport" class="page">
        <button onclick="showPage('home')" class="back-button">← Voltar</button>
        
        <div class="max-w-6xl mx-auto px-6 py-20">
            <h1 class="orbitron text-5xl md:text-7xl font-black gold-glow text-center mb-12">
                🏆 ESPORTE
            </h1>

            <!-- História -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">📚 História do Esporte</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Antiguidade (3000 a.C.)</h3>
                        <p>Primeiros registros de competições esportivas no Egito e Mesopotâmia. Corridas, lutas e jogos com bola eram praticados como rituais religiosos e preparação militar.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Grécia Antiga (776 a.C.)</h3>
                        <p>Nascimento dos Jogos Olímpicos em Olímpia. O esporte ganha caráter competitivo e de excelência física, mental e espiritual.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Era Moderna (1896)</h3>
                        <p>Renascimento dos Jogos Olímpicos modernos por Pierre de Coubertin. O esporte se torna global e profissional.</p>
                    </div>
                </div>
            </div>

            <!-- Diferenças -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🔍 Diferenças Fundamentais</h2>
                <div class="difference-grid">
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">🏆 ESPORTE</h3>
                        <ul class="text-left space-y-2">
                            <li>• Regras oficiais e padronizadas</li>
                            <li>• Competição organizada</li>
                            <li>• Federações e confederações</li>
                            <li>• Técnica específica refinada</li>
                            <li>• Objetivo: vencer e superar</li>
                        </ul>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">🏃‍♂️ ATIVIDADE FÍSICA</h3>
                        <ul class="text-left space-y-2">
                            <li>• Movimento corporal geral</li>
                            <li>• Sem regras rígidas</li>
                            <li>• Flexibilidade de prática</li>
                            <li>• Foco no bem-estar</li>
                            <li>• Objetivo: saúde e prazer</li>
                        </ul>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">💪 EXERCÍCIO FÍSICO</h3>
                        <ul class="text-left space-y-2">
                            <li>• Planejamento estruturado</li>
                            <li>• Objetivos específicos</li>
                            <li>• Progressão controlada</li>
                            <li>• Métodos científicos</li>
                            <li>• Objetivo: condicionamento</li>
                        </ul>
                    </div>
                </div>
            </div>

            <!-- Importância -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">⭐ Importância do Esporte</h2>
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Desenvolvimento Físico</h3>
                        <p>Melhora coordenação, força, resistência, flexibilidade e habilidades motoras específicas.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Desenvolvimento Mental</h3>
                        <p>Desenvolve disciplina, foco, estratégia, tomada de decisão rápida e controle emocional.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Desenvolvimento Social</h3>
                        <p>Ensina trabalho em equipe, respeito, fair play, liderança e comunicação.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Desenvolvimento Pessoal</h3>
                        <p>Constrói autoestima, confiança, perseverança e capacidade de superar desafios.</p>
                    </div>
                </div>
            </div>

            <!-- Como Começar -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🚀 Como Começar no Esporte</h2>
                <div class="steps-container">
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">1. Escolha seu Esporte</h3>
                        <p>Identifique suas preferências, habilidades naturais e objetivos pessoais.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">2. Encontre um Local</h3>
                        <p>Procure clubes, academias, escolas ou grupos comunitários na sua região.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">3. Equipamentos Básicos</h3>
                        <p>Invista gradualmente em equipamentos adequados e de qualidade.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">4. Orientação Profissional</h3>
                        <p>Busque um treinador qualificado para aprender técnicas corretas.</p>
                    </div>
                </div>
            </div>

            <!-- Exemplo de Superação -->
            <div class="inspiration-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🌟 Exemplo de Superação</h2>
                <div class="max-w-4xl mx-auto">
                    <h3 class="text-2xl font-bold mb-4 text-yellow-400">Vinícius Júnior - Real Madrid</h3>
                    <p class="text-lg leading-relaxed mb-6">
                        Nascido em São Gonçalo, Rio de Janeiro, Vinícius Jr. superou as dificuldades da periferia através do futebol. 
                        Começou no Flamengo aos 10 anos, enfrentou críticas por sua finalização, mas nunca desistiu. 
                        Sua dedicação, trabalho árduo e mentalidade vencedora o levaram ao Real Madrid, onde se tornou 
                        um dos principais jogadores do mundo, conquistando Champions League e sendo exemplo de que 
                        o esporte pode transformar vidas e quebrar barreiras sociais.
                    </p>
                    <div class="text-yellow-400 font-bold text-xl">
                        "O esporte me deu tudo: disciplina, oportunidades e a chance de realizar meus sonhos."
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Página Atividade Física -->
    <div id="activity" class="page">
        <button onclick="showPage('home')" class="back-button">← Voltar</button>
        
        <div class="max-w-6xl mx-auto px-6 py-20">
            <h1 class="orbitron text-5xl md:text-7xl font-black gold-glow text-center mb-12">
                🏃‍♂️ ATIVIDADE FÍSICA
            </h1>

            <!-- História -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">📚 História da Atividade Física</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Era Primitiva</h3>
                        <p>Atividade física era essencial para sobrevivência: caça, coleta, migração e defesa. Movimento natural e funcional.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Civilizações Antigas</h3>
                        <p>Chineses desenvolveram Tai Chi, indianos criaram Yoga. Atividade física como medicina preventiva e espiritual.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Século XX</h3>
                        <p>Revolução industrial reduz atividade física. Surge consciência sobre importância do movimento para saúde.</p>
                    </div>
                </div>
            </div>

            <!-- Diferenças -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🔍 Características da Atividade Física</h2>
                <div class="difference-grid">
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">🌟 FLEXIBILIDADE</h3>
                        <p>Pode ser praticada em qualquer lugar, a qualquer hora, sem equipamentos especiais ou regras rígidas.</p>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">🎯 ACESSIBILIDADE</h3>
                        <p>Adequada para todas as idades, níveis de condicionamento e limitações físicas.</p>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">💝 BEM-ESTAR</h3>
                        <p>Foco principal na saúde, prazer, qualidade de vida e prevenção de doenças.</p>
                    </div>
                </div>
            </div>

            <!-- Importância -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">⭐ Benefícios da Atividade Física</h2>
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Saúde Cardiovascular</h3>
                        <p>Fortalece o coração, melhora circulação, reduz pressão arterial e colesterol.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Saúde Mental</h3>
                        <p>Libera endorfinas, reduz estresse, ansiedade e depressão. Melhora humor e autoestima.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Controle de Peso</h3>
                        <p>Queima calorias, acelera metabolismo e ajuda na manutenção do peso ideal.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Longevidade</h3>
                        <p>Previne doenças crônicas, mantém independência funcional e aumenta expectativa de vida.</p>
                    </div>
                </div>
            </div>

            <!-- Como Começar -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🚀 Como Começar Atividade Física</h2>
                <div class="steps-container">
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">1. Comece Devagar</h3>
                        <p>Inicie com 10-15 minutos diários de caminhada ou atividades leves.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">2. Escolha o que Gosta</h3>
                        <p>Dança, caminhada, natação, ciclismo - o importante é sentir prazer.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">3. Crie Rotina</h3>
                        <p>Estabeleça horários regulares e trate como compromisso consigo mesmo.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">4. Aumente Gradualmente</h3>
                        <p>Progrida lentamente em intensidade e duração para evitar lesões.</p>
                    </div>
                </div>
            </div>

            <!-- Exemplo de Superação -->
            <div class="inspiration-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🌟 Exemplo de Superação</h2>
                <div class="max-w-4xl mx-auto">
                    <h3 class="text-2xl font-bold mb-4 text-yellow-400">Maria da Penha - 65 anos</h3>
                    <p class="text-lg leading-relaxed mb-6">
                        Aos 60 anos, Maria estava sedentária, com diabetes e depressão após perder o marido. 
                        Começou caminhando 10 minutos no quintal de casa. Gradualmente, descobriu grupos de 
                        caminhada no bairro, fez amizades e encontrou propósito. Hoje, aos 65, caminha 5km diários, 
                        controla a diabetes naturalmente, lidera um grupo de atividade física para idosos e 
                        transformou sua vida através do movimento simples e constante.
                    </p>
                    <div class="text-yellow-400 font-bold text-xl">
                        "A atividade física me devolveu a alegria de viver e me mostrou que nunca é tarde para recomeçar."
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Página Exercício Físico -->
    <div id="exercise" class="page">
        <button onclick="showPage('home')" class="back-button">← Voltar</button>
        
        <div class="max-w-6xl mx-auto px-6 py-20">
            <h1 class="orbitron text-5xl md:text-7xl font-black gold-glow text-center mb-12">
                💪 EXERCÍCIO FÍSICO
            </h1>

            <!-- História -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">📚 História do Exercício Físico</h2>
                <div class="timeline">
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Grécia Antiga</h3>
                        <p>Ginásios eram centros de treinamento físico sistematizado. Exercícios específicos para desenvolver força, agilidade e resistência.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Século XIX</h3>
                        <p>Desenvolvimento da calistenia e ginástica sueca. Exercícios padronizados para educação física escolar.</p>
                    </div>
                    <div class="timeline-item">
                        <h3 class="text-xl font-bold mb-3 text-yellow-400">Século XX-XXI</h3>
                        <p>Revolução científica: fisiologia do exercício, biomecânica, periodização. Exercício como medicina.</p>
                    </div>
                </div>
            </div>

            <!-- Diferenças -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🔍 Características do Exercício Físico</h2>
                <div class="difference-grid">
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">📊 ESTRUTURADO</h3>
                        <p>Planejamento científico com séries, repetições, cargas e progressões específicas.</p>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">🎯 OBJETIVOS CLAROS</h3>
                        <p>Metas específicas: força, resistência, flexibilidade, composição corporal.</p>
                    </div>
                    <div class="difference-card">
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">📈 PROGRESSIVO</h3>
                        <p>Aumento gradual e controlado de intensidade, volume e complexidade.</p>
                    </div>
                </div>
            </div>

            <!-- Importância -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">⭐ Benefícios do Exercício Físico</h2>
                <div class="grid md:grid-cols-2 gap-6">
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Transformação Corporal</h3>
                        <p>Aumento de massa muscular, redução de gordura, melhora da postura e definição muscular.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Performance Física</h3>
                        <p>Aumento significativo de força, potência, resistência e capacidades físicas específicas.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Saúde Metabólica</h3>
                        <p>Melhora sensibilidade à insulina, acelera metabolismo e otimiza funções hormonais.</p>
                    </div>
                    <div>
                        <h3 class="text-xl font-bold mb-4 text-yellow-400">Disciplina Mental</h3>
                        <p>Desenvolve foco, determinação, autocontrole e capacidade de superar limites.</p>
                    </div>
                </div>
            </div>

            <!-- Como Começar -->
            <div class="section-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🚀 Como Começar Exercício Físico</h2>
                <div class="steps-container">
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">1. Avaliação Inicial</h3>
                        <p>Consulte médico e faça avaliação física completa para definir limitações e objetivos.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">2. Orientação Profissional</h3>
                        <p>Contrate personal trainer ou frequente academia com profissionais qualificados.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">3. Programa Personalizado</h3>
                        <p>Desenvolva treino específico para seus objetivos, nível e disponibilidade.</p>
                    </div>
                    <div class="step-card">
                        <h3 class="text-lg font-bold mb-3 text-yellow-400">4. Consistência</h3>
                        <p>Mantenha regularidade, registre progressos e ajuste o programa conforme evolução.</p>
                    </div>
                </div>
            </div>

            <!-- Exemplo de Superação -->
            <div class="inspiration-card">
                <h2 class="orbitron text-3xl gold-glow mb-6">🌟 Exemplo de Superação</h2>
                <div class="max-w-4xl mx-auto">
                    <h3 class="text-2xl font-bold mb-4 text-yellow-400">Carlos Roberto - Transformação aos 45</h3>
                    <p class="text-lg leading-relaxed mb-6">
                        Executivo sedentário, 120kg, pré-diabético e com baixa autoestima. Aos 45 anos, decidiu mudar. 
                        Começou com exercícios básicos 3x por semana, seguindo programa estruturado de musculação e cardio. 
                        Em 2 anos, perdeu 35kg, ganhou massa muscular, reverteu o pré-diabetes e descobriu paixão pelo 
                        fitness. Hoje compete em fisiculturismo master e inspira outros executivos a priorizarem a saúde 
                        através do exercício físico estruturado.
                    </p>
                    <div class="text-yellow-400 font-bold text-xl">
                        "O exercício físico me deu uma segunda chance de viver com qualidade e propósito."
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        function showPage(pageId) {
            // Esconder todas as páginas
            const pages = document.querySelectorAll('.page');
            pages.forEach(page => {
                page.classList.remove('active');
            });

            // Mostrar página selecionada com animação específica
            setTimeout(() => {
                const targetPage = document.getElementById(pageId);
                targetPage.classList.add('active');
                
                // Aplicar animação específica baseada no tipo
                if (pageId === 'sport') {
                    targetPage.classList.add('sport-transition');
                    setTimeout(() => targetPage.classList.remove('sport-transition'), 800);
                } else if (pageId === 'activity') {
                    targetPage.classList.add('activity-transition');
                    setTimeout(() => targetPage.classList.remove('activity-transition'), 800);
                } else if (pageId === 'exercise') {
                    targetPage.classList.add('exercise-transition');
                    setTimeout(() => targetPage.classList.remove('exercise-transition'), 800);
                }
            }, 100);
        }

        // Adicionar efeitos de hover nos botões
        document.querySelectorAll('.nav-button').forEach(button => {
            button.addEventListener('mouseenter', function() {
                this.style.transform = 'translateY(-5px) scale(1.05)';
            });
            
            button.addEventListener('mouseleave', function() {
                this.style.transform = 'translateY(0) scale(1)';
            });
        });

        // Animação de entrada para elementos quando a página carrega
        window.addEventListener('load', function() {
            const elements = document.querySelectorAll('.section-card, .inspiration-card');
            elements.forEach((element, index) => {
                element.style.opacity = '0';
                element.style.transform = 'translateY(30px)';
                
                setTimeout(() => {
                    element.style.transition = 'all 0.6s ease';
                    element.style.opacity = '1';
                    element.style.transform = 'translateY(0)';
                }, index * 200);
            });
        });

        // Efeito parallax suave nos elementos flutuantes
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const parallax = document.querySelectorAll('.floating-element');
            
            parallax.forEach((element, index) => {
                const speed = 0.5 + (index * 0.1);
                element.style.transform = `translateY(${scrolled * speed}px) rotate(${scrolled * 0.1}deg)`;
            });
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'960d41de8419a49e',t:'MTc1Mjc5MjE5Ny4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
