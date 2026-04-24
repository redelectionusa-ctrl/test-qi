<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Test QI • WISC-V Visuel & Complet</title>
    <style>
        :root {
            --bg: #0f1219;
            --card: #1a1e2b;
            --gold: #e7b42c;
            --goldlight: #fad674;
            --text: #e8e0d3;
            --muted: #9aa4bf;
            --accent: #3e4b6b;
            --success: #5cb878;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: var(--bg);
            font-family: 'Segoe UI', system-ui, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.2rem;
            background-image: radial-gradient(ellipse at 30% 20%, #1f2538 0%, #0b0d13 90%);
        }
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(22, 26, 38, 0.8);
            backdrop-filter: blur(24px);
            border-radius: 3rem;
            padding: 1.8rem 1.8rem 2.2rem;
            border: 1px solid rgba(255, 210, 100, 0.2);
            box-shadow: 0 30px 55px rgba(0, 0, 0, 0.8);
        }
        h1 {
            text-align: center;
            font-size: 2.4rem;
            font-weight: 700;
            letter-spacing: 2px;
            background: linear-gradient(180deg, #f7d774, #d99f2b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.2rem;
        }
        .subtitle {
            text-align: center;
            color: #bcc6dd;
            margin-bottom: 1.5rem;
            font-size: 0.95rem;
        }
        .progress {
            background: #1c2130;
            border-radius: 3rem;
            padding: 0.6rem 1.4rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.4rem;
            flex-wrap: wrap;
            border: 1px solid #ffb34755;
        }
        .badge {
            background: var(--gold);
            color: #0a0c14;
            font-weight: 700;
            padding: 0.3rem 1.3rem;
            border-radius: 2rem;
            font-size: 0.9rem;
        }
        .subtest-title {
            font-size: 1.5rem;
            font-weight: 600;
            color: #f5d78c;
            margin-bottom: 1.2rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .card {
            background: #1b1f2e;
            border-radius: 2rem;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.08);
            box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.05);
        }
        .question-visual {
            font-size: 3rem;
            text-align: center;
            letter-spacing: 6px;
            margin-bottom: 1rem;
            color: #fff6e5;
            filter: drop-shadow(0 4px 8px black);
        }
        .question-text {
            font-size: 1.5rem;
            margin-bottom: 1.3rem;
            color: var(--text);
            line-height: 1.4;
        }
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.8rem;
        }
        .grid-4 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.7rem;
        }
        @media (min-width: 500px) {
            .grid-4 {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        .opt {
            background: #252c40;
            border: 2px solid rgba(255, 200, 100, 0.3);
            border-radius: 1.3rem;
            padding: 0.9rem 0.6rem;
            font-size: 1.1rem;
            text-align: center;
            cursor: pointer;
            transition: 0.2s;
            color: #ddd;
            font-weight: 500;
            word-break: break-word;
        }
        .opt:hover {
            background: #3f4b65;
            border-color: #f9b84a;
            transform: scale(1.02);
            color: white;
        }
        .opt.selected {
            background: #e6a843;
            border-color: #ffe484;
            color: #0e0f16;
            font-weight: 700;
        }
        .nav-row {
            display: flex;
            justify-content: space-between;
            margin-top: 1.2rem;
            gap: 1rem;
        }
        .btn {
            background: #323b53;
            border: 1px solid #f3b95b;
            color: #f7f0dd;
            padding: 0.8rem 2rem;
            border-radius: 2.5rem;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
            backdrop-filter: blur(10px);
        }
        .btn:hover:not(:disabled) {
            background: #e6ad42;
            color: #0f121a;
            border-color: #fff0c0;
        }
        .btn:disabled {
            opacity: 0.4;
            pointer-events: none;
        }
        .result-box {
            text-align: center;
            padding: 1rem;
        }
        .iq-big {
            font-size: 5rem;
            font-weight: 800;
            background: linear-gradient(180deg, #fadf7f, #c98a1e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hidden {
            display: none !important;
        }
        hr {
            border-color: #5f5540;
            margin: 1rem 0;
        }
    </style>
</head>
<body>
<div class="container" id="app">
    <h1>🧩 TEST WISC-V</h1>
    <div class="subtitle">7 sous-tests visuels • 42 questions</div>
    <div id="dynamicRoot"></div>
</div>
<script>
    (function() {
        // ---------- 7 SOUS-TESTS (6 questions chacun) ----------
        const subtests = [
            {
                name: "🖼️ Matrices",
                items: [
                    { q: "Complète la suite : ◼ ◻ ◼ ◻ ◼ ?", visual: "◼ ◻ ◼ ◻ ◼ ?", options: ["◻", "◼", "◆", "●"], correct: 0 },
                    { q: "Suite logique : ▲ ▶ ▼ ◀ ▲ ?", visual: "▲ ▶ ▼ ◀ ▲ ?", options: ["▶", "▼", "◀", "▲"], correct: 0 },
                    { q: "Symboles : ○ ● ○ ● ○ ?", visual: "○ ● ○ ● ○ ?", options: ["●", "○", "◇", "□"], correct: 0 },
                    { q: "Croissants : ☾ ☽ ☾ ☽ ☾ ?", visual: "☾ ☽ ☾ ☽ ☾ ?", options: ["☽", "☾", "★", "☀"], correct: 0 },
                    { q: "Flèches : ↑ → ↓ ← ↑ ?", visual: "↑ → ↓ ← ↑ ?", options: ["→", "↓", "←", "↑"], correct: 0 },
                    { q: "Points : ⬤ ◯ ⬤ ◯ ⬤ ?", visual: "⬤ ◯ ⬤ ◯ ⬤ ?", options: ["◯", "⬤", "⬬", "◉"], correct: 0 }
                ]
            },
            {
                name: "📚 Vocabulaire",
                items: [
                    { q: "Que signifie 'lacune' ?", options: ["Manque", "Excès", "Rapidité", "Silence"], correct: 0 },
                    { q: "Synonyme de 'bravoure' ?", options: ["Peur", "Courage", "Tristesse", "Faiblesse"], correct: 1 },
                    { q: "Que veut dire 'éphémère' ?", options: ["Durable", "Passager", "Solide", "Ancien"], correct: 1 },
                    { q: "Qu'est-ce qu'un 'récif' ?", options: ["Outil", "Rocher marin", "Vent", "Poisson"], correct: 1 },
                    { q: "Définition de 'perplexe' ?", options: ["Enthousiaste", "Hésitant", "Confus", "Joyeux"], correct: 2 },
                    { q: "'Opulent' signifie :", options: ["Pauvre", "Riche", "Simple", "Moderne"], correct: 1 }
                ]
            },
            {
                name: "⚖️ Balances",
                items: [
                    { q: "Si ★★ = 4, combien pèse ★★★ ?", visual: "★★ = 4", options: ["5", "6", "7", "8"], correct: 1 },
                    { q: "● = 3, alors ●●● = ?", visual: "● = 3", options: ["6", "9", "12", "8"], correct: 1 },
                    { q: "♣♣ = 10, que vaut ♣♣♣♣ ?", visual: "♣♣ = 10", options: ["15", "18", "20", "25"], correct: 2 },
                    { q: "◆◆◆ = 12, ◆◆◆◆◆ = ?", visual: "◆◆◆ = 12", options: ["16", "20", "22", "24"], correct: 1 },
                    { q: "Si ☀☀ = 8, alors ☀☀☀☀ = ?", visual: "☀☀ = 8", options: ["12", "14", "16", "18"], correct: 2 },
                    { q: "▼▼▼ = 9, combien pour ▼▼▼▼▼▼ ?", visual: "▼▼▼=9", options: ["15", "18", "21", "24"], correct: 1 }
                ]
            },
            {
                name: "🧩 Puzzles visuels",
                items: [
                    { q: "Quelle pièce complète ? 🔲🔲?🔲 (carré manquant)", visual: "⬜⬛⬜?⬜⬛", options: ["⬛", "⬜", "🔲", "⬜"], correct: 0 },
                    { q: "Suite de formes : △□△□△ ?", visual: "△ □ △ □ △ ?", options: ["□", "△", "○", "☆"], correct: 0 },
                    { q: "Alternance : 🌕🌑🌕🌑🌕 ?", visual: "🌕 🌑 🌕 🌑 🌕 ?", options: ["🌑", "🌕", "🌗", "🌒"], correct: 0 },
                    { q: "Symétrie : ◢◣ ◢◣ ◢ ?", visual: "◢◣ ◢◣ ◢ ?", options: ["◣", "◢", "◤", "◥"], correct: 0 },
                    { q: "Motif : ⚫⚪⚫⚪⚫ ?", visual: "⚫ ⚪ ⚫ ⚪ ⚫ ?", options: ["⚪", "⚫", "🔘", "⭕"], correct: 0 },
                    { q: "Pyramide : 🔺🔻🔺🔻🔺 ?", visual: "🔺 🔻 🔺 🔻 🔺 ?", options: ["🔻", "🔺", "🔷", "🔶"], correct: 0 }
                ]
            },
            {
                name: "🖼️ Mémoire d'images",
                items: [
                    { q: "Image montrée : 🐶. Lequel était affiché ?", visual: "🐶", options: ["🐱", "🐶", "🐭", "🐹"], correct: 1 },
                    { q: "Souviens-toi : 🌲", visual: "🌲", options: ["🌳", "🌲", "🎄", "🌴"], correct: 1 },
                    { q: "Mémorise : 🚗", visual: "🚗", options: ["🚙", "🚗", "🚕", "🚓"], correct: 1 },
                    { q: "Image : 🍎", visual: "🍎", options: ["🍏", "🍎", "🍊", "🍇"], correct: 1 },
                    { q: "Vu avant : ⭐", visual: "⭐", options: ["🌟", "⭐", "✨", "💫"], correct: 1 },
                    { q: "Rappel : ☎️", visual: "☎️", options: ["📞", "☎️", "📱", "📠"], correct: 1 }
                ]
            },
            {
                name: "🌍 Connaissances",
                items: [
                    { q: "Combien de continents sur Terre ?", options: ["5", "6", "7", "8"], correct: 2 },
                    { q: "Qui a peint la Joconde ?", options: ["Van Gogh", "Picasso", "Léonard de Vinci", "Rembrandt"], correct: 2 },
                    { q: "Capitale du Japon ?", options: ["Séoul", "Tokyo", "Pékin", "Bangkok"], correct: 1 },
                    { q: "Combien de jours dans une année bissextile ?", options: ["364", "365", "366", "367"], correct: 2 },
                    { q: "Quel océan est le plus grand ?", options: ["Atlantique", "Indien", "Arctique", "Pacifique"], correct: 3 },
                    { q: "Qui a écrit 'Roméo et Juliette' ?", options: ["Molière", "Shakespeare", "Cervantes", "Hugo"], correct: 1 }
                ]
            },
            {
                name: "🔤 Similitudes",
                items: [
                    { q: "Chien - Chat", options: ["Animaux domestiques", "Mammifères", "Ont des poils", "Compagnons"], correct: 1 },
                    { q: "Colère - Joie", options: ["Émotions", "Réactions", "Humeurs", "Sentiments"], correct: 0 },
                    { q: "Pomme - Banane", options: ["Fruits", "Aliments", "Comestibles", "Sucrés"], correct: 0 },
                    { q: "Marteau - Tournevis", options: ["Outils", "Objets", "Fer", "Bricolage"], correct: 0 },
                    { q: "Rouge - Bleu", options: ["Couleurs primaires", "Teintes", "Visibles", "Arc-en-ciel"], correct: 0 },
                    { q: "Médecin - Enseignant", options: ["Professions", "Métiers", "Aident", "Respectés"], correct: 0 }
                ]
            }
        ];
        const TOTAL_SUBTESTS = subtests.length;
        const Q_PER_SUBTEST = 6;
        let currentSub = 0;
        let currentQ = 0;
        let answers = Array(TOTAL_SUBTESTS).fill().map(() => Array(Q_PER_SUBTEST).fill(null));
        let finished = false;
        const root = document.getElementById('dynamicRoot');
        function render() {
            if (finished) {
                showResults();
                return;
            }
            const sub = subtests[currentSub];
            const item = sub.items[currentQ];
            const sel = answers[currentSub][currentQ];
            const totalQ = TOTAL_SUBTESTS * Q_PER_SUBTEST;
            const currentGlobal = currentSub * Q_PER_SUBTEST + currentQ + 1;
            let html = `
                <div class="progress">
                    <span class="badge">${currentGlobal}/${totalQ}</span>
                    <span style="color:#fadf9e;">${sub.name} · ${currentQ+1}/${Q_PER_SUBTEST}</span>
                </div>
                <div class="subtest-title">${sub.name}</div>
                <div class="card">
            `;
            if (item.visual) {
                html += `<div class="question-visual">${item.visual}</div>`;
            }
            html += `<div class="question-text">${item.q}</div>`;
            html += `<div class="grid-2" id="optContainer">`;
            item.options.forEach((opt, idx) => {
                html += `<div class="opt${sel === idx ? ' selected' : ''}" data-idx="${idx}">${opt}</div>`;
            });
            html += `</div>`;
            html += `
                <div class="nav-row">
                    <button class="btn" id="prevBtn" ${(currentSub===0 && currentQ===0)?'disabled':''}>◀ Précédent</button>
                    <button class="btn" id="nextBtn">${(currentSub===TOTAL_SUBTESTS-1 && currentQ===Q_PER_SUBTEST-1)?'🏁 Terminer':'Suivant ▶'}</button>
                </div>
                </div>
            `;
            root.innerHTML = html;
            document.querySelectorAll('#optContainer .opt').forEach(btn => {
                btn.addEventListener('click', function() {
                    const idx = parseInt(this.dataset.idx);
                    answers[currentSub][currentQ] = idx;
                    document.querySelectorAll('#optContainer .opt').forEach(b => b.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            document.getElementById('prevBtn')?.addEventListener('click', () => {
                if (currentQ > 0) currentQ--;
                else if (currentSub > 0) { currentSub--; currentQ = Q_PER_SUBTEST-1; }
                render();
            });
            document.getElementById('nextBtn')?.addEventListener('click', () => {
                if (currentSub === TOTAL_SUBTESTS-1 && currentQ === Q_PER_SUBTEST-1) {
                    finished = true;
                    render();
                } else if (currentQ === Q_PER_SUBTEST-1) {
                    currentSub++; currentQ = 0; render();
                } else {
                    currentQ++; render();
                }
            });
        }
        function showResults() {
            let correct = 0;
            for (let s = 0; s < TOTAL_SUBTESTS; s++) {
                for (let q = 0; q < Q_PER_SUBTEST; q++) {
                    if (answers[s][q] === subtests[s].items[q].correct) correct++;
                }
            }
            const max = TOTAL_SUBTESTS * Q_PER_SUBTEST;
            const iq = Math.min(150, Math.round(70 + (correct / max) * 80));
            root.innerHTML = `
                <div class="result-box">
                    <h2 style="color:#ffd966;">Résultat WISC-V estimé</h2>
                    <div class="iq-big">${iq}</div>
                    <p style="font-size:1.4rem; color:white;">${correct}/${max} bonnes réponses</p>
                    <p style="color:#ccc;">🧠 Basé sur 7 indices visuels et connaissances.</p>
                    <hr>
                    <button class="btn" id="restartBtn">🔄 Recommencer</button>
                </div>
            `;
            document.getElementById('restartBtn').addEventListener('click', ()=>{
                currentSub=0; currentQ=0; answers=Array(TOTAL_SUBTESTS).fill().map(()=>Array(Q_PER_SUBTEST).fill(null));
                finished=false; render();
            });
        }
        render();
    })();
</script>
</body>
</html>
