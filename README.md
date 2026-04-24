<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Test QI • WISC-V Ultra Complet</title>
    <style>
        :root {
            --bg: #080c15;
            --card: #111827;
            --gold: #d4942b;
            --goldlight: #f5d078;
            --text: #e8e0d0;
            --muted: #8892a8;
            --accent: #283148;
            --danger: #c44;
            --success: #5b8;
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
            padding: 1rem;
            background-image: radial-gradient(ellipse at 25% 20%, #1a1f30 0%, #05070c 90%);
        }
        .container {
            max-width: 900px;
            width: 100%;
            background: rgba(15, 19, 30, 0.9);
            backdrop-filter: blur(30px);
            border-radius: 2.5rem;
            padding: 1.5rem 1.5rem 2rem;
            border: 1px solid rgba(200, 160, 50, 0.25);
            box-shadow: 0 40px 70px rgba(0, 0, 0, 0.9);
        }
        h1 {
            font-size: 2.2rem;
            text-align: center;
            letter-spacing: 2px;
            background: linear-gradient(180deg, #ffe69b, #b8781c);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 0.1rem;
            font-weight: 700;
        }
        .subtitle {
            text-align: center;
            color: #a0b0cf;
            margin-bottom: 1rem;
            font-size: 0.85rem;
            border-bottom: 1px dashed #444b60;
            padding-bottom: 0.7rem;
        }
        .progress {
            background: #1a1f32;
            border-radius: 2rem;
            padding: 0.5rem 1.2rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1rem;
            border: 1px solid #ffb34744;
            flex-wrap: wrap;
        }
        .badge {
            background: #d4942b;
            color: #090c14;
            font-weight: 700;
            padding: 0.25rem 1rem;
            border-radius: 2rem;
            font-size: 0.8rem;
        }
        .subtest-name {
            font-size: 1.4rem;
            font-weight: 600;
            color: #f7d37a;
            margin-bottom: 0.8rem;
        }
        .card {
            background: #141b2b;
            border-radius: 1.8rem;
            padding: 1.4rem;
            border: 1px solid rgba(255, 255, 255, 0.06);
            margin-bottom: 0.5rem;
        }
        .memory-timer {
            font-size: 3rem;
            text-align: center;
            color: #ffd966;
            font-weight: 800;
            margin: 0.5rem 0;
        }
        .memory-image {
            font-size: 7rem;
            text-align: center;
            margin: 0.5rem 0;
            filter: drop-shadow(0 10px 15px black);
        }
        .visual-display {
            font-size: 3.5rem;
            text-align: center;
            letter-spacing: 6px;
            margin: 0.6rem 0;
            color: #fff3da;
            filter: drop-shadow(0 5px 8px #00000080);
        }
        .question-text {
            font-size: 1.4rem;
            margin: 0.8rem 0 1rem;
            color: var(--text);
            line-height: 1.4;
        }
        .grid-2 {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.7rem;
            margin: 1rem 0;
        }
        .grid-4 {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 0.6rem;
            margin: 1rem 0;
        }
        @media (max-width: 500px) {
            .grid-4 {
                grid-template-columns: repeat(2, 1fr);
            }
        }
        .opt {
            background: #1f283d;
            border: 2px solid rgba(255, 190, 60, 0.35);
            border-radius: 1.2rem;
            padding: 0.8rem 0.5rem;
            font-size: 1rem;
            font-weight: 500;
            color: #d8d4c8;
            cursor: pointer;
            transition: 0.2s;
            text-align: center;
            word-break: break-word;
        }
        .opt:hover {
            background: #374362;
            border-color: #f9b84a;
            color: white;
        }
        .opt.selected {
            background: #d4942b;
            border-color: #ffe288;
            color: #0b0e18;
            font-weight: 700;
            box-shadow: 0 0 16px #f90;
        }
        .opt.correct-reveal {
            background: #3a7d4a;
            border-color: #5f8;
        }
        .opt.wrong-reveal {
            background: #8b3a3a;
            border-color: #f66;
        }
        .nav-row {
            display: flex;
            justify-content: space-between;
            margin-top: 1rem;
            gap: 0.8rem;
        }
        .btn {
            background: #283148;
            border: 1px solid #e7a843;
            color: #f5edd8;
            padding: 0.7rem 1.6rem;
            border-radius: 2.5rem;
            font-weight: 700;
            cursor: pointer;
            transition: 0.2s;
            font-size: 0.95rem;
        }
        .btn:hover:not(:disabled) {
            background: #c0802a;
            border-color: #ffe7b0;
            color: #111;
        }
        .btn:disabled {
            opacity: 0.4;
            pointer-events: none;
        }
        .hidden {
            display: none !important;
        }
        .result-box {
            text-align: center;
            padding: 1rem;
        }
        .iq-big {
            font-size: 5rem;
            font-weight: 800;
            background: linear-gradient(180deg, #ffe484, #b87014);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .memory-phase {
            text-align: center;
            padding: 1rem;
        }
        hr {
            border-color: #50472f;
            margin: 1rem 0;
        }
        .cube-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 0.4rem;
            max-width: 200px;
            margin: 1rem auto;
        }
        .cube-cell {
            aspect-ratio: 1;
            border-radius: 0.4rem;
            border: 1px solid #555;
        }
    </style>
</head>
<body>
<div class="container" id="app">
    <h1>🧠 WISC-V ULTRA</h1>
    <div class="subtitle">9 sous-tests · Mémoire chronométrée · Difficulté réelle</div>
    <div id="dynamicUI"></div>
</div>
<script>
    (function() {
        // ==================== SOUS-TESTS ====================
        const subtests = [
            // 1. MÉMOIRE D'IMAGES (affichage 15s puis disparition)
            {
                name: "📸 Mémoire d'images",
                type: "memory",
                items: [
                    { image: "🐶", options: ["🐱", "🐶", "🐭", "🐹", "🐰", "🦊"], correct: 1 },
                    { image: "🌲", options: ["🌳", "🎄", "🌲", "🌴", "🌿", "🍀"], correct: 2 },
                    { image: "🚀", options: ["✈️", "🚁", "🛸", "🚀", "🛩️", "🚂"], correct: 3 },
                    { image: "🎻", options: ["🎸", "🎹", "🎺", "🥁", "🎻", "🪕"], correct: 4 },
                    { image: "🗼", options: ["🗽", "🗼", "🏰", "🏯", "🗿", "🕌"], correct: 1 },
                    { image: "🦋", options: ["🐝", "🐞", "🦋", "🪲", "🐛", "🪰"], correct: 2 },
                    { image: "⚓", options: ["⚓", "🛟", "🛶", "⛵", "🚢", "🏴‍☠️"], correct: 0 },
                    { image: "🎭", options: ["🎪", "🎭", "🎬", "🎤", "🎧", "📺"], correct: 1 },
                ],
                displayTime: 15
            },
            // 2. CULTURE GÉNÉRALE (niveau adulte)
            {
                name: "🌍 Culture générale",
                type: "standard",
                items: [
                    { q: "Qui a écrit 'Les Misérables' ?", options: ["Zola", "Hugo", "Balzac", "Flaubert", "Stendhal", "Dumas"], correct: 1 },
                    { q: "Quelle est la capitale de la Mongolie ?", options: ["Astana", "Oulan-Bator", "Bichkek", "Tachkent", "Douchanbé", "Almaty"], correct: 1 },
                    { q: "En quelle année le mur de Berlin est-il tombé ?", options: ["1987", "1988", "1989", "1990", "1991", "1985"], correct: 2 },
                    { q: "Quel élément a le numéro atomique 79 ?", options: ["Argent", "Or", "Platine", "Mercure", "Plomb", "Cuivre"], correct: 1 },
                    { q: "Qui a peint 'Guernica' ?", options: ["Dalí", "Miró", "Picasso", "Goya", "Velázquez", "El Greco"], correct: 2 },
                    { q: "Quel est le plus long fleuve du monde ?", options: ["Nil", "Amazone", "Mississippi", "Yangtsé", "Congo", "Mékong"], correct: 0 },
                    { q: "Qui a composé 'Les Quatre Saisons' ?", options: ["Bach", "Mozart", "Vivaldi", "Beethoven", "Haendel", "Chopin"], correct: 2 },
                    { q: "Quelle est la monnaie du Japon ?", options: ["Yuan", "Won", "Yen", "Ringgit", "Baht", "Dong"], correct: 2 },
                    { q: "Qui a découvert la pénicilline ?", options: ["Pasteur", "Fleming", "Koch", "Jenner", "Ehrlich", "Sabin"], correct: 1 },
                    { q: "Quel pays a le plus de fuseaux horaires ?", options: ["USA", "Russie", "France", "Chine", "Canada", "Australie"], correct: 2 },
                    { q: "Qui a écrit 'L'Étranger' ?", options: ["Sartre", "Camus", "Beauvoir", "Ionesco", "Beckett", "Genet"], correct: 1 },
                    { q: "Quelle est la planète la plus proche du Soleil ?", options: ["Vénus", "Terre", "Mercure", "Mars", "Jupiter", "Saturne"], correct: 2 },
                    { q: "En quelle année a eu lieu la Révolution française ?", options: ["1776", "1789", "1792", "1799", "1804", "1785"], correct: 1 },
                    { q: "Qui a peint le plafond de la Chapelle Sixtine ?", options: ["Raphaël", "Michel-Ange", "Léonard", "Donatello", "Botticelli", "Caravage"], correct: 1 },
                    { q: "Quel est le plus grand désert du monde ?", options: ["Sahara", "Gobi", "Antarctique", "Kalahari", "Atacama", "Sonora"], correct: 2 },
                ]
            },
            // 3. VOCABULAIRE (niveau adulte)
            {
                name: "📚 Vocabulaire",
                type: "standard",
                items: [
                    { q: "Que signifie 'pusillanime' ?", options: ["Courageux", "Timoré", "Fier", "Grand", "Rapide", "Fort"], correct: 1 },
                    { q: "Que signifie 'objurgation' ?", options: ["Louange", "Blâme sévère", "Indifférence", "Rire", "Chant", "Prière"], correct: 1 },
                    { q: "Que signifie 'sycophante' ?", options: ["Honnête", "Délateur", "Artiste", "Soldat", "Médecin", "Juge"], correct: 1 },
                    { q: "Que signifie 'ataraxie' ?", options: ["Excitation", "Tranquillité", "Colère", "Peur", "Joie", "Tristesse"], correct: 1 },
                    { q: "Que signifie 'inénarrable' ?", options: ["Banal", "Indescriptible", "Rapide", "Visible", "Lourd", "Simple"], correct: 1 },
                    { q: "Que signifie 'velléité' ?", options: ["Volonté ferme", "Intention faible", "Force", "Clarté", "Beauté", "Vitesse"], correct: 1 },
                    { q: "Que signifie 'prolégomènes' ?", options: ["Conclusion", "Introduction", "Digression", "Résumé", "Index", "Annexe"], correct: 1 },
                    { q: "Que signifie 'palimpseste' ?", options: ["Manuscrit gratté", "Pierre précieuse", "Poème", "Discours", "Château", "Armure"], correct: 0 },
                    { q: "Que signifie 'uxorilocal' ?", options: ["Nomade", "Résidence chez l'épouse", "Célibataire", "Divorcé", "Voyageur", "Ermite"], correct: 1 },
                    { q: "Que signifie 'thuriféraire' ?", options: ["Critique", "Admirateur", "Ennemi", "Marchand", "Paysan", "Soldat"], correct: 1 },
                    { q: "Que signifie 'anomie' ?", options: ["Ordre", "Absence de normes", "Richesse", "Pauvreté", "Joie", "Tristesse"], correct: 1 },
                    { q: "Que signifie 'solipsisme' ?", options: ["Altruisme", "Égocentrisme radical", "Générosité", "Haine", "Amour", "Peur"], correct: 1 },
                ]
            },
            // 4. SIMILITUDES (niveau adulte)
            {
                name: "🔤 Similitudes",
                type: "standard",
                items: [
                    { q: "Démocratie - Dictature", options: ["Régimes politiques", "Idées", "Mots", "Pays", "Guerres", "Traités"], correct: 0 },
                    { q: "Atome - Galaxie", options: ["Taille différente", "Systèmes", "Science", "Espace", "Temps", "Matière"], correct: 1 },
                    { q: "Révolution - Évolution", options: ["Changements", "Vitesse", "Politique", "Biologie", "Histoire", "Guerre"], correct: 0 },
                    { q: "Sonate - Symphonie", options: ["Œuvres musicales", "Instruments", "Orchestres", "Compositeurs", "Notes", "Rythmes"], correct: 0 },
                    { q: "Métaphore - Allégorie", options: ["Figures de style", "Poèmes", "Récits", "Mensonges", "Vérités", "Chansons"], correct: 0 },
                    { q: "Éthique - Morale", options: ["Philosophie", "Règles", "Religion", "Lois", "Coutumes", "Valeurs"], correct: 0 },
                    { q: "Photosynthèse - Respiration", options: ["Processus vitaux", "Plantes", "Animaux", "Chimie", "Biologie", "Énergie"], correct: 0 },
                    { q: "Sismologie - Volcanologie", options: ["Sciences de la Terre", "Montagnes", "Catastrophes", "Géographie", "Histoire", "Physique"], correct: 0 },
                    { q: "Calligraphie - Typographie", options: ["Arts de l'écriture", "Peinture", "Sculpture", "Musique", "Danse", "Théâtre"], correct: 0 },
                    { q: "Paradoxe - Oxymore", options: ["Contradictions", "Vérités", "Mensonges", "Poésie", "Prose", "Théâtre"], correct: 0 },
                    { q: "Économie - Écologie", options: ["Sciences", "Argent", "Nature", "Politique", "Société", "Histoire"], correct: 0 },
                    { q: "Nostalgie - Mélancolie", options: ["Émotions", "Souvenirs", "Tristesse", "Joie", "Peur", "Colère"], correct: 0 },
                ]
            },
            // 5. MATRICES (raisonnement visuel)
            {
                name: "🖼️ Matrices",
                type: "standard",
                items: [
                    { q: "Complète la suite : ◼ ◻ ◼ ◻ ◼ ?", visual: "◼ ◻ ◼ ◻ ◼ ?", options: ["◻", "◼", "◆", "●", "○", "□"], correct: 0 },
                    { q: "Suite : ▲ ▶ ▼ ◀ ▲ ?", visual: "▲ ▶ ▼ ◀ ▲ ?", options: ["▶", "▼", "◀", "▲", "◆", "■"], correct: 0 },
                    { q: "Alternance : ○ ● ○ ● ○ ?", visual: "○ ● ○ ● ○ ?", options: ["●", "○", "◇", "□", "△", "☆"], correct: 0 },
                    { q: "Croissants : ☾ ☽ ☾ ☽ ☾ ?", visual: "☾ ☽ ☾ ☽ ☾ ?", options: ["☽", "☾", "★", "☀", "☁", "☂"], correct: 0 },
                    { q: "Flèches : ↑ → ↓ ← ↑ ?", visual: "↑ → ↓ ← ↑ ?", options: ["→", "↓", "←", "↑", "↗", "↘"], correct: 0 },
                    { q: "Rotation : ↻ ↺ ↻ ↺ ?", visual: "↻ ↺ ↻ ↺ ?", options: ["↻", "↺", "↝", "↜", "⟳", "⟲"], correct: 0 },
                    { q: "Motif complexe : ⬡ ⬢ ⬡ ⬢ ?", visual: "⬡ ⬢ ⬡ ⬢ ?", options: ["⬡", "⬢", "⬣", "⬟", "⬠", "⬡"], correct: 0 },
                    { q: "Symboles : ◐ ◑ ◒ ◓ ?", visual: "◐ ◑ ◒ ◓ ?", options: ["◐", "◔", "◕", "◑", "◒", "◓"], correct: 0 },
                    { q: "Lune : 🌕 🌖 🌗 🌘 🌑 ?", visual: "🌕🌖🌗🌘🌑?", options: ["🌒", "🌓", "🌔", "🌕", "🌖", "🌗"], correct: 0 },
                    { q: "Carrés : ◧ ◨ ◩ ◪ ?", visual: "◧ ◨ ◩ ◪ ?", options: ["◫", "◧", "◨", "◩", "◪", "◰"], correct: 0 },
                ]
            },
            // 6. BALANCES (équations visuelles)
            {
                name: "⚖️ Balances",
                type: "standard",
                items: [
                    { q: "★★ = 4, donc ★★★ = ?", visual: "★★ = 4", options: ["5", "6", "7", "8", "9", "10"], correct: 1 },
                    { q: "● = 3, donc ●●●● = ?", visual: "● = 3", options: ["9", "10", "11", "12", "13", "14"], correct: 3 },
                    { q: "♣♣ = 10, donc ♣♣♣♣♣ = ?", visual: "♣♣ = 10", options: ["20", "22", "24", "25", "26", "28"], correct: 3 },
                    { q: "◆◆◆ = 12, ◆◆◆◆◆ = ?", visual: "◆◆◆ = 12", options: ["16", "18", "20", "22", "24", "26"], correct: 2 },
                    { q: "☀☀ = 8, ☀☀☀☀ = ?", visual: "☀☀ = 8", options: ["12", "14", "15", "16", "18", "20"], correct: 3 },
                    { q: "▼▼▼ = 9, ▼▼▼▼▼▼ = ?", visual: "▼▼▼ = 9", options: ["15", "16", "17", "18", "19", "20"], correct: 3 },
                    { q: "◇◇◇◇ = 16, ◇◇ = ?", visual: "◇◇◇◇ = 16", options: ["4", "6", "7", "8", "9", "10"], correct: 3 },
                    { q: "✿✿✿ = 15, ✿✿✿✿✿ = ?", visual: "✿✿✿ = 15", options: ["20", "22", "24", "25", "26", "28"], correct: 3 },
                    { q: "⚡⚡ = 14, ⚡⚡⚡ = ?", visual: "⚡⚡ = 14", options: ["18", "20", "21", "22", "24", "28"], correct: 2 },
                    { q: "♠♠♠ = 18, ♠♠♠♠♠ = ?", visual: "♠♠♠ = 18", options: ["24", "26", "28", "30", "32", "34"], correct: 3 },
                ]
            },
            // 7. CUBES (rotation mentale)
            {
                name: "🧊 Cubes",
                type: "standard",
                items: [
                    { q: "Quel cube correspond après rotation ?", visual: "🧊↻", options: ["⬜⬛⬜\n⬛⬜⬛\n⬜⬛⬜", "⬛⬜⬛\n⬜⬛⬜\n⬛⬜⬛", "⬜⬜⬜\n⬛⬛⬛\n⬜⬜⬜", "⬛⬛⬛\n⬜⬜⬜\n⬛⬛⬛", "⬜⬛⬛\n⬛⬜⬛\n⬛⬛⬜", "⬛⬜⬜\n⬜⬛⬜\n⬜⬜⬛"], correct: 0 },
                ]
            },
            // 8. PUZZLES VISUELS
            {
                name: "🧩 Puzzles",
                type: "standard",
                items: [
                    { q: "Pièce manquante : 🔲🔲?🔲🔲", visual: "⬜⬛⬜?⬜⬛", options: ["⬛", "⬜", "🔲", "⬜", "◼", "◻"], correct: 0 },
                    { q: "△□△□△□△ ?", visual: "△□△□△□△?", options: ["□", "△", "○", "☆", "◇", "▽"], correct: 0 },
                    { q: "🌕🌑🌕🌑🌕🌑🌕 ?", visual: "🌕🌑🌕🌑🌕🌑🌕?", options: ["🌑", "🌕", "🌗", "🌒", "🌓", "🌔"], correct: 0 },
                    { q: "◢◣◢◣◢◣◢ ?", visual: "◢◣◢◣◢◣◢?", options: ["◣", "◢", "◤", "◥", "◧", "◨"], correct: 0 },
                    { q: "⚫⚪⚫⚪⚫⚪⚫ ?", visual: "⚫⚪⚫⚪⚫⚪⚫?", options: ["⚪", "⚫", "🔘", "⭕", "◉", "◎"], correct: 0 },
                    { q: "🔺🔻🔺🔻🔺🔻🔺 ?", visual: "🔺🔻🔺🔻🔺🔻🔺?", options: ["🔻", "🔺", "🔷", "🔶", "🔸", "🔹"], correct: 0 },
                    { q: "🟦🟥🟦🟥🟦🟥🟦 ?", visual: "🟦🟥🟦🟥🟦🟥🟦?", options: ["🟥", "🟦", "🟨", "🟩", "🟪", "🟫"], correct: 0 },
                    { q: "▦▧▦▧▦▧▦ ?", visual: "▦▧▦▧▦▧▦?", options: ["▧", "▦", "▨", "▩", "▤", "▥"], correct: 0 },
                ]
            },
            // 9. BARRAGE (attention visuelle)
            {
                name: "🔍 Barrage",
                type: "standard",
                items: [
                    { q: "Combien de ◆ dans : ◆◇◆◇◇◆◇◆◆◇ ?", visual: "◆◇◆◇◇◆◇◆◆◇", options: ["3", "4", "5", "6", "7", "8"], correct: 2 },
                    { q: "Compte les ● : ●○●●○○●○●●○●", visual: "●○●●○○●○●●○●", options: ["5", "6", "7", "8", "9", "10"], correct: 2 },
                ]
            }
        ];

        // ==================== STATE ====================
        let currentSubtest = 0;
        let currentItem = 0;
        let answers = subtests.map(s => new Array(s.items.length).fill(null));
        let testFinished = false;
        // Pour mémoire
        let memoryPhase = 'show'; // 'show' | 'answer'
        let memoryTimer = null;
        let memorySecondsLeft = 0;

        function stopMemoryTimer() {
            if (memoryTimer) { clearInterval(memoryTimer); memoryTimer = null; }
        }

        function startMemoryDisplay(subtest) {
            memoryPhase = 'show';
            memorySecondsLeft = subtest.displayTime || 15;
            render();
            stopMemoryTimer();
            memoryTimer = setInterval(() => {
                memorySecondsLeft--;
                const timerEl = document.getElementById('memoryTimerDisplay');
                if (timerEl) timerEl.textContent = memorySecondsLeft + 's';
                if (memorySecondsLeft <= 0) {
                    stopMemoryTimer();
                    memoryPhase = 'answer';
                    render();
                }
            }, 1000);
        }

        function render() {
            const ui = document.getElementById('dynamicUI');
            if (testFinished) {
                showResults(ui);
                return;
            }
            const sub = subtests[currentSubtest];
            const item = sub.items[currentItem];
            const selected = answers[currentSubtest][currentItem];
            const globalProgress = subtests.reduce((acc, s, idx) => {
                for (let i = 0; i < s.items.length; i++) if (answers[idx][i] !== null) acc++;
                return acc;
            }, 0);
            const totalItems = subtests.reduce((s, sub) => s + sub.items.length, 0);

            // Si mémoire et phase 'show'
            if (sub.type === 'memory' && memoryPhase === 'show') {
                ui.innerHTML = `
                    <div class="progress"><span class="badge">${globalProgress}/${totalItems}</span><span>${sub.name}</span></div>
                    <div class="card memory-phase">
                        <p style="color:#fadf9e;">Mémorisez cette image :</p>
                        <div class="memory-image">${item.image}</div>
                        <div class="memory-timer" id="memoryTimerDisplay">${memorySecondsLeft}s</div>
                        <p style="color:#8892a8;">L'image va disparaître...</p>
                    </div>
                `;
                return;
            }

            // Affichage normal ou phase réponse mémoire
            let html = `
                <div class="progress">
                    <span class="badge">${globalProgress}/${totalItems}</span>
                    <span style="color:#fadf9e;">${sub.name} · ${currentItem+1}/${sub.items.length}</span>
                </div>
                <div class="subtest-name">${sub.name}</div>
                <div class="card">
            `;
            if (sub.type === 'memory' && memoryPhase === 'answer') {
                html += `<p style="color:#ffb347; text-align:center; margin-bottom:0.8rem;">⏰ Temps écoulé ! Quelle image était affichée ?</p>`;
            }
            if (item.visual) {
                html += `<div class="visual-display">${item.visual}</div>`;
            }
            html += `<div class="question-text">${item.q}</div>`;
            const gridClass = item.options.length <= 4 ? 'grid-2' : 'grid-4';
            html += `<div class="${gridClass}" id="optsContainer">`;
            item.options.forEach((opt, idx) => {
                let cls = 'opt';
                if (selected === idx) cls += ' selected';
                html += `<div class="${cls}" data-idx="${idx}">${opt}</div>`;
            });
            html += `</div>`;
            html += `
                <div class="nav-row">
                    <button class="btn" id="prevBtn" ${(currentSubtest===0 && currentItem===0)?'disabled':''}>◀ Précédent</button>
                    <button class="btn" id="nextBtn">${(currentSubtest===subtests.length-1 && currentItem===sub.items.length-1)?'🏁 Terminer':'Suivant ▶'}</button>
                </div></div>`;
            ui.innerHTML = html;

            // Events options
            document.querySelectorAll('#optsContainer .opt').forEach(btn => {
                btn.addEventListener('click', function() {
                    const idx = parseInt(this.dataset.idx);
                    answers[currentSubtest][currentItem] = idx;
                    document.querySelectorAll('#optsContainer .opt').forEach(b => b.classList.remove('selected'));
                    this.classList.add('selected');
                });
            });
            document.getElementById('prevBtn')?.addEventListener('click', () => {
                stopMemoryTimer();
                if (currentItem > 0) { currentItem--; }
                else if (currentSubtest > 0) { currentSubtest--; currentItem = subtests[currentSubtest].items.length - 1; }
                if (subtests[currentSubtest].type === 'memory') startMemoryDisplay(subtests[currentSubtest]);
                else { memoryPhase = 'answer'; render(); }
            });
            document.getElementById('nextBtn')?.addEventListener('click', () => {
                stopMemoryTimer();
                if (currentSubtest === subtests.length - 1 && currentItem === sub.items.length - 1) {
                    testFinished = true;
                    render();
                } else if (currentItem === sub.items.length - 1) {
                    currentSubtest++;
                    currentItem = 0;
                    if (subtests[currentSubtest].type === 'memory') startMemoryDisplay(subtests[currentSubtest]);
                    else { memoryPhase = 'answer'; render(); }
                } else {
                    currentItem++;
                    if (sub.type === 'memory') startMemoryDisplay(sub);
                    else render();
                }
            });
        }

        function showResults(container) {
            stopMemoryTimer();
            let correct = 0, total = 0;
            subtests.forEach((sub, idx) => {
                for (let i = 0; i < sub.items.length; i++) {
                    total++;
                    if (answers[idx][i] === sub.items[i].correct) correct++;
                }
            });
            const iq = Math.min(150, Math.round(70 + (correct / total) * 80));
            container.innerHTML = `
                <div class="result-box">
                    <h2 style="color:#f5cd6e;">Résultat WISC-V Ultra</h2>
                    <div class="iq-big">${iq}</div>
                    <p style="font-size:1.3rem;">${correct}/${total} bonnes réponses</p>
                    <p style="color:#a0b0cf;">9 sous-tests · Mémoire chronométrée · Niveau adulte</p>
                    <hr>
                    <button class="btn" id="restartBtn">🔄 Recommencer</button>
                </div>
            `;
            document.getElementById('restartBtn').addEventListener('click', () => {
                stopMemoryTimer();
                answers = subtests.map(s => new Array(s.items.length).fill(null));
                currentSubtest = 0;
                currentItem = 0;
                testFinished = false;
                memoryPhase = 'show';
                if (subtests[0].type === 'memory') startMemoryDisplay(subtests[0]);
                else render();
            });
        }

        // Init
        if (subtests[0].type === 'memory') startMemoryDisplay(subtests[0]);
        else render();
    })();
</script>
</body>
</html>
