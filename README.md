<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, maximum-scale=1.5">
  <title>Test QI Type WISC-V • Complet 30 questions</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    body {
      background: linear-gradient(145deg, #1a1e2b 0%, #2a2f3f 100%);
      font-family: 'Segoe UI', Roboto, 'Helvetica Neue', system-ui, sans-serif;
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.5rem;
      margin: 0;
    }
    .container {
      max-width: 950px;
      width: 100%;
      background: rgba(255, 255, 255, 0.07);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      border-radius: 3.5rem;
      padding: 2rem 2rem 2.5rem;
      box-shadow: 0 35px 70px rgba(0, 0, 0, 0.6), inset 0 1px 0 rgba(255, 255, 255, 0.15);
      border: 1px solid rgba(255, 255, 255, 0.1);
      transition: all 0.2s ease;
      color: #f0e9e1;
    }
    h1 {
      font-size: 2.9rem;
      font-weight: 700;
      letter-spacing: 3px;
      text-align: center;
      margin-bottom: 0.3rem;
      background: linear-gradient(135deg, #f9d56e, #f8b042);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      filter: drop-shadow(0 8px 12px rgba(0,0,0,0.5));
      text-transform: uppercase;
    }
    .subtitle {
      text-align: center;
      font-size: 1.1rem;
      color: #b9c6da;
      margin-bottom: 2.2rem;
      font-weight: 400;
      letter-spacing: 1px;
      border-bottom: 1px dashed rgba(255, 200, 100, 0.4);
      padding-bottom: 1.2rem;
    }
    .progress-section {
      background: rgba(10, 12, 20, 0.5);
      border-radius: 3rem;
      padding: 0.9rem 1.8rem;
      margin-bottom: 2rem;
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 180, 60, 0.3);
    }
    .badge {
      background: #f8b042;
      color: #0b0e14;
      font-weight: 700;
      padding: 0.4rem 1.4rem;
      border-radius: 2rem;
      font-size: 0.9rem;
      letter-spacing: 0.5px;
    }
    .progress-text {
      font-weight: 600;
      color: #fadf9e;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }
    .subtest-name {
      font-weight: 700;
      font-size: 1.5rem;
      background: rgba(255, 215, 130, 0.15);
      padding: 0.5rem 1.8rem;
      border-radius: 2.5rem;
      display: inline-block;
      margin-bottom: 1.8rem;
      color: #ffda94;
      border: 1px solid #ffb142;
    }
    .question-card {
      background: rgba(18, 22, 35, 0.8);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-radius: 2.5rem;
      padding: 2rem 2rem 1.8rem;
      margin-bottom: 2rem;
      border: 1px solid rgba(255, 255, 255, 0.1);
      box-shadow: 0 20px 35px rgba(0, 0, 0, 0.7);
    }
    .question-text {
      font-size: 1.8rem;
      font-weight: 500;
      margin-bottom: 2rem;
      line-height: 1.4;
      word-break: break-word;
      color: #f7efe2;
    }
    .options-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 1rem;
      margin: 1.8rem 0 1.2rem;
    }
    .option-btn {
      background: #232a3b;
      border: 2px solid rgba(255, 255, 255, 0.2);
      padding: 1rem 1.2rem;
      border-radius: 1.8rem;
      font-size: 1.2rem;
      font-weight: 500;
      color: #dfdbd2;
      cursor: pointer;
      transition: all 0.25s ease;
      backdrop-filter: blur(5px);
      text-align: left;
      display: flex;
      align-items: center;
      gap: 0.7rem;
      letter-spacing: 0.3px;
    }
    .option-btn:hover:not(:disabled) {
      background: #3f4b64;
      border-color: #f9b84a;
      transform: translateY(-2px);
      box-shadow: 0 12px 20px rgba(0,0,0,0.5);
      color: white;
    }
    .option-btn.selected {
      background: #e6a843;
      border-color: #ffd966;
      color: #0a0c14;
      font-weight: 700;
      box-shadow: 0 0 18px #f90;
    }
    .option-btn:disabled {
      opacity: 0.7;
      cursor: default;
    }
    .nav-buttons {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 1.8rem;
      flex-wrap: wrap;
      gap: 1rem;
    }
    .btn {
      background: #2f354a;
      border: none;
      padding: 0.9rem 2.2rem;
      border-radius: 2.5rem;
      font-weight: 700;
      font-size: 1rem;
      letter-spacing: 0.8px;
      color: #ece6d5;
      cursor: pointer;
      backdrop-filter: blur(12px);
      background: rgba(45, 55, 75, 0.7);
      border: 1px solid rgba(255, 200, 100, 0.5);
      transition: 0.2s;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }
    .btn:hover:not(:disabled) {
      background: #f3b85c;
      color: #121624;
      border-color: #fff2c9;
      box-shadow: 0 0 18px #ffa500;
    }
    .btn:disabled {
      opacity: 0.4;
      pointer-events: none;
    }
    .result-screen {
      background: #1e2332;
      border-radius: 2.5rem;
      padding: 2rem;
      text-align: center;
      backdrop-filter: blur(20px);
      border: 1px solid #f8c25c;
    }
    .iq-score {
      font-size: 5.5rem;
      font-weight: 800;
      background: linear-gradient(180deg, #ffd966, #f09820);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      margin: 0.5rem 0;
    }
    .remark {
      font-size: 1.6rem;
      color: #ffcf8a;
    }
    .hidden {
      display: none !important;
    }
    hr {
      border-color: rgba(255,255,200,0.2);
      margin: 1rem 0;
    }
    .small-note {
      font-size: 0.85rem;
      color: #aaa;
    }
  </style>
</head>
<body>
<div class="container" id="appContainer">
  <h1>🧠 WISC-V PRO</h1>
  <div class="subtitle">Simulation Haute Fidélité • 5 sous-tests • 30 items</div>

  <!-- DYNAMIQUE -->
  <div id="dynamicUI"></div>
</div>

<script>
  (function() {
    // ---- BASE DE DONNÉES DES 5 SOUS-TESTS (6 questions chacun) ----
    const subtests = [
      {
        name: "🔢 Mémoire des chiffres",
        id: "digitSpan",
        instruction: "Répète la séquence dans l'ordre inverse.",
        items: [
          { q: "Séquence : 7 - 4 - 9", options: ["9-4-7", "7-4-9", "4-7-9", "9-7-4"], correct: 0 },
          { q: "Séquence : 2 - 8 - 5 - 1", options: ["1-5-8-2", "2-8-5-1", "5-8-2-1", "1-2-5-8"], correct: 0 },
          { q: "Séquence : 3 - 6 - 2", options: ["2-6-3", "3-6-2", "6-2-3", "2-3-6"], correct: 0 },
          { q: "Séquence : 9 - 1 - 7 - 4", options: ["4-7-1-9", "9-1-7-4", "1-9-4-7", "7-1-9-4"], correct: 0 },
          { q: "Séquence : 5 - 3 - 8 - 2", options: ["2-8-3-5", "5-3-8-2", "3-5-2-8", "8-5-3-2"], correct: 0 },
          { q: "Séquence : 6 - 0 - 4 - 9 - 1", options: ["1-9-4-0-6", "6-0-4-9-1", "0-6-9-4-1", "4-9-1-0-6"], correct: 0 }
        ]
      },
      {
        name: "🔤 Similitudes",
        id: "similarities",
        instruction: "Trouve le point commun le plus spécifique.",
        items: [
          { q: "Chien - Chat", options: ["Animaux domestiques", "Mammifères", "Ont des poils", "Compagnons"], correct: 1 },
          { q: "Colère - Joie", options: ["Émotions", "Sentiments", "Réactions", "Humeurs"], correct: 0 },
          { q: "Pomme - Banane", options: ["Fruits", "Aliments sucrés", "Comestibles", "Poussent sur des arbres"], correct: 0 },
          { q: "Marteau - Tournevis", options: ["Outils", "Objets métalliques", "Bricolage", "Manuels"], correct: 0 },
          { q: "Rouge - Bleu", options: ["Couleurs primaires", "Teintes", "Visibles", "Arc-en-ciel"], correct: 0 },
          { q: "Médecin - Enseignant", options: ["Professions", "Travailleurs", "Aident les autres", "Métiers respectés"], correct: 0 }
        ]
      },
      {
        name: "🧮 Arithmétique",
        id: "arithmetic",
        instruction: "Résous mentalement.",
        items: [
          { q: "Si 4 pommes + 3 pommes = ?", options: ["6", "7", "8", "5"], correct: 1 },
          { q: "12 ÷ 3 = ?", options: ["3", "4", "5", "2"], correct: 1 },
          { q: "7 × 8 = ?", options: ["54", "56", "48", "64"], correct: 1 },
          { q: "25 - 9 = ?", options: ["14", "15", "16", "17"], correct: 2 },
          { q: "La moitié de 50 plus 10 = ?", options: ["30", "35", "25", "40"], correct: 1 },
          { q: "Si 3 cahiers coûtent 6€, combien pour 5 ?", options: ["8€", "10€", "12€", "9€"], correct: 1 }
        ]
      },
      {
        name: "🔲 Matrices logiques",
        id: "matrix",
        instruction: "Complète la suite logique.",
        items: [
          { q: "⬛ ◼ ◼ ⬛ ? (alternance)", options: ["◼", "⬛", "◆", "●"], correct: 0 },
          { q: "2, 4, 6, 8, ?", options: ["9", "10", "12", "11"], correct: 1 },
          { q: "A, C, E, G, ?", options: ["H", "I", "J", "F"], correct: 1 },
          { q: "☆ ☀ ☆ ☀ ☆ ?", options: ["☀", "☆", "☁", "🌙"], correct: 0 },
          { q: "1, 4, 9, 16, ?", options: ["20", "25", "24", "18"], correct: 1 },
          { q: "⬆ ➡ ⬇ ⬅ ⬆ ?", options: ["⬅", "⬇", "➡", "⬆"], correct: 2 }
        ]
      },
      {
        name: "📖 Vocabulaire",
        id: "vocabulary",
        instruction: "Choisis le synonyme le plus proche.",
        items: [
          { q: "Éphémère", options: ["Durable", "Passager", "Éternel", "Léger"], correct: 1 },
          { q: "Prolixe", options: ["Silencieux", "Bavard", "Précis", "Rapide"], correct: 1 },
          { q: "Altruiste", options: ["Égoïste", "Généreux", "Solitaire", "Fier"], correct: 1 },
          { q: "Laconique", options: ["Long", "Concis", "Complexe", "Détaillé"], correct: 1 },
          { q: "Opulent", options: ["Pauvre", "Riche", "Simple", "Moderne"], correct: 1 },
          { q: "Pérenne", options: ["Fragile", "Durable", "Annuel", "Jeune"], correct: 1 }
        ]
      }
    ];

    // --- STATE ---
    const totalSubtests = subtests.length;
    const questionsPerSubtest = 6; // 6 items par sous-test = 30 questions
    let currentSubtestIndex = 0;
    let currentQuestionIndex = 0;
    // Réponses utilisateur : tableau de tableaux [subtest][question] = optionIndex (null si pas répondu)
    let userAnswers = Array(totalSubtests).fill().map(() => Array(questionsPerSubtest).fill(null));
    let testFinished = false;

    // Afficher l'interface courante
    function renderUI() {
      const dynamicUI = document.getElementById('dynamicUI');
      if (!dynamicUI) return;

      if (testFinished) {
        renderResults(dynamicUI);
        return;
      }

      const subtest = subtests[currentSubtestIndex];
      const item = subtest.items[currentQuestionIndex];
      const selectedAnswer = userAnswers[currentSubtestIndex][currentQuestionIndex];
      const totalQuestionsGlobal = totalSubtests * questionsPerSubtest;
      const currentGlobalIndex = currentSubtestIndex * questionsPerSubtest + currentQuestionIndex + 1;

      let html = `
        <div class="progress-section">
          <span class="badge">${currentGlobalIndex} / ${totalQuestionsGlobal}</span>
          <span class="progress-text">📊 Sous-test ${currentSubtestIndex+1}/${totalSubtests} • Question ${currentQuestionIndex+1}/${questionsPerSubtest}</span>
        </div>
        <div class="subtest-name">${subtest.name}</div>
        <div class="question-card">
          <div class="question-text">${item.q}</div>
          <div class="options-grid" id="optionsContainer">
      `;

      item.options.forEach((opt, idx) => {
        const selectedClass = (selectedAnswer === idx) ? 'selected' : '';
        html += `
          <button class="option-btn ${selectedClass}" data-option-index="${idx}" ${testFinished ? 'disabled' : ''}>
            <span style="font-weight:bold; margin-right:4px;">${String.fromCharCode(65 + idx)}.</span> ${opt}
          </button>
        `;
      });

      html += `</div>`;

      // Navigation
      html += `
        <div class="nav-buttons">
          <button class="btn" id="prevBtn" ${(currentSubtestIndex === 0 && currentQuestionIndex === 0) ? 'disabled' : ''}>
            ◀ Précédent
          </button>
          <button class="btn" id="nextBtn">
            ${ (currentSubtestIndex === totalSubtests-1 && currentQuestionIndex === questionsPerSubtest-1) ? '🏁 Terminer' : 'Suivant ▶' }
          </button>
        </div>
        <div class="small-note" style="text-align:center; margin-top:10px;">${subtest.instruction}</div>
      `;

      dynamicUI.innerHTML = html;

      // Attacher les événements aux options
      document.querySelectorAll('.option-btn').forEach(btn => {
        btn.addEventListener('click', function(e) {
          if (testFinished) return;
          const optionIndex = parseInt(this.getAttribute('data-option-index'), 10);
          // Enregistrer la réponse
          userAnswers[currentSubtestIndex][currentQuestionIndex] = optionIndex;
          // Mise à jour visuelle immédiate
          document.querySelectorAll('.option-btn').forEach(b => b.classList.remove('selected'));
          this.classList.add('selected');
        });
      });

      // Bouton précédent
      const prevBtn = document.getElementById('prevBtn');
      if (prevBtn) {
        prevBtn.addEventListener('click', (e) => {
          if (testFinished) return;
          if (currentQuestionIndex > 0) {
            currentQuestionIndex--;
          } else if (currentSubtestIndex > 0) {
            currentSubtestIndex--;
            currentQuestionIndex = questionsPerSubtest - 1;
          }
          renderUI();
        });
      }

      // Bouton suivant / terminer
      const nextBtn = document.getElementById('nextBtn');
      if (nextBtn) {
        nextBtn.addEventListener('click', (e) => {
          if (testFinished) return;
          const isLastQuestionOfSubtest = (currentQuestionIndex === questionsPerSubtest - 1);
          const isLastSubtest = (currentSubtestIndex === totalSubtests - 1);

          if (isLastSubtest && isLastQuestionOfSubtest) {
            // Fin du test complet
            testFinished = true;
            renderUI();
          } else if (isLastQuestionOfSubtest) {
            // Passer au sous-test suivant
            currentSubtestIndex++;
            currentQuestionIndex = 0;
            renderUI();
          } else {
            // Question suivante dans le même sous-test
            currentQuestionIndex++;
            renderUI();
          }
        });
      }
    }

    function calculateIQ() {
      let totalCorrect = 0;
      for (let s = 0; s < totalSubtests; s++) {
        for (let q = 0; q < questionsPerSubtest; q++) {
          const userAns = userAnswers[s][q];
          if (userAns !== null && userAns === subtests[s].items[q].correct) {
            totalCorrect++;
          }
        }
      }
      // Score brut sur 30
      const maxScore = 30;
      // Mapping linéaire vers QI moyen 100, écart-type 15 (plage ~55 à 145)
      let iq = Math.round(70 + (totalCorrect / maxScore) * 60); // 70 à 130 base, on élargit un peu
      if (totalCorrect === maxScore) iq = 145;
      if (totalCorrect === 0) iq = 55;
      // Ajustement plus réaliste
      iq = Math.min(145, Math.max(55, Math.round(70 + (totalCorrect / maxScore) * 75)));
      return { totalCorrect, iq, maxScore };
    }

    function renderResults(container) {
      const { totalCorrect, iq, maxScore } = calculateIQ();
      let niveau = "";
      if (iq >= 130) niveau = "🌟 Très supérieur";
      else if (iq >= 120) niveau = "✨ Supérieur";
      else if (iq >= 110) niveau = "📘 Moyen fort";
      else if (iq >= 90) niveau = "📗 Moyen";
      else if (iq >= 80) niveau = "📙 Moyen faible";
      else niveau = "⚠️ Limite";

      container.innerHTML = `
        <div class="result-screen">
          <h2 style="color:#fadf9e; margin-bottom:1rem;">Profil WISC-V estimé</h2>
          <div class="iq-score">${iq}</div>
          <div class="remark">${niveau}</div>
          <p style="font-size:1.4rem; margin:1rem 0;">✅ ${totalCorrect} / ${maxScore} bonnes réponses</p>
          <hr>
          <p style="color:#ccc; margin-bottom:1.5rem;">Simulation basée sur 5 indices (MD, SIM, ARI, MAT, VOC).</p>
          <button class="btn" id="restartBtn" style="margin:0 auto;">🔄 Recommencer le test</button>
          <p class="small-note" style="margin-top:1.2rem;">Test complet 30 questions • WISC-V style</p>
        </div>
      `;
      document.getElementById('restartBtn')?.addEventListener('click', () => {
        // Reset complet
        currentSubtestIndex = 0;
        currentQuestionIndex = 0;
        userAnswers = Array(totalSubtests).fill().map(() => Array(questionsPerSubtest).fill(null));
        testFinished = false;
        renderUI();
      });
    }

    // Initialisation
    renderUI();
  })();
</script>
</body>
</html>
