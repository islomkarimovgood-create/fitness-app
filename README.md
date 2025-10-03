<!DOCTYPE html>
<html>
<head>
    <title>FitGenius Pro - 30-дневная трансформация</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;700;800&family=Roboto:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            --primary: #4ECDC4;
            --secondary: #FF6B6B;
            --background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            --card-bg: rgba(255,255,255,0.12);
            --text: white;
        }
        
        .dark-theme {
            --background: linear-gradient(135deg, #2c3e50 0%, #3498db 100%);
            --card-bg: rgba(255,255,255,0.08);
        }
        
        body {
            font-family: 'Roboto', sans-serif;
            background: var(--background);
            color: var(--text);
            min-height: 100vh;
            background-attachment: fixed;
            transition: all 0.3s ease;
        }
        
        .theme-toggle {
            position: fixed;
            top: 90px;
            right: 20px;
            background: var(--card-bg);
            border: none;
            color: var(--text);
            padding: 10px;
            border-radius: 50%;
            cursor: pointer;
            z-index: 1000;
            backdrop-filter: blur(10px);
        }
        
        .navbar {
            background: rgba(0,0,0,0.95);
            padding: 18px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            backdrop-filter: blur(10px);
            border-bottom: 2px solid var(--primary);
        }
        
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 25px;
        }
        
        .logo {
            font-family: 'Montserrat', sans-serif;
            font-size: 28px;
            font-weight: 800;
            background: linear-gradient(45deg, var(--secondary), var(--primary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        
        .container {
            max-width: 1200px;
            margin: 90px auto 0;
            padding: 40px 25px;
            min-height: calc(100vh - 90px);
        }

        /* Таймер для упражнений */
        .timer-container {
            background: var(--card-bg);
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
        }
        
        .timer {
            font-size: 48px;
            font-weight: bold;
            font-family: 'Montserrat', sans-serif;
            margin: 20px 0;
        }
        
        .timer-btn {
            background: var(--primary);
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            margin: 5px;
            cursor: pointer;
            font-family: 'Montserrat', sans-serif;
        }

        /* Прогресс фотографии */
        .photo-progress {
            background: var(--card-bg);
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        
        .photo-upload {
            border: 2px dashed var(--primary);
            padding: 40px;
            text-align: center;
            border-radius: 10px;
            margin: 10px 0;
            cursor: pointer;
        }
        
        .photo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 10px;
            margin-top: 20px;
        }
        
        .photo-item {
            width: 100%;
            height: 150px;
            object-fit: cover;
            border-radius: 10px;
        }

        /* Мотивационные уведомления */
        .motivation-card {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
            text-align: center;
            animation: pulse 2s infinite;
        }

        /* Водный режим */
        .water-tracker {
            background: var(--card-bg);
            padding: 20px;
            border-radius: 15px;
            margin: 20px 0;
        }
        
        .water-cups {
            display: flex;
            justify-content: center;
            gap: 10px;
            margin: 20px 0;
        }
        
        .water-cup {
            width: 40px;
            height: 60px;
            background: rgba(255,255,255,0.2);
            border-radius: 0 0 10px 10px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        
        .water-cup.filled {
            background: #3498db;
        }

        /* Остальные стили остаются как были */
        .feature-card {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 15px;
            margin: 20px 0;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255,255,255,0.1);
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.05); }
            100% { transform: scale(1); }
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .container {
                padding: 20px 15px;
                margin-top: 80px;
            }
            
            .theme-toggle {
                top: 80px;
                right: 15px;
            }
        }
    </style>
</head>
<body>
    <button class="theme-toggle" onclick="toggleTheme()">🌙</button>

    <nav class="navbar">
        <div class="nav-container">
            <div class="logo">🏋️ FitGenius Pro</div>
            <div class="nav-links">
                <a href="#" onclick="showPage('home')">Главная</a>
                <a href="#" onclick="showPage('program')">Тренировки</a>
                <a href="#" onclick="showPage('nutrition')">Питание</a>
                <a href="#" onclick="showPage('progress')">Прогресс</a>
                <a href="#" onclick="showPage('community')">Сообщество</a>
            </div>
        </div>
    </nav>

    <div class="container">
        <!-- Главная страница -->
        <div id="home" class="page active">
            <div class="hero">
                <h1>30-дневная трансформация</h1>
                <p>Новые функции: таймеры, прогресс фото, водный режим!</p>
                <button class="cta-button" onclick="showPage('program')">Начать трансформацию</button>
            </div>

            <div class="motivation-card">
                <h3>💪 Ты сможешь!</h3>
                <p>Сегодняшняя тренировка изменит твое завтра</p>
            </div>

            <div class="stats">
                <div class="stat-card">
                    <div class="stat-number" id="totalWorkouts">0</div>
                    <div class="stat-label">Завершено тренировок</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="waterCount">0/8</div>
                    <div class="stat-label">Стаканов воды</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number" id="currentStreak">0</div>
                    <div class="stat-label">Дней подряд</div>
                </div>
            </div>
        </div>

        <!-- Тренировки с таймером -->
        <div id="program" class="page">
            <h1>💪 Тренировки + Таймер</h1>
            
            <div class="timer-container">
                <h3>⏱️ Таймер упражнений</h3>
                <div class="timer" id="exerciseTimer">00:30</div>
                <button class="timer-btn" onclick="startTimer()">Старт</button>
                <button class="timer-btn" onclick="pauseTimer()">Пауза</button>
                <button class="timer-btn" onclick="resetTimer()">Сброс</button>
            </div>

            <!-- Остальной код тренировок -->
        </div>

        <!-- Новый раздел - Сообщество -->
        <div id="community" class="page">
            <h1>👥 Фитнес Сообщество</h1>
            
            <div class="feature-card">
                <h3>📸 Мой прогресс в фото</h3>
                <div class="photo-upload" onclick="document.getElementById('photoInput').click()">
                    <p>📷 Нажми чтобы добавить фото прогресса</p>
                    <input type="file" id="photoInput" accept="image/*" style="display:none" onchange="handlePhotoUpload(event)">
                </div>
                <div class="photo-grid" id="photoGrid"></div>
            </div>

            <div class="water-tracker">
                <h3>💧 Водный режим</h3>
                <p>Выпито стаканов: <span id="waterDisplay">0</span>/8</p>
                <div class="water-cups" id="waterCups"></div>
                <button class="cta-button" onclick="resetWater()">Сбросить на день</button>
            </div>

            <div class="feature-card">
                <h3>🏆 Достижения</h3>
                <div id="achievementsList"></div>
            </div>
        </div>

        <!-- Остальные страницы (Питание, Прогресс) -->
    </div>

    <script>
        // Новые функции
        let isDarkTheme = false;
        let timerInterval;
        let timerSeconds = 30;
        let waterCount = 0;
        let achievements = JSON.parse(localStorage.getItem('achievements')) || [];

        // Переключение темы
        function toggleTheme() {
            isDarkTheme = !isDarkTheme;
            document.body.classList.toggle('dark-theme');
            document.querySelector('.theme-toggle').textContent = isDarkTheme ? '☀️' : '🌙';
        }

        // Таймер упражнений
        function startTimer() {
            clearInterval(timerInterval);
            timerInterval = setInterval(() => {
                timerSeconds--;
                updateTimerDisplay();
                if (timerSeconds <= 0) {
                    clearInterval(timerInterval);
                    alert('⏰ Время вышло! Отличная работа!');
                }
            }, 1000);
        }

        function pauseTimer() {
            clearInterval(timerInterval);
        }

        function resetTimer() {
            clearInterval(timerInterval);
            timerSeconds = 30;
            updateTimerDisplay();
        }

        function updateTimerDisplay() {
            const minutes = Math.floor(timerSeconds / 60);
            const seconds = timerSeconds % 60;
            document.getElementById('exerciseTimer').textContent = 
                `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
        }

        // Водный режим
        function initWaterTracker() {
            const waterCups = document.getElementById('waterCups');
            waterCups.innerHTML = '';
            waterCount = parseInt(localStorage.getItem('waterCount')) || 0;
            
            for (let i = 0; i < 8; i++) {
                const cup = document.createElement('div');
                cup.className = `water-cup ${i < waterCount ? 'filled' : ''}`;
                cup.onclick = () => drinkWater(i);
                waterCups.appendChild(cup);
            }
            updateWaterDisplay();
        }

        function drinkWater(cupIndex) {
            if (cupIndex === waterCount) {
                waterCount++;
                localStorage.setItem('waterCount', waterCount);
                initWaterTracker();
                
                if (waterCount === 8) {
                    unlockAchievement('waterMaster');
                }
            }
        }

        function resetWater() {
            waterCount = 0;
            localStorage.setItem('waterCount', waterCount);
            initWaterTracker();
        }

        function updateWaterDisplay() {
            document.getElementById('waterDisplay').textContent = waterCount;
            document.getElementById('waterCount').textContent = `${waterCount}/8`;
        }

        // Система достижений
        function unlockAchievement(achievementId) {
            const achievement = {
                id: achievementId,
                date: new Date().toISOString(),
                unlocked: true
            };
            
            if (!achievements.find(a => a.id === achievementId)) {
                achievements.push(achievement);
                localStorage.setItem('achievements', JSON.stringify(achievements));
                showAchievementNotification(achievementId);
            }
        }

        function showAchievementNotification(achievementId) {
            const messages = {
                waterMaster: '💧 Достижение: Водный мастер!',
                weekComplete: '🏆 Неделя завершена!',
                monthComplete: '🎉 Месяц завершен!'
            };
            
            alert(messages[achievementId] || '🎊 Новое достижение!');
        }

        // Загрузка фото
        function handlePhotoUpload(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    const photos = JSON.parse(localStorage.getItem('progressPhotos')) || [];
                    photos.push({
                        url: e.target.result,
                        date: new Date().toISOString(),
                        day: currentDay
                    });
                    localStorage.setItem('progressPhotos', JSON.stringify(photos));
                    loadProgressPhotos();
                };
                reader.readAsDataURL(file);
            }
        }

        function loadProgressPhotos() {
            const photos = JSON.parse(localStorage.getItem('progressPhotos')) || [];
            const grid = document.getElementById('photoGrid');
            grid.innerHTML = '';
            
            photos.forEach(photo => {
                const img = document.createElement('img');
                img.src = photo.url;
                img.className = 'photo-item';
                grid.appendChild(img);
            });
        }

        // Инициализация при загрузке
        function initNewFeatures() {
            initWaterTracker();
            loadProgressPhotos();
            updateTimerDisplay();
        }

        // Добавь этот вызов в существующую функцию init()
        document.addEventListener('DOMContentLoaded', function() {
            init(); // твоя существующая функция
            initNewFeatures(); // новые функции
        });
    </script>

    <!-- Существующий JavaScript код остаётся здесь -->
</body>
</html>
