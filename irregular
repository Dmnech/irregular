<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Dino Verbs - Irregular Verbs Test</title>
    <style>
        :root {
            --primary-color: #3498db;
            --secondary-color: #2ecc71;
            --accent-color: #9b59b6;
            --error-color: #e74c3c;
            --success-color: #27ae60;
            --text-color: #2c3e50;
            --light-text: #7f8c8d;
            --background: rgba(255,255,255,0.95);
            --shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', sans-serif;
            max-width: 100%;
            margin: 0;
            padding: 10px;
            color: var(--text-color);
            background-color: #f5f5f5;
            line-height: 1.5;
            touch-action: manipulation;
        }

        body::before {
            content: "";
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://assets.codepen.io/21542/codepen-dino-dance.gif') center/cover no-repeat;
            opacity: 0.05;
            z-index: -1;
            pointer-events: none;
        }

        h1 {
            text-align: center;
            color: var(--text-color);
            margin: 15px 0;
            font-size: 1.8rem;
        }

        .controls {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 15px;
            background-color: var(--background);
            padding: 15px;
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .control-group {
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .control-group-title {
            font-weight: bold;
            font-size: 0.9rem;
            color: var(--light-text);
            margin-bottom: 5px;
        }

        .mode-selector, .alphabet-filter, .direction-selector {
            display: flex;
            flex-wrap: wrap;
            gap: 6px;
            justify-content: center;
        }

        button, .alphabet-btn, .direction-btn {
            padding: 10px 12px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.2s;
            font-weight: 600;
            font-size: 0.9rem;
            flex: 1 1 auto;
            min-width: 0;
            text-align: center;
        }

        button {
            touch-action: manipulation;
        }

        .alphabet-btn {
            padding: 8px 0;
            background-color: var(--secondary-color);
            min-width: 30px;
            flex: 0 0 calc(11.1% - 6px);
            font-size: 0.8rem;
        }

        .direction-btn {
            background-color: var(--accent-color);
            flex: 1 1 45%;
        }

        button:active, .alphabet-btn:active, .direction-btn:active {
            transform: scale(0.98);
        }

        .alphabet-btn.active, .direction-btn.active {
            background-color: var(--error-color);
            transform: scale(1);
            box-shadow: 0 0 0 2px white, 0 0 0 4px var(--error-color);
        }

        .card {
            background-color: var(--background);
            padding: 20px;
            border-radius: 12px;
            box-shadow: var(--shadow);
            margin-bottom: 20px;
        }

        input, textarea {
            padding: 12px;
            margin: 8px 0;
            width: 100%;
            border: 2px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: border 0.2s;
            background-color: white;
        }

        input:focus, textarea:focus {
            border-color: var(--primary-color);
            outline: none;
        }

        .feedback {
            margin-top: 15px;
            font-weight: bold;
            font-size: 1rem;
            padding: 12px;
            border-radius: 8px;
            text-align: center;
        }

        .correct {
            color: var(--success-color);
            background-color: rgba(39, 174, 96, 0.1);
        }

        .incorrect {
            color: var(--error-color);
            background-color: rgba(231, 76, 60, 0.1);
        }

        .progress {
            margin-top: 20px;
            text-align: center;
            font-size: 1rem;
            font-weight: bold;
        }

        #currentVerb {
            min-height: 60px;
            margin-bottom: 15px;
            text-align: center;
        }

        #currentVerb h2 {
            color: var(--primary-color);
            font-size: 1.3rem;
            margin-bottom: 8px;
        }

        #currentVerb p {
            font-size: 1rem;
            color: var(--light-text);
        }

        .pagination {
            text-align: center;
            margin: 10px 0;
            font-weight: bold;
            font-size: 0.9rem;
            color: var(--light-text);
        }

        .dino-icon {
            display: inline-block;
            margin: 0 3px;
            font-size: 1.2rem;
        }

        .add-word-form {
            margin-top: 15px;
            padding: 15px;
            background-color: var(--background);
            border-radius: 12px;
            box-shadow: var(--shadow);
        }

        .add-word-form h3 {
            margin-top: 0;
            color: var(--text-color);
            font-size: 1.2rem;
        }

        .tab-buttons {
            display: flex;
            margin-bottom: 10px;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: var(--shadow);
        }

        .tab-button {
            flex: 1;
            padding: 12px;
            text-align: center;
            background-color: #e0e0e0;
            border: none;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.9rem;
        }

        .tab-button.active {
            background-color: var(--primary-color);
            color: white;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        @media (max-width: 480px) {
            h1 {
                font-size: 1.5rem;
                margin: 10px 0;
            }
            
            .controls {
                padding: 12px;
            }
            
            button, .direction-btn {
                padding: 10px 8px;
                font-size: 0.8rem;
            }
            
            .alphabet-btn {
                padding: 6px 0;
                min-width: 28px;
                font-size: 0.7rem;
                flex: 0 0 calc(11.1% - 4px);
            }
        }

        .scroll-top {
            position: fixed;
            bottom: 20px;
            right: 20px;
            width: 50px;
            height: 50px;
            background-color: var(--primary-color);
            color: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            box-shadow: 0 2px 15px rgba(0,0,0,0.2);
            z-index: 100;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.3s;
        }

        .scroll-top.visible {
            opacity: 1;
            pointer-events: auto;
        }
    </style>
</head>
<body>
    <h1>Dino Verbs <span class="dino-icon">🦖</span></h1>
    
    <div class="tab-buttons">
        <button class="tab-button active" onclick="openTab('practice')">Practice</button>
        <button class="tab-button" onclick="openTab('addWords')">Add Words</button>
        <button class="tab-button" onclick="openTab('mistakes')">Mistakes</button>
    </div>

    <div id="practice" class="tab-content active">
        <div class="controls">
            <div class="control-group">
                <div class="control-group-title">Practice Mode</div>
                <div class="mode-selector">
                    <button onclick="setMode('all')">All Forms</button>
                    <button onclick="setMode('translation')">Translation</button>
                    <button onclick="setMode('forms')">V2 + V3</button>
                </div>
            </div>
            
            <div class="control-group">
                <div class="control-group-title">Direction</div>
                <div class="direction-selector">
                    <div class="direction-btn active" id="dirEnRu" onclick="setDirection('en-ru')">EN → RU</div>
                    <div class="direction-btn" id="dirRuEn" onclick="setDirection('ru-en')">RU → EN</div>
                </div>
            </div>
            
            <div class="control-group">
                <div class="control-group-title">Filter by Letter</div>
                <div class="alphabet-filter" id="alphabetFilter"></div>
            </div>
        </div>
        
        <div class="pagination" id="pagination"></div>
        
        <div class="card">
            <div id="currentVerb"></div>
            <div id="inputFields"></div>
            <div style="display: flex; gap: 10px; margin-top: 15px;">
                <button onclick="checkAnswer()" style="flex: 2;">Check <span class="dino-icon">✓</span></button>
                <button onclick="nextVerb()" style="flex: 1;">Skip <span class="dino-icon">→</span></button>
            </div>
            <div id="feedback" class="feedback"></div>
            <div id="correctAnswer" class="feedback"></div>
        </div>
        
        <div class="progress">
            <p>Progress: <span id="score">0</span> / <span id="total">0</span> <span class="dino-icon">🏆</span></p>
        </div>
    </div>

    <div id="addWords" class="tab-content">
        <div class="add-word-form">
            <h3>Add New Verb</h3>
            <input type="text" id="newV1" placeholder="Base form (V1)" required>
            <input type="text" id="newV2" placeholder="Past Simple (V2)" required>
            <input type="text" id="newV3" placeholder="Past Participle (V3)" required>
            <input type="text" id="newTranslation" placeholder="Translation" required>
            <button onclick="addNewVerb()" style="margin-top: 10px;">Add Verb</button>
            <div id="addVerbFeedback" style="margin-top: 10px;"></div>
        </div>

        <div class="add-word-form" style="margin-top: 15px;">
            <h3>Import/Export Verbs</h3>
            <textarea id="importJson" rows="5" style="width: 100%; margin-bottom: 10px;" placeholder='Paste JSON array here'></textarea>
            <div style="display: flex; gap: 10px;">
                <button onclick="importVerbs()" style="flex: 1;">Import</button>
                <button onclick="exportVerbs()" style="flex: 1;">Export</button>
            </div>
            <div id="importExportFeedback" style="margin-top: 10px;"></div>
        </div>
    </div>

    <div id="mistakes" class="tab-content">
        <div class="card">
            <h2>Practice Mistakes</h2>
            <p>Here you can practice only the verbs you answered incorrectly.</p>
            
            <div id="mistakesList" style="margin: 15px 0;"></div>
            
            <div style="display: flex; gap: 10px;">
                <button onclick="startMistakesPractice()" id="startMistakesBtn" disabled style="flex: 2;">Start Practice</button>
                <button onclick="clearMistakes()" style="flex: 1;">Clear All</button>
            </div>
        </div>
    </div>

    <div class="scroll-top" onclick="window.scrollTo({top: 0, behavior: 'smooth'})">↑</div>

    <script>
        // Полный список из 120 неправильных глаголов
        let verbs = [
            { v1: 'arise', v2: 'arose', v3: 'arisen', translation: 'возникать' },
            { v1: 'awake', v2: 'awoke', v3: 'awoken', translation: 'просыпаться' },
            { v1: 'be', v2: 'was/were', v3: 'been', translation: 'быть' },
            { v1: 'bear', v2: 'bore', v3: 'borne', translation: 'нести' },
            { v1: 'beat', v2: 'beat', v3: 'beaten', translation: 'бить' },
            { v1: 'become', v2: 'became', v3: 'become', translation: 'становиться' },
            { v1: 'begin', v2: 'began', v3: 'begun', translation: 'начинать' },
            { v1: 'bet', v2: 'bet', v3: 'bet', translation: 'держать пари' },
            { v1: 'bind', v2: 'bound', v3: 'bound', translation: 'связывать' },
            { v1: 'bite', v2: 'bit', v3: 'bitten', translation: 'кусать' },
            { v1: 'bleed', v2: 'bled', v3: 'bled', translation: 'кровоточить' },
            { v1: 'blow', v2: 'blew', v3: 'blown', translation: 'дуть' },
            { v1: 'break', v2: 'broke', v3: 'broken', translation: 'ломать' },
            { v1: 'bring', v2: 'brought', v3: 'brought', translation: 'приносить' },
            { v1: 'build', v2: 'built', v3: 'built', translation: 'строить' },
            { v1: 'burn', v2: 'burnt', v3: 'burnt', translation: 'гореть' },
            { v1: 'burst', v2: 'burst', v3: 'burst', translation: 'лопаться' },
            { v1: 'buy', v2: 'bought', v3: 'bought', translation: 'покупать' },
            { v1: 'can', v2: 'could', v3: 'been able', translation: 'мочь' },
            { v1: 'catch', v2: 'caught', v3: 'caught', translation: 'ловить' },
            { v1: 'choose', v2: 'chose', v3: 'chosen', translation: 'выбирать' },
            { v1: 'come', v2: 'came', v3: 'come', translation: 'приходить' },
            { v1: 'cost', v2: 'cost', v3: 'cost', translation: 'стоить' },
            { v1: 'creep', v2: 'crept', v3: 'crept', translation: 'ползать' },
            { v1: 'cut', v2: 'cut', v3: 'cut', translation: 'резать' },
            { v1: 'deal', v2: 'dealt', v3: 'dealt', translation: 'иметь дело' },
            { v1: 'dig', v2: 'dug', v3: 'dug', translation: 'копать' },
            { v1: 'do', v2: 'did', v3: 'done', translation: 'делать' },
            { v1: 'draw', v2: 'drew', v3: 'drawn', translation: 'рисовать' },
            { v1: 'dream', v2: 'dreamt', v3: 'dreamt', translation: 'мечтать' },
            { v1: 'drink', v2: 'drank', v3: 'drunk', translation: 'пить' },
            { v1: 'drive', v2: 'drove', v3: 'driven', translation: 'водить' },
            { v1: 'eat', v2: 'ate', v3: 'eaten', translation: 'есть' },
            { v1: 'fall', v2: 'fell', v3: 'fallen', translation: 'падать' },
            { v1: 'feed', v2: 'fed', v3: 'fed', translation: 'кормить' },
            { v1: 'feel', v2: 'felt', v3: 'felt', translation: 'чувствовать' },
            { v1: 'fight', v2: 'fought', v3: 'fought', translation: 'бороться' },
            { v1: 'find', v2: 'found', v3: 'found', translation: 'находить' },
            { v1: 'fly', v2: 'flew', v3: 'flown', translation: 'летать' },
            { v1: 'forbid', v2: 'forbade', v3: 'forbidden', translation: 'запрещать' },
            { v1: 'forget', v2: 'forgot', v3: 'forgotten', translation: 'забывать' },
            { v1: 'forgive', v2: 'forgave', v3: 'forgiven', translation: 'прощать' },
            { v1: 'freeze', v2: 'froze', v3: 'frozen', translation: 'замерзать' },
            { v1: 'get', v2: 'got', v3: 'gotten', translation: 'получать' },
            { v1: 'give', v2: 'gave', v3: 'given', translation: 'давать' },
            { v1: 'go', v2: 'went', v3: 'gone', translation: 'идти' },
            { v1: 'grind', v2: 'ground', v3: 'ground', translation: 'молоть' },
            { v1: 'grow', v2: 'grew', v3: 'grown', translation: 'расти' },
            { v1: 'hang', v2: 'hung', v3: 'hung', translation: 'висеть' },
            { v1: 'have', v2: 'had', v3: 'had', translation: 'иметь' },
            { v1: 'hear', v2: 'heard', v3: 'heard', translation: 'слышать' },
            { v1: 'hide', v2: 'hid', v3: 'hidden', translation: 'прятать' },
            { v1: 'hit', v2: 'hit', v3: 'hit', translation: 'ударять' },
            { v1: 'hold', v2: 'held', v3: 'held', translation: 'держать' },
            { v1: 'hurt', v2: 'hurt', v3: 'hurt', translation: 'причинять боль' },
            { v1: 'keep', v2: 'kept', v3: 'kept', translation: 'хранить' },
            { v1: 'kneel', v2: 'knelt', v3: 'knelt', translation: 'становиться на колени' },
            { v1: 'know', v2: 'knew', v3: 'known', translation: 'знать' },
            { v1: 'lay', v2: 'laid', v3: 'laid', translation: 'класть' },
            { v1: 'lead', v2: 'led', v3: 'led', translation: 'вести' },
            { v1: 'lean', v2: 'leant', v3: 'leant', translation: 'наклоняться' },
            { v1: 'learn', v2: 'learnt', v3: 'learnt', translation: 'учить' },
            { v1: 'leave', v2: 'left', v3: 'left', translation: 'оставлять' },
            { v1: 'lend', v2: 'lent', v3: 'lent', translation: 'одалживать' },
            { v1: 'let', v2: 'let', v3: 'let', translation: 'позволять' },
            { v1: 'lie', v2: 'lay', v3: 'lain', translation: 'лежать' },
            { v1: 'light', v2: 'lit', v3: 'lit', translation: 'зажигать' },
            { v1: 'lose', v2: 'lost', v3: 'lost', translation: 'терять' },
            { v1: 'make', v2: 'made', v3: 'made', translation: 'делать' },
            { v1: 'may', v2: 'might', v3: 'might', translation: 'мочь' },
            { v1: 'mean', v2: 'meant', v3: 'meant', translation: 'значить' },
            { v1: 'meet', v2: 'met', v3: 'met', translation: 'встречать' },
            { v1: 'mow', v2: 'mowed', v3: 'mown', translation: 'косить' },
            { v1: 'must', v2: 'had to', v3: 'had to', translation: 'должен' },
            { v1: 'overtake', v2: 'overtook', v3: 'overtaken', translation: 'догонять' },
            { v1: 'pay', v2: 'paid', v3: 'paid', translation: 'платить' },
            { v1: 'put', v2: 'put', v3: 'put', translation: 'класть' },
            { v1: 'read', v2: 'read', v3: 'read', translation: 'читать' },
            { v1: 'ride', v2: 'rode', v3: 'ridden', translation: 'ехать верхом' },
            { v1: 'ring', v2: 'rang', v3: 'rung', translation: 'звонить' },
            { v1: 'rise', v2: 'rose', v3: 'risen', translation: 'подниматься' },
            { v1: 'run', v2: 'ran', v3: 'run', translation: 'бежать' },
            { v1: 'saw', v2: 'sawed', v3: 'sawn', translation: 'пилить' },
            { v1: 'say', v2: 'said', v3: 'said', translation: 'говорить' },
            { v1: 'see', v2: 'saw', v3: 'seen', translation: 'видеть' },
            { v1: 'seek', v2: 'sought', v3: 'sought', translation: 'искать' },
            { v1: 'sell', v2: 'sold', v3: 'sold', translation: 'продавать' },
            { v1: 'send', v2: 'sent', v3: 'sent', translation: 'отправлять' },
            { v1: 'set', v2: 'set', v3: 'set', translation: 'устанавливать' },
            { v1: 'sew', v2: 'sewed', v3: 'sewn', translation: 'шить' },
            { v1: 'shake', v2: 'shook', v3: 'shaken', translation: 'трясти' },
            { v1: 'shear', v2: 'sheared', v3: 'shorn', translation: 'стричь' },
            { v1: 'shed', v2: 'shed', v3: 'shed', translation: 'проливать' },
            { v1: 'shine', v2: 'shone', v3: 'shone', translation: 'светить' },
            { v1: 'shoot', v2: 'shot', v3: 'shot', translation: 'стрелять' },
            { v1: 'show', v2: 'showed', v3: 'shown', translation: 'показывать' },
            { v1: 'shrink', v2: 'shrank', v3: 'shrunk', translation: 'сжиматься' },
            { v1: 'shut', v2: 'shut', v3: 'shut', translation: 'закрывать' },
            { v1: 'sing', v2: 'sang', v3: 'sung', translation: 'петь' },
            { v1: 'sink', v2: 'sank', v3: 'sunk', translation: 'тонуть' },
            { v1: 'sit', v2: 'sat', v3: 'sat', translation: 'сидеть' },
            { v1: 'sleep', v2: 'slept', v3: 'slept', translation: 'спать' },
            { v1: 'slide', v2: 'slid', v3: 'slid', translation: 'скользить' },
            { v1: 'smell', v2: 'smelt', v3: 'smelt', translation: 'нюхать' },
            { v1: 'sow', v2: 'sowed', v3: 'sown', translation: 'сеять' },
            { v1: 'speak', v2: 'spoke', v3: 'spoken', translation: 'говорить' },
            { v1: 'spell', v2: 'spelt', v3: 'spelt', translation: 'произносить по буквам' },
            { v1: 'spend', v2: 'spent', v3: 'spent', translation: 'тратить' },
            { v1: 'spill', v2: 'spilt', v3: 'spilt', translation: 'проливать' },
            { v1: 'spin', v2: 'spun', v3: 'spun', translation: 'крутить' },
            { v1: 'spit', v2: 'spat', v3: 'spat', translation: 'плевать' },
            { v1: 'split', v2: 'split', v3: 'split', translation: 'раскалывать' },
            { v1: 'spoil', v2: 'spoilt', v3: 'spoilt', translation: 'портить' },
            { v1: 'spread', v2: 'spread', v3: 'spread', translation: 'распространять' },
            { v1: 'stand', v2: 'stood', v3: 'stood', translation: 'стоять' },
            { v1: 'steal', v2: 'stole', v3: 'stolen', translation: 'красть' },
            { v1: 'stick', v2: 'stuck', v3: 'stuck', translation: 'приклеивать' },
            { v1: 'sting', v2: 'stung', v3: 'stung', translation: 'жалить' },
            { v1: 'stink', v2: 'stank', v3: 'stunk', translation: 'вонять' },
            { v1: 'strike', v2: 'struck', v3: 'struck', translation: 'ударять' }
        ];

        let currentMode = 'all';
        let currentVerbIndex = 0;
        let score = 0;
        let shuffledVerbs = [];
        let currentLetterFilter = null;
        let currentDirection = 'en-ru';
        let mistakes = JSON.parse(localStorage.getItem('verbMistakes')) || [];
        let isMistakesMode = false;

        function createAlphabetFilter() {
            const alphabet = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('');
            const container = document.getElementById('alphabetFilter');
            container.innerHTML = '';
            
            const allBtn = document.createElement('div');
            allBtn.className = 'alphabet-btn active';
            allBtn.textContent = 'All';
            allBtn.onclick = () => setLetterFilter(null);
            container.appendChild(allBtn);
            
            alphabet.forEach(letter => {
                const btn = document.createElement('div');
                btn.className = 'alphabet-btn';
                btn.textContent = letter;
                btn.onclick = () => setLetterFilter(letter);
                container.appendChild(btn);
            });
        }

        function setDirection(direction) {
            currentDirection = direction;
            document.getElementById('dirEnRu').classList.toggle('active', direction === 'en-ru');
            document.getElementById('dirRuEn').classList.toggle('active', direction === 'ru-en');
            setMode(currentMode);
        }

        function setLetterFilter(letter) {
            document.querySelectorAll('.alphabet-btn').forEach(btn => {
                btn.classList.remove('active');
                if ((letter === null && btn.textContent === 'All') || 
                    (letter !== null && btn.textContent === letter)) {
                    btn.classList.add('active');
                }
            });
            currentLetterFilter = letter;
            setMode(currentMode);
        }

        function filterVerbsByLetter(verbsArray) {
            if (!currentLetterFilter) return verbsArray;
            return verbsArray.filter(verb => 
                verb.v1.charAt(0).toUpperCase() === currentLetterFilter
            );
        }

        function shuffleArray(array) {
            for (let i = array.length - 1; i > 0; i--) {
                const j = Math.floor(Math.random() * (i + 1));
                [array[i], array[j]] = [array[j], array[i]];
            }
            return array;
        }

        function setMode(mode) {
            currentMode = mode;
            isMistakesMode = false;
            
            let filteredVerbs = filterVerbsByLetter(verbs);
            shuffledVerbs = shuffleArray([...filteredVerbs]);
            currentVerbIndex = 0;
            score = 0;
            updateScore();
            showCurrentVerb();
        }

        function showCurrentVerb() {
            if (shuffledVerbs.length === 0) {
                document.getElementById('currentVerb').innerHTML = `
                    <h2>No verbs found</h2>
                    <p>No verbs starting with '${currentLetterFilter}'</p>
                `;
                document.getElementById('inputFields').innerHTML = '';
                document.getElementById('pagination').textContent = '';
                return;
            }

            const verb = shuffledVerbs[currentVerbIndex];
            const isReverse = currentDirection === 'ru-en';
            
            if (isReverse) {
                document.getElementById('currentVerb').innerHTML = `
                    <h2><span class="dino-icon">🦕</span> Translate to English:</h2>
                    <p>"${verb.translation}"</p>
                `;

                document.getElementById('inputFields').innerHTML = `
                    <p>English verb: <input type="text" id="v1" placeholder="Type the verb..."></p>
                `;
            } else {
                document.getElementById('currentVerb').innerHTML = `
                    <h2><span class="dino-icon">🦖</span> Verb: ${verb.v1}</h2>
                    ${currentMode === 'translation' ? `<p>Forms: ${verb.v2}, ${verb.v3}</p>` : ''}
                    ${currentMode === 'forms' ? `<p>Translation: ${verb.translation}</p>` : ''}
                `;

                document.getElementById('inputFields').innerHTML = `
                    ${currentMode !== 'forms' ? `<p>Translation: <input type="text" id="translation" placeholder="Type translation..."></p>` : ''}
                    ${currentMode !== 'translation' ? `<p>Past Simple (V2): <input type="text" id="v2" placeholder="Type V2 form..."></p>` : ''}
                    ${currentMode !== 'translation' ? `<p>Past Participle (V3): <input type="text" id="v3" placeholder="Type V3 form..."></p>` : ''}
                `;
            }

            document.getElementById('feedback').innerHTML = '';
            document.getElementById('correctAnswer').innerHTML = '';
            document.getElementById('pagination').textContent = isMistakesMode 
                ? `Mistake ${currentVerbIndex + 1} of ${shuffledVerbs.length}` 
                : `Verb ${currentVerbIndex + 1} of ${shuffledVerbs.length}`;
            
            const firstInput = document.querySelector('input');
            if (firstInput) firstInput.focus();
        }

        function checkAnswer() {
            const verb = shuffledVerbs[currentVerbIndex];
            const feedbackElement = document.getElementById('feedback');
            const correctAnswerElement = document.getElementById('correctAnswer');
            let isCorrect = true;
            let correctAnswers = [];
            const isReverse = currentDirection === 'ru-en';

            function normalizeAnswer(answer) {
                return answer.trim().toLowerCase().replace(/\/.*$/, '');
            }

            if (isReverse) {
                const v1Input = normalizeAnswer(document.getElementById('v1').value);
                if (v1Input !== normalizeAnswer(verb.v1)) {
                    isCorrect = false;
                    correctAnswers.push(`Correct: ${verb.v1}`);
                }
            } else {
                if (currentMode !== 'forms') {
                    const translationInput = normalizeAnswer(document.getElementById('translation').value);
                    if (translationInput !== normalizeAnswer(verb.translation)) {
                        isCorrect = false;
                        correctAnswers.push(`Translation: ${verb.translation}`);
                    }
                }
                
                if (currentMode !== 'translation') {
                    const v2Input = normalizeAnswer(document.getElementById('v2').value);
                    const v3Input = normalizeAnswer(document.getElementById('v3').value);
                    
                    if (v2Input !== normalizeAnswer(verb.v2)) {
                        isCorrect = false;
                        correctAnswers.push(`V2: ${verb.v2}`);
                    }
                    if (v3Input !== normalizeAnswer(verb.v3)) {
                        isCorrect = false;
                        correctAnswers.push(`V3: ${verb.v3}`);
                    }
                }
            }

            if (isCorrect) {
                feedbackElement.textContent = 'Correct! 🎉';
                feedbackElement.className = 'feedback correct';
                score++;
                updateScore();
                
                if (isMistakesMode) {
                    mistakes = mistakes.filter(m => m.v1 !== verb.v1);
                    localStorage.setItem('verbMistakes', JSON.stringify(mistakes));
                    updateMistakesList();
                }
                
                setTimeout(nextVerb, 800);
            } else {
                feedbackElement.textContent = 'Incorrect! 😢';
                feedbackElement.className = 'feedback incorrect';
                correctAnswerElement.innerHTML = correctAnswers.join('<br>');
                
                if (!mistakes.some(m => m.v1 === verb.v1)) {
                    mistakes.push(verb);
                    localStorage.setItem('verbMistakes', JSON.stringify(mistakes));
                    updateMistakesList();
                }
            }
        }

        function nextVerb() {
            currentVerbIndex++;
            if (currentVerbIndex >= shuffledVerbs.length) {
                currentVerbIndex = 0;
                const message = isMistakesMode 
                    ? `🦖 Rawr! You finished all ${shuffledVerbs.length} mistake verbs! Score: ${score}/${shuffledVerbs.length}`
                    : `🦖 Rawr! You finished all ${shuffledVerbs.length} verbs! Score: ${score}/${shuffledVerbs.length}`;
                
                alert(message);
                
                if (isMistakesMode) {
                    startMistakesPractice();
                } else {
                    setMode(currentMode);
                }
            } else {
                showCurrentVerb();
            }
        }

        function updateScore() {
            document.getElementById('score').textContent = score;
            document.getElementById('total').textContent = shuffledVerbs.length;
        }

        function addNewVerb() {
            const v1 = document.getElementById('newV1').value.trim();
            const v2 = document.getElementById('newV2').value.trim();
            const v3 = document.getElementById('newV3').value.trim();
            const translation = document.getElementById('newTranslation').value.trim();
            
            if (!v1 || !v2 || !v3 || !translation) {
                document.getElementById('addVerbFeedback').textContent = 'Please fill all fields!';
                document.getElementById('addVerbFeedback').style.color = 'red';
                return;
            }
            
            if (verbs.some(verb => verb.v1.toLowerCase() === v1.toLowerCase())) {
                document.getElementById('addVerbFeedback').textContent = 'This verb already exists!';
                document.getElementById('addVerbFeedback').style.color = 'red';
                return;
            }
            
            const newVerb = { v1, v2, v3, translation };
            verbs.push(newVerb);
            
            // Save user verbs to localStorage
            const userVerbs = JSON.parse(localStorage.getItem('userVerbs')) || [];
            userVerbs.push(newVerb);
            localStorage.setItem('userVerbs', JSON.stringify(userVerbs));
            
            document.getElementById('newV1').value = '';
            document.getElementById('newV2').value = '';
            document.getElementById('newV3').value = '';
            document.getElementById('newTranslation').value = '';
            
            document.getElementById('addVerbFeedback').textContent = 'Verb added successfully!';
            document.getElementById('addVerbFeedback').style.color = 'green';
            
            if (currentLetterFilter && v1.charAt(0).toUpperCase() === currentLetterFilter) {
                setMode(currentMode);
            }
        }

        function importVerbs() {
            const jsonInput = document.getElementById('importJson').value.trim();
            
            try {
                const newVerbs = JSON.parse(jsonInput);
                if (!Array.isArray(newVerbs)) {
                    throw new Error('Input should be a JSON array');
                }
                
                let addedCount = 0;
                const userVerbs = JSON.parse(localStorage.getItem('userVerbs')) || [];
                
                newVerbs.forEach(verb => {
                    if (verb.v1 && verb.v2 && verb.v3 && verb.translation) {
                        if (!verbs.some(v => v.v1.toLowerCase() === verb.v1.toLowerCase())) {
                            verbs.push(verb);
                            userVerbs.push(verb);
                            addedCount++;
                        }
                    }
                });
                
                localStorage.setItem('userVerbs', JSON.stringify(userVerbs));
                document.getElementById('importExportFeedback').textContent = 
                    `Successfully added ${addedCount} new verbs!`;
                document.getElementById('importExportFeedback').style.color = 'green';
                
                setMode(currentMode);
            } catch (e) {
                document.getElementById('importExportFeedback').textContent = 
                    'Error: Invalid JSON format or structure. Please check your input.';
                document.getElementById('importExportFeedback').style.color = 'red';
                console.error(e);
            }
        }

        function exportVerbs() {
            const jsonStr = JSON.stringify(verbs, null, 2);
            document.getElementById('importJson').value = jsonStr;
            document.getElementById('importExportFeedback').textContent = 
                'Verbs copied to the import field. You can now copy them.';
            document.getElementById('importExportFeedback').style.color = 'green';
        }

        function updateMistakesList() {
            const mistakesList = document.getElementById('mistakesList');
            mistakesList.innerHTML = '';
            
            if (mistakes.length === 0) {
                mistakesList.innerHTML = '<p>No mistakes yet! Keep practicing!</p>';
                document.getElementById('startMistakesBtn').disabled = true;
                return;
            }
            
            document.getElementById('startMistakesBtn').disabled = false;
            
            const list = document.createElement('ul');
            mistakes.forEach((verb, index) => {
                const item = document.createElement('li');
                item.innerHTML = `<strong>${verb.v1}</strong>: ${verb.v2}, ${verb.v3} - ${verb.translation}`;
                list.appendChild(item);
            });
            
            mistakesList.appendChild(list);
        }

        function startMistakesPractice() {
            if (mistakes.length === 0) {
                alert('No mistakes to practice!');
                return;
            }
            
            isMistakesMode = true;
            shuffledVerbs = shuffleArray([...mistakes]);
            currentVerbIndex = 0;
            score = 0;
            updateScore();
            showCurrentVerb();
            
            openTab('practice');
        }

        function clearMistakes() {
            if (confirm('Are you sure you want to clear all mistakes?')) {
                mistakes = [];
                localStorage.setItem('verbMistakes', JSON.stringify(mistakes));
                updateMistakesList();
            }
        }

        function openTab(tabName) {
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            document.getElementById(tabName).classList.add('active');
            
            document.querySelectorAll('.tab-button').forEach(btn => {
                btn.classList.remove('active');
                if (btn.textContent.toLowerCase().includes(tabName)) {
                    btn.classList.add('active');
                }
            });
            
            if (tabName === 'mistakes') {
                updateMistakesList();
            }
        }

        function initApp() {
            createAlphabetFilter();
            setMode('all');
            updateMistakesList();
            
            const savedVerbs = localStorage.getItem('userVerbs');
            if (savedVerbs) {
                try {
                    const userVerbs = JSON.parse(savedVerbs);
                    verbs = [...verbs, ...userVerbs];
                } catch (e) {
                    console.error('Error loading user verbs:', e);
                }
            }
            
            window.addEventListener('scroll', function() {
                const scrollTopBtn = document.querySelector('.scroll-top');
                if (window.pageYOffset > 300) {
                    scrollTopBtn.classList.add('visible');
                } else {
                    scrollTopBtn.classList.remove('visible');
                }
            });
            
            document.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    checkAnswer();
                }
            });
            
            if (/iPad|iPhone|iPod/.test(navigator.userAgent)) {
                document.body.classList.add('ios');
            }
        }

        document.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>
