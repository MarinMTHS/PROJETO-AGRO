<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>AgroGestor | Soluções em Agronegócio e Gestão de Terras</title>
    <!-- Font Awesome 6 (Free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Fonts: Formal e elegante -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&family=Playfair+Display:wght@500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: #f5f7f2;
            color: #1e2a1f;
            line-height: 1.5;
            scroll-behavior: smooth;
        }

        .container {
            max-width: 1280px;
            margin: 0 auto;
            padding: 0 32px;
        }

        header {
            background: linear-gradient(135deg, #0f3b1c 0%, #1c5e2a 100%);
            color: white;
            padding: 24px 0;
            box-shadow: 0 12px 28px rgba(0, 0, 0, 0.08);
            border-bottom: 1px solid rgba(255,255,255,0.2);
        }

        .header-flex {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo h1 {
            font-family: 'Playfair Display', serif;
            font-size: 2rem;
            letter-spacing: -0.5px;
            font-weight: 700;
        }

        .logo p {
            font-size: 0.85rem;
            opacity: 0.85;
            letter-spacing: 1px;
        }

        .creators {
            background: rgba(255,255,240,0.12);
            backdrop-filter: blur(4px);
            padding: 12px 20px;
            border-radius: 48px;
            text-align: right;
            font-weight: 500;
            border: 1px solid rgba(255,215,140,0.4);
        }

        .creators span {
            font-weight: 700;
            color: #f9e0a0;
        }

        .nav-tabs {
            background: white;
            border-radius: 60px;
            margin-top: 28px;
            display: inline-flex;
            box-shadow: 0 6px 14px rgba(0,0,0,0.05);
            overflow: hidden;
            border: 1px solid #e2e8dd;
        }

        .tab-btn {
            background: transparent;
            border: none;
            padding: 14px 32px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.25s ease;
            font-family: 'Inter', sans-serif;
            color: #2d4a2c;
            letter-spacing: -0.2px;
        }

        .tab-btn i {
            margin-right: 10px;
            font-size: 1.1rem;
        }

        .tab-btn.active {
            background: #1f5e2c;
            color: white;
            box-shadow: inset 0 -2px 0 #cba135;
        }

        .tab-btn:not(.active):hover {
            background: #eef4ea;
            color: #0a3b13;
        }

        .tab-content {
            background: white;
            border-radius: 32px;
            margin-top: 28px;
            padding: 40px 36px;
            box-shadow: 0 20px 35px -12px rgba(0,0,0,0.1);
            border: 1px solid #e9efe3;
            transition: all 0.2s;
        }

        .tab-pane {
            display: none;
            animation: fadeIn 0.35s ease;
        }

        .tab-pane.active-pane {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px);}
            to { opacity: 1; transform: translateY(0);}
        }

        .card-soil {
            background: #fefdf9;
            border-radius: 28px;
            padding: 28px;
            margin-bottom: 32px;
            border-left: 8px solid #4b7b3b;
            box-shadow: 0 2px 8px rgba(0,0,0,0.02);
        }

        h2 {
            font-family: 'Playfair Display', serif;
            font-size: 1.9rem;
            margin-bottom: 1rem;
            color: #1f4529;
        }

        h3 {
            font-weight: 600;
            margin: 1.5rem 0 1rem 0;
            font-size: 1.5rem;
            color: #2b5e2f;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        label {
            font-weight: 600;
            display: block;
            margin-bottom: 0.5rem;
            color: #1f3b1a;
        }

        input, select {
            width: 100%;
            padding: 14px 18px;
            border: 1.5px solid #dde3d6;
            border-radius: 24px;
            font-size: 1rem;
            font-family: 'Inter', sans-serif;
            background: #ffffff;
            transition: 0.2s;
        }

        input:focus, select:focus {
            outline: none;
            border-color: #58853e;
            box-shadow: 0 0 0 3px rgba(88,133,62,0.2);
        }

        button {
            background: #1f5e2c;
            color: white;
            border: none;
            padding: 12px 28px;
            border-radius: 40px;
            font-weight: 600;
            font-size: 0.95rem;
            cursor: pointer;
            transition: 0.2s;
            font-family: 'Inter', sans-serif;
        }

        button:hover {
            background: #11421c;
            transform: translateY(-2px);
        }

        .result-box {
            background: #eef3e8;
            border-radius: 28px;
            padding: 20px;
            margin-top: 20px;
            border: 1px solid #cde0c2;
        }

        .result-box p {
            font-size: 1.1rem;
            margin: 8px 0;
        }

        .badge-success {
            background: #1f5e2c;
            display: inline-block;
            padding: 6px 16px;
            border-radius: 40px;
            color: white;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .table-soil {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }

        .table-soil th, .table-soil td {
            padding: 14px 12px;
            text-align: left;
            border-bottom: 1px solid #e0e8d9;
        }

        .table-soil th {
            background: #eef4e6;
            font-weight: 700;
            color: #1c461f;
        }

        .vscode-link {
            display: inline-flex;
            align-items: center;
            gap: 12px;
            background: #0a2b12;
            color: white;
            padding: 12px 30px;
            border-radius: 48px;
            text-decoration: none;
            font-weight: 600;
            margin-top: 16px;
            transition: 0.2s;
            border: 1px solid #b8d9a6;
        }

        .vscode-link i {
            font-size: 1.6rem;
        }

        .vscode-link:hover {
            background: #194e24;
            transform: scale(1.02);
        }

        footer {
            margin-top: 60px;
            background: #0f2a13;
            color: #d4e6ca;
            padding: 32px 0;
            text-align: center;
            border-radius: 40px 40px 0 0;
        }

        hr {
            margin: 20px 0;
            border-color: #cde0bf;
        }

        @media (max-width: 720px) {
            .container {
                padding: 0 20px;
            }
            .tab-btn {
                padding: 10px 18px;
                font-size: 0.85rem;
            }
            .tab-content {
                padding: 24px;
            }
            .header-flex {
                flex-direction: column;
                text-align: center;
            }
        }
    </style>
</head>
<body>

<header>
    <div class="container">
        <div class="header-flex">
            <div class="logo">
                <h1><i class="fas fa-seedling" style="color: #d9e66b;"></i> AgroGestor</h1>
                <p>Inteligência em territórios · Excelência no campo</p>
            </div>
            <div class="creators">
                <i class="fas fa-leaf"></i> Desenvolvido por <span>Matheus</span> e <span>Daniel</span><br>
                <span style="font-size:0.7rem;">Plataforma de análise fundiária</span>
            </div>
        </div>
        <div class="nav-tabs">
            <button class="tab-btn active" data-tab="tab1"><i class="fas fa-chart-line"></i> Diagnóstico de Terras</button>
            <button class="tab-btn" data-tab="tab2"><i class="fas fa-tractor"></i> Classificação de Solo</button>
            <button class="tab-btn" data-tab="tab3"><i class="fas fa-file-alt"></i> Relatório Técnico</button>
        </div>
    </div>
</header>

<main class="container">
    <div class="tab-content">
        <!-- ABA 1 - Diagnóstico de Terras com teste interativo -->
        <div id="tab1" class="tab-pane active-pane">
            <div class="card-soil">
                <h2><i class="fas fa-map-marked-alt"></i> Teste de Aptidão da Terra</h2>
                <p>Avalie o potencial produtivo da sua propriedade com base em parâmetros técnicos (solo, topografia, clima). Preencha os campos abaixo para obter um diagnóstico personalizado.</p>
                <hr>
                <form id="landTestForm">
                    <div class="form-group">
                        <label><i class="fas fa-droplet"></i> Índice de Fertilidade (0-100):</label>
                        <input type="number" id="fertility" min="0" max="100" value="68" step="1">
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-water"></i> Disponibilidade Hídrica (0-100):</label>
                        <input type="number" id="water" min="0" max="100" value="72" step="1">
                    </div>
                    <div class="form-group">
                        <label><i class="fas fa-mountain"></i> Topografia (plano/suave/acentuado):</label>
                        <select id="topography">
                            <option value="plano">Plano (ideal para cultivo mecanizado)</option>
                            <option value="suave" selected>Suave ondulado (bom potencial)</option>
                            <option value="acentuado">Acentuado (limitação severa)</option>
                        </select>
                    </div>
                    <button type="submit" id="runTestBtn"><i class="fas fa-calculator"></i> Realizar Teste de Terras</button>
                </form>
                <div id="landResult" class="result-box" style="display: none;">
                    <p><strong>🔍 Diagnóstico Técnico:</strong> <span id="diagnosticText"></span></p>
                    <p><strong>📈 Índice de Potencial Agrícola (IPA):</strong> <span id="ipaValue"></span> / 100</p>
                    <p><strong>✅ Recomendação:</strong> <span id="recommendation"></span></p>
                </div>
            </div>
            <div class="card-soil">
                <h3><i class="fas fa-chart-simple"></i> Mapa de Referência</h3>
                <p>O teste acima utiliza metodologia adaptada da <strong>EMBRAPA</strong> para classificação de terras agrícolas. Quanto maior o IPA, maior o potencial produtivo sustentável.</p>
                <div class="badge-success">Base científica · 3 categorias: Baixo / Médio / Alto Potencial</div>
            </div>
        </div>

        <!-- ABA 2 - Classificação de Solo -->
        <div id="tab2" class="tab-pane">
            <h2><i class="fas fa-flask"></i> Classificação de Solos Agrícolas</h2>
            <p>Análise simplificada de parâmetros físico-químicos para enquadramento em classes texturais.</p>
            <div class="form-group">
                <label>Percentual de Argila (%):</label>
                <input type="number" id="clay" placeholder="ex: 35" value="38" step="1">
            </div>
            <div class="form-group">
                <label>Percentual de Silte (%):</label>
                <input type="number" id="silt" placeholder="ex: 25" value="27" step="1">
            </div>
            <div class="form-group">
                <label>Matéria Orgânica (g/kg):</label>
                <input type="number" id="om" placeholder="ex: 25" value="28" step="1">
            </div>
            <button id="classifySoilBtn"><i class="fas fa-microscope"></i> Classificar Solo</button>
            <div id="soilClassificationResult" class="result-box" style="margin-top: 25px; display: none;">
                <p><strong>🏷️ Classe Textural:</strong> <span id="texturalClass"></span></p>
                <p><strong>🌾 Qualidade Agronômica:</strong> <span id="agroQuality"></span></p>
                <p><strong>💡 Manejo sugerido:</strong> <span id="managementTip"></span></p>
            </div>
            <hr>
            <h3>Referência de Classes (EMBRAPA)</h3>
            <table class="table-soil">
                <thead>
                    <tr><th>Tipo de Solo</th><th>Argila %</th><th>Característica</th></tr>
                </thead>
                <tbody>
                    <tr><td>Argiloso</td><td>> 60%</td><td>Alta retenção, manejo hídrico cuidadoso</td></tr>
                    <tr><td>Textura Média</td><td>35% - 60%</td><td>Equilibrado, boa produtividade</td></tr>
                    <tr><td>Arenoso</td><td>< 15%</td><td>Drenagem rápida, baixa fertilidade natural</td></tr>
                </tbody>
            </table>
        </div>

        <!-- ABA 3 - Relatório Técnico e link Visual Studio Code -->
        <div id="tab3" class="tab-pane">
            <h2><i class="fas fa-file-contract"></i> Relatório Estratégico & Ferramentas</h2>
            <p>Documento formal de avaliação de terras elaborado pelos especialistas <strong>Matheus & Daniel</strong>. Abaixo disponibilizamos acesso direto ao ambiente de desenvolvimento integrado.</p>
            <div class="card-soil" style="background: #fafaf5;">
                <h3><i class="fas fa-code"></i> Acesso ao Visual Studio Code</h3>
                <p>Clique no botão oficial para acessar o portal do VS Code e potencializar seus projetos no agronegócio digital.</p>
                <a href="https://code.visualstudio.com/" target="_blank" class="vscode-link">
                    <i class="fab fa-visual-studio-code"></i> Visual Studio Code — Editor oficial
                </a>
                <p style="margin-top: 18px; font-size:0.9rem;">🖥️ Integração com tecnologias de geoprocessamento, telemetria e gestão rural.</p>
            </div>
            <div class="card-soil">
                <h3><i class="fas fa-clipboard-list"></i> Síntese de Recomendações Agrícolas</h3>
                <p>Com base nos dados informados nas abas “Diagnóstico de Terras” e “Classificação de Solo”, é possível elaborar um zoneamento agrícola de alta precisão.</p>
                <ul style="margin-left: 1.8rem; margin-top: 12px;">
                    <li>Recomenda-se correção de acidez para solos com alta argila.</li>
                    <li>Em áreas com topografia acentuada, adotar terraceamento e cultivo em nível.</li>
                    <li>Utilizar imagens de satélite e sensoriamento remoto.</li>
                </ul>
            </div>
            <div class="badge-success" style="font-size:0.9rem;">Versão 2.4 · Laudo Técnico emitido por Matheus e Daniel, especialistas em Agronegócio</div>
        </div>
    </div>
</main>

<footer>
    <div class="container">
        <p><i class="fas fa-copyright"></i> AgroGestor 2026 — Plataforma de Análise Fundiária e Agronegócio</p>
        <p style="margin-top: 10px;">Desenvolvido por <strong>Matheus e Daniel</strong> | Compromisso com a inovação rural e sustentabilidade.</p>
        <p><i class="fas fa-globe"></i> Dados simulados para demonstração técnica. Precisão e formalismo alinhados às boas práticas do setor.</p>
    </div>
</footer>

<script>
    // SISTEMA DE ABAS FUNCIONAL E ESTÁVEL - SEM PISCAR
    const tabBtns = document.querySelectorAll('.tab-btn');
    const panes = document.querySelectorAll('.tab-pane');

    function activateTab(tabId) {
        panes.forEach(pane => {
            pane.classList.remove('active-pane');
            if(pane.id === tabId) {
                pane.classList.add('active-pane');
            }
        });
        tabBtns.forEach(btn => {
            btn.classList.remove('active');
            if(btn.getAttribute('data-tab') === tabId) {
                btn.classList.add('active');
            }
        });
    }

    tabBtns.forEach(btn => {
        btn.addEventListener('click', (e) => {
            const tabId = btn.getAttribute('data-tab');
            activateTab(tabId);
        });
    });

    // ==================== TESTE DE TERRAS (ABA 1) ====================
    const landForm = document.getElementById('landTestForm');
    const landResultDiv = document.getElementById('landResult');
    const diagnosticTextSpan = document.getElementById('diagnosticText');
    const ipaValueSpan = document.getElementById('ipaValue');
    const recommendationSpan = document.getElementById('recommendation');

    function computeLandDiagnosis(fert, water, topo) {
        let topoScore = 1;
        if(topo === 'plano') topoScore = 1.0;
        else if(topo === 'suave') topoScore = 0.85;
        else if(topo === 'acentuado') topoScore = 0.5;
        let baseIPA = (fert * 0.45) + (water * 0.4) + (topoScore * 100 * 0.15);
        let IPA = Math.min(100, Math.max(0, Math.round(baseIPA)));
        let categoria = '';
        let rec = '';
        if(IPA >= 75) {
            categoria = '🔷 Terras de Alto Potencial Agrícola - aptidão plena para cultivos perenes e grãos.';
            rec = 'Recomenda-se investimento em agricultura de precisão e rotação de culturas. Alta rentabilidade esperada.';
        } else if(IPA >= 45) {
            categoria = '🟢 Terras de Médio Potencial - requerem manejo moderado e correções pontuais.';
            rec = 'Adubação equilibrada e práticas conservacionistas (plantio direto) elevarão produtividade.';
        } else {
            categoria = '🟠 Terras de Baixo Potencial - restrições significativas para agricultura intensiva.';
            rec = 'Indicado para sistemas silvipastoris, recuperação de pastagens ou florestas comerciais.';
        }
        return { IPA, categoria, rec };
    }

    landForm.addEventListener('submit', (e) => {
        e.preventDefault();
        let fertility = parseFloat(document.getElementById('fertility').value);
        let water = parseFloat(document.getElementById('water').value);
        let topography = document.getElementById('topography').value;
       
        if(isNaN(fertility)) fertility = 50;
        if(isNaN(water)) water = 50;
        fertility = Math.min(100, Math.max(0, fertility));
        water = Math.min(100, Math.max(0, water));
       
        const result = computeLandDiagnosis(fertility, water, topography);
        diagnosticTextSpan.innerText = result.categoria;
        ipaValueSpan.innerText = result.IPA;
        recommendationSpan.innerText = result.rec;
        landResultDiv.style.display = 'block';
    });

    // ==================== CLASSIFICAÇÃO DE SOLO (ABA 2) ====================
    const classifyBtn = document.getElementById('classifySoilBtn');
    const soilResultDiv = document.getElementById('soilClassificationResult');
    const texturalSpan = document.getElementById('texturalClass');
    const agroQualitySpan = document.getElementById('agroQuality');
    const managementTipSpan = document.getElementById('managementTip');

    function getSoilClass(clay, silt, om) {
        let textural = '';
        let quality = '';
        let tip = '';
       
        if(clay > 60) {
            textural = 'Solo Argiloso (muita argila)';
            quality = 'Alta capacidade de retenção de água e nutrientes, porém suscetível à compactação.';
            tip = 'Utilize subsolagem e evite tráfego pesado quando úmido. Aplique gesso agrícola para melhorar subsolo.';
        } else if(clay >= 35 && clay <= 60) {
            textural = 'Solo de Textura Média / Franco-argiloso';
            quality = 'Estrutura equilibrada, boa drenagem e capacidade de troca catiônica moderada.';
            tip = 'Ideal para a maioria das culturas anuais. Mantenha cobertura morta e adube com base em análise.';
        } else if(clay < 15) {
            textural = 'Solo Arenoso / Areia Franca';
            quality = 'Baixa retenção de água e nutrientes, rápida lixiviação.';
            tip = 'Irrigação por gotejamento, aumento de matéria orgânica e adubação parcelada são essenciais.';
        } else {
            textural = 'Solo Franco-Arenoso (transição)';
            quality = 'Textura leve, intermediário entre arenoso e médio.';
            tip = 'Monitorar umidade e adicionar composto orgânico para elevar CTC.';
        }
       
        if(om > 40) {
            quality += ' (Alto teor de matéria orgânica: excelente fertilidade biológica).';
            tip += ' Potencial para agricultura orgânica.';
        } else if(om < 15) {
            quality += ' (Baixa matéria orgânica, necessário incremento com adubos verdes).';
            tip += ' Cultivo de plantas de cobertura e incorporação de resíduos.';
        } else {
            quality += ' (Teor de MO moderado, favorável).';
        }
        return { textural, quality, tip };
    }

    classifyBtn.addEventListener('click', () => {
        let clay = parseFloat(document.getElementById('clay').value);
        let silt = parseFloat(document.getElementById('silt').value);
        let om = parseFloat(document.getElementById('om').value);
       
        if(isNaN(clay)) clay = 30;
        if(isNaN(silt)) silt = 30;
        if(isNaN(om)) om = 20;
       
        clay = Math.min(100, Math.max(0, clay));
        silt = Math.min(100, Math.max(0, silt));
        om = Math.min(100, Math.max(0, om));
       
        if(clay + silt > 100) {
            alert("Atenção: a soma de argila + silte não deve ultrapassar 100% (modelo simplificado). Ajuste os valores.");
            return;
        }
       
        const { textural, quality, tip } = getSoilClass(clay, silt, om);
        texturalSpan.innerText = textural;
        agroQualitySpan.innerText = quality;
        managementTipSpan.innerText = tip;
        soilResultDiv.style.display = 'block';
    });

    // Tudo estável - sem execuções automáticas que causem piscamento
    console.log("AgroGestor pronto — Sistema estável, formal e desenvolvido por Matheus e Daniel");
</script>
</body>
</html>
