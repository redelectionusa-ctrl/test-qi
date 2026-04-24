<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, maximum-scale=1.5">
    <title>Test QI WISC-V • Complet & Progressif</title>
    <style>
        :root {
            --bg: #0c0f17;
            --card: #151b28;
            --gold: #e2a83e;
            --gold2: #f5cd6e;
            --text: #e7dfd1;
            --muted: #8f9bb5;
            --accent: #2e3a55;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: var(--bg);
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            background-image: radial-gradient(ellipse at 20% 30%, #1f263a 0%, #080a10 90%);
        }
        .container {
            max-width: 850px;
            width: 100%;
            background: rgba(18, 22, 35, 0.85);
            backdrop-filter: blur(28px);
            -webkit-backdrop-filter: blur(28px);
            border-radius: 2.8rem;
            padding: 1.7rem 1.7rem 2rem;
            border: 1px solid rgba(220, 180, 70, 0.25);
            box-shadow: 0 35px 65px rgba(0, 0, 0, 0.8);
        }
        h1 {
            font-size: 2.3rem;
            text-align: center;
            letter-spacing: 2px;
            background: linear-gradient(180deg, #ffde89, #c5841e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.2rem;
            font-weight: 700;
        }
        .subtitle {
            text-align: center;
            color: #b2bedb;
            margin-bottom: 1.3rem;
            font-size: 0.9rem;
            border-bottom: 1px dashed #4a4f60;
            padding-bottom: 0.8rem;
        }
        .progress-bar {
            background: #1d2333;
            border-radius: 2.5rem;
            padding: 0.6rem 1.4rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.3rem;
            border: 1px solid #ffaf3c55;
        }
        .badge {
            background: #e2a83e;
            color: #0a0d14;
            font-weight: 700;
            padding: 0.3rem 1.2rem;
            border-radius: 2rem;
            font-size: 0.85rem;
        }
        .subtest-header {
            display: flex;
            align-items: center;
            gap: 0.6rem;
            margin-bottom: 1rem;
            font-size: 1.4rem;
            font-weight: 600;
            color: #f7d686;
        }
        .card {
            background: rgba(20, 24, 38, 0.9);
            border-radius: 2rem;
            padding: 1.5rem;
            border: 1px solid rgba(255, 255, 255, 0.07);
            box-shadow: inset 0 1px 0 rgba(255, 255, 200, 0.06);
        }
        .visual-large {
            font-size: 3.2rem;
            text-align: center;
            letter-spacing: 5px;
            margin-bottom: 0.8rem;
            color: #fff3da;
            filter: drop-shadow(0 6px 10px #00000060);
        }
        .question {
            font-size: 1.5rem;
            margin: 0.8rem 0 1.2rem;
            color: var(--text);
            line-height: 1.4;
        }
        .options-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.8rem;
            margin: 1rem 0 0.8rem;
        }
        @media (min-width: 500px) {
            .options-grid.col4 {
                grid-template-columns: repeat(4, 1fr);
            }
        }
        .opt-btn {
            background: #222a3c;
            border: 2px solid rgba(255, 190, 70, 0.35);
            border-radius: 1.3rem;
            padding: 0.8rem 0.5rem;
            font-size: 1rem;
            font-weight: 500;
            color: #ddd9ce;
            cursor: pointer;
            transition: all 0.2s;
            text-align: center;
            word-break: break-word;
        }
        .opt-btn:hover {
            background: #3e4864;
            border-color: #f9b84a;
            transform: scale(1.02);
            color: white;
        }
        .opt-btn.selected {
            background: #e2a83e;
            border-color: #ffdd88;
            color: #0b0e18;
            font-weight: 700;
            box-shadow: 0 0 18px #f90;
        }
        .nav-buttons {
            display: flex;
            justify-content: space-between;
            margin-top: 1.3rem;
            gap: 0.8rem;
        }
        .btn {
            background: #2f3852;
            border: 1px solid #f0b64b;
            color: #f5edd8;
            padding: 0.7rem 1.8rem;
            border-radius: 2.5rem;
            font-weight: 700;
            cursor: pointer;
            backdrop-filter: blur(10px);
            transition: 0.2s;
        }
        .btn:hover:not(:disabled) {
            background: #d9982e;
            border-color: #ffe7b0;
            color: #12141d;
        }
        .btn:disabled {
            opacity: 0.4;
            pointer-events: none;
        }
        .stop-message {
            background: #2d2b1c;
            color: #ffcd7a;
            padding: 0.8rem;
            border-radius: 1.2rem;
            margin-top: 0.8rem;
            font-weight: 500;
        }
        .result-screen {
            text-align: center;
        }
        .iq-big {
            font-size: 5.5rem;
            font-weight: 800;
            background: linear-gradient(180deg, #ffe484, #c07e1a);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        hr {
            border-color: #4e472f;
            margin: 1.2rem 0;
        }
    </style>
</head>
<body>
<div class="container" id="app">
    <h1>🧠 WISC-V ÉTENDU</h1>
    <div class="subtitle">7 indices · jusqu'à 26 items progressifs · règles d'arrêt</div>
    <div id="dynamicUI"></div>
</div>
<script>
    (function() {
        // ----- générateur de sous-tests avec difficulté progressive -----
        function generateSubtest(name, icon, baseItems, extraHardItems = []) {
            // Fusionne items de base + items difficiles (difficulté croissante implicite par l'ordre)
            return {
                name: `${icon} ${name}`,
                items: [...baseItems, ...extraHardItems],
                stopRule: 4, // si 4 échecs cumulés dans ce sous-test, on arrête (comme WISC)
            };
        }
        // Chaque sous-test contient entre 18 et 26 items, difficulté croissante
        const subtests = [
            generateSubtest("Matrices", "🖼️",
                [
                    { q: "Complète : ◼ ◻ ◼ ◻ ◼ ?", visual:"◼ ◻ ◼ ◻ ◼ ?", options:["◻","◼","◆","●"], correct:0 },
                    { q: "Suite : ▲ ▶ ▼ ◀ ▲ ?", visual:"▲ ▶ ▼ ◀ ▲ ?", options:["▶","▼","◀","▲"], correct:0 },
                    { q: "Symboles : ○ ● ○ ● ○ ?", visual:"○ ● ○ ● ○ ?", options:["●","○","◇","□"], correct:0 },
                    { q: "Croissants : ☾ ☽ ☾ ☽ ☾ ?", visual:"☾ ☽ ☾ ☽ ☾ ?", options:["☽","☾","★","☀"], correct:0 },
                    { q: "Flèches : ↑ → ↓ ← ↑ ?", visual:"↑ → ↓ ← ↑ ?", options:["→","↓","←","↑"], correct:0 },
                    { q: "Points : ⬤ ◯ ⬤ ◯ ⬤ ?", visual:"⬤ ◯ ⬤ ◯ ⬤ ?", options:["◯","⬤","⬬","◉"], correct:0 },
                    { q: "Étoiles : ★ ☆ ★ ☆ ★ ?", visual:"★ ☆ ★ ☆ ★ ?", options:["☆","★","✦","✧"], correct:0 },
                    { q: "Lune : 🌕 🌖 🌗 🌘 🌑 ?", visual:"🌕🌖🌗🌘🌑?", options:["🌒","🌓","🌔","🌕"], correct:0 },
                    { q: "Carrés : ◧ ◨ ◩ ◪ ?", visual:"◧ ◨ ◩ ◪ ?", options:["◫","◧","◨","◩"], correct:0 },
                    { q: "Triangles : ◢ ◣ ◤ ◥ ◢ ?", visual:"◢◣◤◥◢?", options:["◣","◤","◥","◢"], correct:0 },
                    { q: "Cercles : ◐ ◑ ◒ ◓ ?", visual:"◐◑◒◓?", options:["◐","◔","◕","◑"], correct:1 },
                    { q: "Losanges : ◆ ◇ ◆ ◇ ◆ ?", visual:"◆◇◆◇◆?", options:["◇","◆","◈","⬖"], correct:0 },
                ],
                [
                    { q: "Motif complexe : ⬡ ⬢ ⬡ ⬢ ?", visual:"⬡⬢⬡⬢?", options:["⬡","⬢","⬣","⬟"], correct:0 },
                    { q: "Spirale : ◌ ◍ ◎ ● ◉ ?", visual:"◌◍◎●◉?", options:["◌","○","◐","◒"], correct:0 },
                    { q: "Flèches doubles : ⇐ ⇑ ⇒ ⇓ ⇐ ?", visual:"⇐⇑⇒⇓⇐?", options:["⇑","⇒","⇓","⇐"], correct:0 },
                    { q: "Rotation : ↻ ↺ ↻ ↺ ?", visual:"↻↺↻↺?", options:["↻","↺","↻","↝"], correct:0 },
                    { q: "Puzzle visuel : ◰ ◱ ◲ ◳ ?", visual:"◰◱◲◳?", options:["◰","◱","◳","◲"], correct:1 },
                    { q: "Alternance binaire : ◧ ◨ ◧ ◨ ?", visual:"◧◨◧◨?", options:["◨","◧","◩","◪"], correct:0 },
                    { q: "Symbole croissant : ◸ ◹ ◺ ◻ ?", visual:"◸◹◺◻?", options:["◸","◹","◼","◻"], correct:0 },
                    { q: "Quadrillage : ╋ ┣ ┫ ┻ ?", visual:"╋┣┫┻?", options:["╋","┣","┳","┫"], correct:0 },
                ]),
            generateSubtest("Vocabulaire", "📚",
                [
                    { q:"Que signifie 'lacune' ?", options:["Manque","Excès","Rapidité","Silence"], correct:0 },
                    { q:"Synonyme de 'bravoure' ?", options:["Peur","Courage","Tristesse","Faiblesse"], correct:1 },
                    { q:"'Éphémère' veut dire ?", options:["Durable","Passager","Solide","Ancien"], correct:1 },
                    { q:"Qu'est-ce qu'un 'récif' ?", options:["Outil","Rocher marin","Vent","Poisson"], correct:1 },
                    { q:"'Perplexe' signifie ?", options:["Enthousiaste","Hésitant","Confus","Joyeux"], correct:2 },
                    { q:"'Opulent' :", options:["Pauvre","Riche","Simple","Moderne"], correct:1 },
                    { q:"'Prolixe' :", options:["Silencieux","Bavard","Précis","Rapide"], correct:1 },
                    { q:"'Altruiste' :", options:["Égoïste","Généreux","Solitaire","Fier"], correct:1 },
                    { q:"'Laconique' :", options:["Long","Concis","Complexe","Détaillé"], correct:1 },
                    { q:"'Immuable' :", options:["Changeant","Fixe","Liquide","Fragile"], correct:1 },
                    { q:"'Vorace' :", options:["Délicat","Gourmand","Patient","Timide"], correct:1 },
                    { q:"'Onerux' :", options:["Gratuit","Coûteux","Léger","Rapide"], correct:1 },
                ],
                [
                    { q:"'Pusillanime' :", options:["Courageux","Timoré","Fier","Grand"], correct:1 },
                    { q:"'Objurgation' :", options:["Blâme sévère","Louange","Indifférence","Rire"], correct:0 },
                    { q:"'Sycophante' :", options:["Personne honnête","Délateur flatteur","Artiste","Soldat"], correct:1 },
                    { q:"'Ataraxie' :", options:["Excitation","Tranquillité absolue","Colère","Peur"], correct:1 },
                    { q:"'Inénarrable' :", options:["Banal","Indescriptible","Rapide","Visible"], correct:1 },
                    { q:"'Velléité' :", options:["Volonté ferme","Intention faible","Force","Clarté"], correct:1 },
                ]),
            generateSubtest("Balances", "⚖️",
                [
                    { q:"★★ = 4, ★★★ = ?", visual:"★★=4", options:["5","6","7","8"], correct:1 },
                    { q:"●=3, ●●●= ?", visual:"●=3", options:["6","9","12","8"], correct:1 },
                    { q:"♣♣=10, ♣♣♣♣= ?", visual:"♣♣=10", options:["15","18","20","25"], correct:2 },
                    { q:"◆◆◆=12, ◆◆◆◆◆= ?", visual:"◆◆◆=12", options:["16","20","22","24"], correct:1 },
                    { q:"☀☀=8, ☀☀☀☀= ?", visual:"☀☀=8", options:["12","14","16","18"], correct:2 },
                    { q:"▼▼▼=9, ▼▼▼▼▼▼= ?", visual:"▼▼▼=9", options:["15","18","21","24"], correct:1 },
                    { q:"◇◇◇◇=16, ◇◇= ?", visual:"◇◇◇◇=16", options:["4","6","8","10"], correct:2 },
                    { q:"✿✿✿=15, ✿✿✿✿= ?", visual:"✿✿✿=15", options:["18","20","22","25"], correct:1 },
                    { q:"⚡⚡=14, ⚡⚡⚡= ?", visual:"⚡⚡=14", options:["18","21","24","28"], correct:1 },
                ],[
                    { q:"Si ♠♠♠=18 et ♠=6, combien ♠♠♠♠♠?", options:["24","28","30","32"], correct:2 },
                    { q:"⚖️ équilibre: ●● = ▲▲▲▲ (●=4) alors ▲=?", options:["1","2","3","4"], correct:0 },
                    { q:"★★★ + ●● = 20 (★=4), ●=?", options:["2","3","4","5"], correct:2 },
                    { q:"△△△ = 9, □□ = △△△△, □=?", options:["4","5","6","7"], correct:2 },
                ]),
            generateSubtest("Puzzles visuels", "🧩",
                [
                    { q:"Pièce manquante : 🔲🔲?🔲", visual:"⬜⬛⬜?⬜", options:["⬛","⬜","⬜","🔲"], correct:0 },
                    { q:"△□△□△ ?", visual:"△□△□△?", options:["□","△","○","☆"], correct:0 },
                    { q:"🌕🌑🌕🌑🌕 ?", visual:"🌕🌑🌕🌑🌕?", options:["🌑","🌕","🌗","🌒"], correct:0 },
                    { q:"◢◣◢◣◢ ?", visual:"◢◣◢◣◢?", options:["◣","◢","◤","◥"], correct:0 },
                    { q:"⚫⚪⚫⚪⚫ ?", visual:"⚫⚪⚫⚪⚫?", options:["⚪","⚫","🔘","⭕"], correct:0 },
                    { q:"🔺🔻🔺🔻🔺 ?", visual:"🔺🔻🔺🔻🔺?", options:["🔻","🔺","🔷","🔶"], correct:0 },
                    { q:"🟦🟥🟦🟥🟦 ?", visual:"🟦🟥🟦🟥🟦?", options:["🟥","🟦","🟨","🟩"], correct:0 },
                ],[
                    { q:"Motif 3x3 : ▦ ▧ ▦ ?", visual:"▦▧▦?", options:["▧","▦","▨","▩"], correct:0 },
                ]),
            generateSubtest("Mémoire d'images", "🖼️",
                [
                    { q:"🐶 montré, lequel ?", visual:"🐶", options:["🐱","🐶","🐭","🐹"], correct:1 },
                    { q:"🌲", visual:"🌲", options:["🌳","🌲","🎄","🌴"], correct:1 },
                    { q:"🚗", visual:"🚗", options:["🚙","🚗","🚕","🚓"], correct:1 },
                    { q:"🍎", visual:"🍎", options:["🍏","🍎","🍊","🍇"], correct:1 },
                    { q:"⭐", visual:"⭐", options:["🌟","⭐","✨","💫"], correct:1 },
                    { q:"☎️", visual:"☎️", options:["📞","☎️","📱","📠"], correct:1 },
                ],[
                    { q:"🦋", visual:"🦋", options:["🐝","🦋","🐞","🪲"], correct:1 },
                    { q:"🎸", visual:"🎸", options:["🎹","🎸","🎺","🥁"], correct:1 },
                ]),
            generateSubtest("Connaissances", "🌍",
                [
                    { q:"Combien de continents ?", options:["5","6","7","8"], correct:2 },
                    { q:"Qui a peint la Joconde ?", options:["Van Gogh","Picasso","L. de Vinci","Rembrandt"], correct:2 },
                    { q:"Capitale du Japon ?", options:["Séoul","Tokyo","Pékin","Bangkok"], correct:1 },
                    { q:"Jours année bissextile ?", options:["364","365","366","367"], correct:2 },
                    { q:"Plus grand océan ?", options:["Atlantique","Indien","Arctique","Pacifique"], correct:3 },
                    { q:"Auteur Roméo & Juliette ?", options:["Molière","Shakespeare","Cervantes","Hugo"], correct:1 },
                ],[
                    { q:"Élément chimique H ?", options:["Oxygène","Hydrogène","Hélium","Azote"], correct:1 },
                    { q:"Planète la plus proche du Soleil ?", options:["Vénus","Terre","Mercure","Mars"], correct:2 },
                ]),
            generateSubtest("Similitudes", "🔤",
                [
                    { q:"Chien - Chat", options:["Animaux domestiques","Mammifères","Poils","Compagnons"], correct:1 },
                    { q:"Colère - Joie", options:["Émotions","Réactions","Humeurs","Sentiments"], correct:0 },
                    { q:"Pomme - Banane", options:["Fruits","Aliments","Comestibles","Sucrés"], correct:0 },
                    { q:"Marteau - Tournevis", options:["Outils","Objets","Fer","Bricolage"], correct:0 },
                    { q:"Rouge - Bleu", options:["Couleurs primaires","Teintes","Visibles","Arc-en-ciel"], correct:0 },
                    { q:"Médecin - Enseignant", options:["Professions","Métiers","Aident","Respectés"], correct:0 },
                ],[
                    { q:"Liberté - Égalité", options:["Valeurs républicaines","Mots","Idées","Droits"], correct:0 },
                ]),
        ];
        // ----- ÉTAT GLOBAL -----
        let currentSubtest = 0;
        let currentItem = 0;
        let answers = subtests.map(sub => new Array(sub.items.length).fill(null));
        let subtestFinished = subtests.map(() => false); // true si règle d'arrêt ou terminé
        let testFinished = false;
        // Compte les échecs cumulés dans le sous-test courant (pour règle d'arrêt)
        function countFailuresInSubtest(subIdx) {
            let fails = 0;
            for (let i = 0; i < subtests[subIdx].items.length; i++) {
                const ans = answers[subIdx][i];
                if (ans !== null && ans !== subtests[subIdx].items[i].correct) {
                    fails++;
                }
            }
            return fails;
        }
        function advanceToNextSubtest() {
            subtestFinished[currentSubtest] = true;
            // Cherche prochain sous-test non fini
            let next = currentSubtest + 1;
            while (next < subtests.length && subtestFinished[next]) next++;
            if (next >= subtests.length) {
                testFinished = true;
            } else {
                currentSubtest = next;
                currentItem = 0;
            }
        }
        function render() {
            const ui = document.getElementById('dynamicUI');
            if (testFinished) {
                showFinalResults(ui);
                return;
            }
            const sub = subtests[currentSubtest];
            const item = sub.items[currentItem];
            const selected = answers[currentSubtest][currentItem];
            const globalProgress = subtests.reduce((acc, s, idx) => {
                for (let i=0; i<s.items.length; i++) if(answers[idx][i]!==null) acc++;
                return acc;
            }, 0);
            const totalItemsAll = subtests.reduce((s, sub) => s+sub.items.length, 0);
            let html = `
                <div class="progress-bar">
                    <span class="badge">${globalProgress}/${totalItemsAll}</span>
                    <span style="color:#fadf9e;">${sub.name} · item ${currentItem+1}/${sub.items.length}</span>
                </div>
                <div class="subtest-header">${sub.name}</div>
                <div class="card">
            `;
            if(item.visual) html += `<div class="visual-large">${item.visual}</div>`;
            html += `<div class="question">${item.q}</div>`;
            html += `<div class="options-grid ${item.options.length===4?'col4':''}" id="opts">`;
            item.options.forEach((opt,idx)=>{
                html += `<div class="opt-btn${selected===idx?' selected':''}" data-idx="${idx}">${opt}</div>`;
            });
            html += `</div>`;
            if(subtestFinished[currentSubtest]) {
                html += `<div class="stop-message">⏹️ Sous-test terminé (règle d'arrêt atteinte).</div>`;
            }
            html += `<div class="nav-buttons">
                <button class="btn" id="prevBtn" ${(currentSubtest===0 && currentItem===0)?'disabled':''}>◀ Précédent</button>
                <button class="btn" id="nextBtn">${(currentSubtest===subtests.length-1 && (currentItem===sub.items.length-1 || subtestFinished[currentSubtest]))?'🏁 Terminer':'Suivant ▶'}</button>
            </div></div>`;
            ui.innerHTML = html;
            // Events options
            document.querySelectorAll('#opts .opt-btn').forEach(btn => {
                btn.addEventListener('click', function(){
                    if(subtestFinished[currentSubtest]) return;
                    const idx = parseInt(this.dataset.idx);
                    answers[currentSubtest][currentItem] = idx;
                    document.querySelectorAll('#opts .opt-btn').forEach(b=>b.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            document.getElementById('prevBtn')?.addEventListener('click', ()=>{
                if(currentItem>0) currentItem--;
                else if(currentSubtest>0){
                    let prev = currentSubtest-1;
                    while(prev>=0 && subtestFinished[prev]) prev--;
                    if(prev>=0){ currentSubtest=prev; currentItem=subtests[prev].items.length-1; }
                }
                render();
            });
            document.getElementById('nextBtn')?.addEventListener('click', ()=>{
                if(subtestFinished[currentSubtest]){
                    advanceToNextSubtest();
                    render();
                    return;
                }
                // Vérifier règle d'arrêt après avoir répondu ?
                const failures = countFailuresInSubtest(currentSubtest);
                if(failures >= sub.stopRule){
                    subtestFinished[currentSubtest]=true;
                    advanceToNextSubtest();
                    render();
                    return;
                }
                if(currentItem === sub.items.length-1){
                    subtestFinished[currentSubtest]=true;
                    advanceToNextSubtest();
                } else {
                    currentItem++;
                }
                render();
            });
        }
        function showFinalResults(container){
            let totalCorrect=0, totalItems=0;
            subtests.forEach((sub,idx)=>{
                for(let i=0;i<sub.items.length;i++){
                    totalItems++;
                    if(answers[idx][i]===sub.items[i].correct) totalCorrect++;
                }
            });
            const iq = Math.min(150, Math.round(70 + (totalCorrect/totalItems)*80));
            container.innerHTML = `
                <div class="result-screen">
                    <h2 style="color:#f5cd6e;">Résultat WISC-V</h2>
                    <div class="iq-big">${iq}</div>
                    <p style="font-size:1.4rem;">${totalCorrect}/${totalItems} bonnes réponses</p>
                    <p style="color:#bcc6dd;">Basé sur 7 indices · règles d'arrêt appliquées</p>
                    <hr>
                    <button class="btn" id="restartBtn">🔄 Recommencer le test complet</button>
                </div>
            `;
            document.getElementById('restartBtn').addEventListener('click',()=>{
                answers = subtests.map(sub=>new Array(sub.items.length).fill(null));
                subtestFinished = subtests.map(()=>false);
                currentSubtest=0; currentItem=0; testFinished=false;
                render();
            });
        }
        render();
    })();
</script>
</body>
</html>
