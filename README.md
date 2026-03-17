<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Матриця Долі | Аліна Таро Фадєєва</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', 'Arial', sans-serif;
        }
        
        body {
            background: linear-gradient(145deg, #1e1029 0%, #3d1f4a 100%);
            min-height: 100vh;
            display: flex;
            justify-content: center;
            padding: 15px;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(255, 248, 250, 0.97);
            border-radius: 40px;
            padding: 30px 20px;
            margin: 20px 0;
            box-shadow: 0 30px 60px rgba(0,0,0,0.6);
            border: 2px solid #dab0ff;
        }
        
        .header {
            text-align: center;
            margin-bottom: 25px;
            border-bottom: 3px solid #b692e0;
            padding-bottom: 20px;
        }
        
        .header h1 {
            font-size: 32px;
            background: linear-gradient(45deg, #5a2d7a, #b24592);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            font-weight: 800;
        }
        
        .header p {
            color: #5a3c72;
            font-size: 18px;
            font-weight: 600;
            margin-top: 5px;
        }
        
        .input-block {
            background: #f0e2ff;
            border-radius: 80px;
            padding: 18px 25px;
            margin-bottom: 30px;
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            align-items: center;
            border: 2px solid white;
        }
        
        .input-block label {
            font-size: 18px;
            font-weight: 700;
            color: #3a2450;
        }
        
        .input-block input {
            flex: 1;
            min-width: 250px;
            padding: 16px 25px;
            border: 3px solid #c59bff;
            border-radius: 60px;
            font-size: 16px;
            background: white;
        }
        
        .calc-button {
            background: linear-gradient(145deg, #7e4fa5, #b23b8d);
            color: white;
            border: none;
            padding: 16px 35px;
            border-radius: 60px;
            font-size: 18px;
            font-weight: 700;
            cursor: pointer;
            box-shadow: 0 8px 16px rgba(120, 60, 140, 0.5);
            width: 100%;
        }
        
        .result-title {
            font-size: 24px;
            font-weight: 800;
            color: #341f44;
            text-align: center;
            margin: 25px 0 15px;
            background: #e7d1ff;
            padding: 12px;
            border-radius: 40px;
        }
        
        .points-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
            gap: 12px;
            margin-bottom: 30px;
        }
        
        .point-card {
            background: white;
            border-radius: 30px;
            padding: 14px 10px;
            border: 2px solid #e4ccff;
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
            transition: 0.2s;
        }
        
        .point-card:hover {
            border-color: #b24592;
            background: #fcf3ff;
        }
        
        .point-name {
            font-size: 14px;
            font-weight: 600;
            color: #7b58a6;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 5px;
        }
        
        .point-value {
            font-size: 32px;
            font-weight: 800;
            background: linear-gradient(145deg, #3d2560, #b53b96);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            line-height: 1.2;
        }
        
        .footer-brand {
            background: #e7d1ff;
            border-radius: 60px;
            padding: 20px;
            text-align: center;
            margin: 25px 0;
            font-size: 18px;
            font-weight: 600;
            border: 3px dashed #a07ac2;
        }
        
        .footer-brand a {
            color: #aa3380;
            text-decoration: none;
            font-weight: 800;
            border-bottom: 2px solid;
        }
        
        .download-btn {
            background: white;
            border: 4px solid #9b66b9;
            color: #4a2a6b;
            padding: 18px 30px;
            border-radius: 60px;
            font-size: 20px;
            font-weight: 700;
            cursor: pointer;
            width: 100%;
            margin: 10px 0;
            transition: 0.2s;
        }
        
        .download-btn:hover {
            background: #f0e0ff;
            border-color: #b24592;
        }
        
        .watermark {
            font-size: 13px;
            color: #8f79b0;
            text-align: center;
            margin-top: 20px;
            font-weight: 500;
        }
    </style>
</head>
<body>
    <div class="container" id="matrixContainer">
        <div class="header">
            <h1>🔮 ПОВНА МАТРИЦЯ ДОЛІ</h1>
            <p>розрахунок 37 точок | АЛІНА ТАРО ФАДЄЄВА</p>
        </div>
        
        <div class="input-block">
            <label>📅 Ваша дата народження:</label>
            <input type="date" id="birthDate" value="1990-01-01">
        </div>
        
        <button class="calc-button" id="calcBtn">✨ РОЗРАХУВАТИ ВСІ ТОЧКИ ✨</button>
        
        <div id="resultArea" style="display: none;">
            <div class="result-title">📋 ВАШІ 37 ЕНЕРГІЙ</div>
            
            <div class="points-grid" id="pointsList">
                <!-- результати будуть тут -->
            </div>
            
            <div class="footer-brand">
                🌸 ДЕТАЛЬНЕ РОЗШИФРУВАННЯ КОЖНОЇ ТОЧКИ — НА КОНСУЛЬТАЦІЇ 🌸<br>
                <a href="#">📲 @alina_taro_fadeeva</a>
            </div>
            
            <button class="download-btn" id="downloadBtn">
                ⬇️ ЗАВАНТАЖИТИ МІЙ РЕЗУЛЬТАТ
            </button>
            <div class="watermark">© Аліна Таро Фадєєва | матрицядолі.аліна.укр</div>
        </div>
    </div>
    
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2canvas/1.4.1/html2canvas.min.js"></script>
    <script>
        (function() {
            // Функція зведення до числа 1-22
            function toArcan(num) {
                if (num <= 22 && num > 0) return num;
                if (num === 0) return 22;
                
                let sum = 0;
                let numStr = Math.abs(num).toString();
                for (let i = 0; i < numStr.length; i++) {
                    sum += parseInt(numStr[i]);
                }
                
                if (sum > 22) {
                    return toArcan(sum);
                }
                return sum === 0 ? 22 : sum;
            }

            // ГОЛОВНА ФУНКЦІЯ РОЗРАХУНКУ (37 точок за вашими формулами)
            function calculateAllPoints(dateString) {
                const parts = dateString.split('-');
                if (parts.length !== 3) return null;
                
                const year = parseInt(parts[0]);
                const month = parseInt(parts[1]);
                const day = parseInt(parts[2]);
                
                // День, місяць, рік (базові)
                let a = day > 22 ? toArcan(day) : day;          // ЗОНА РЕСУРСА
                let b = month;                                   // ГЛАВНЫЙ ТАЛАНТ (місяць до 12)
                let yearSum = 0;
                for (let char of year.toString()) yearSum += parseInt(char);
                let c = toArcan(yearSum);                        // ЗАДАЧА ДУШИ
                
                // Основні розрахунки
                let d = toArcan(a + b + c);                      // ГЛАВНАЯ ПРОРАБОТКА
                let e = toArcan(a + b + c + d);                  // ЗОНА КОМФОРТА ДУШИ
                
                // РОДОВЫЕ ПРОГРАММЫ ПО МУЖСКОМУ РОДУ
                let f = toArcan(a + b);                           // f
                let y = toArcan(c + d);                           // y
                let o = toArcan(f + y);                           // o
                
                // РОДОВЫЕ ПРОГРАММЫ ПО ЖЕНСКОМУ РОДУ
                let g = toArcan(b + c);                           // g
                let k = toArcan(a + d);                           // k
                let u = toArcan(g + k);                           // u
                
                // ЗОНА РОДИТЕЛЬСКО-ДЕТСКИХ ОТНОШЕНИЙ
                let a1 = toArcan(a + e);                          // a1
                let a2 = toArcan(a + a1);                         // a2
                
                // КАРМИЧЕСКИЙ ХВОСТ
                let d1 = toArcan(d + e);                          // d1
                let d2 = toArcan(d + d1);                         // d2
                
                // ЛИНИЯ БЛАГОПОЛУЧИЯ
                let c1 = toArcan(c + e);                          // c1
                let x = toArcan(d1 + c1);                         // x
                let x1 = toArcan(d1 + x);                         // x1
                let c2 = toArcan(c + c1);                         // c2
                let x2 = toArcan(x + c1);                         // x2
                
                // ПРОГРАММА СЕКСУАЛЬНОСТИ
                let e1 = toArcan(f + g + y + k);                  // e1
                let e2 = toArcan(e + e1);                         // e2
                
                // ДОПОЛНИТЕЛЬНЫЕ ТОЧКИ РОДОВЫХ ЛИНИЙ
                let s1 = toArcan(e1 + f);                         // s1
                let s2 = toArcan(f + s1);                         // s2
                let s4 = toArcan(y + e1);                         // s4
                let s3 = toArcan(y + s4);                         // s3
                let p1 = toArcan(g + e1);                         // p1
                let p2 = toArcan(g + p1);                         // p2
                let p3 = toArcan(k + e1);                         // p3
                let p4 = toArcan(k + p3);                         // p4
                
                // ТАЛАНТЫ ОТ БОГА
                let b1 = toArcan(b + e);                          // b1
                let b2 = toArcan(b + b1);                         // b2
                
                // ПРЕДНАЗНАЧЕНИЕ 20-40 ЛЕТ
                let h = toArcan(b + d);                            // h
                let j = toArcan(a + c);                            // j
                let m = toArcan(h + j);                            // m
                
                // ПРЕДНАЗНАЧЕНИЕ 40-60 ЛЕТ
                let n = toArcan(f + y);                            // n
                let t = toArcan(g + k);                            // t
                let z = toArcan(n + t);                            // z
                
                // ПРЕДНАЗНАЧЕНИЕ ПОСЛЕ 60 ЛЕТ
                let s = toArcan(m + z);                            // s
                
                // Повертаємо ВСІ точки з назвами
                return [
                    { name: "🌸 ЗОНА РЕСУРСА (а)", value: a },
                    { name: "🌟 ГОЛОВНИЙ ТАЛАНТ (b)", value: b },
                    { name: "📿 ЗАВДАННЯ ДУШІ (c)", value: c },
                    { name: "⚡ ГОЛОВНЕ ПРОРОБЛЕННЯ (d)", value: d },
                    { name: "🕊️ ЗОНА КОМФОРТУ ДУШІ (e)", value: e },
                    { name: "👨‍👩‍👦 РОДОВІ ЧОЛОВІЧІ (f)", value: f },
                    { name: "👩‍👧‍👦 РОДОВІ ЧОЛОВІЧІ (y)", value: y },
                    { name: "👑 РОДОВІ ЧОЛОВІЧІ (o)", value: o },
                    { name: "👭 РОДОВІ ЖІНОЧІ (g)", value: g },
                    { name: "👯‍♀️ РОДОВІ ЖІНОЧІ (k)", value: k },
                    { name: "💞 РОДОВІ ЖІНОЧІ (u)", value: u },
                    { name: "👪 БАТЬКИ-ДІТИ (a1)", value: a1 },
                    { name: "👨‍👩‍👧 БАТЬКИ-ДІТИ (a2)", value: a2 },
                    { name: "🌀 КАРМІЧНИЙ ХВІСТ (d1)", value: d1 },
                    { name: "♻️ КАРМІЧНИЙ ХВІСТ (d2)", value: d2 },
                    { name: "💫 ЛІНІЯ БЛАГОПОЛУЧЧЯ (c1)", value: c1 },
                    { name: "💎 ЛІНІЯ БЛАГОПОЛУЧЧЯ (x)", value: x },
                    { name: "✨ ЛІНІЯ БЛАГОПОЛУЧЧЯ (x1)", value: x1 },
                    { name: "🌟 ЛІНІЯ БЛАГОПОЛУЧЧЯ (c2)", value: c2 },
                    { name: "⚜️ ЛІНІЯ БЛАГОПОЛУЧЧЯ (x2)", value: x2 },
                    { name: "🔥 СЕКСУАЛЬНІСТЬ (e1)", value: e1 },
                    { name: "💋 СЕКСУАЛЬНІСТЬ (e2)", value: e2 },
                    { name: "🔹 ДОД. РОДОВІ (s1)", value: s1 },
                    { name: "🔸 ДОД. РОДОВІ (s2)", value: s2 },
                    { name: "🔺 ДОД. РОДОВІ (s4)", value: s4 },
                    { name: "🔻 ДОД. РОДОВІ (s3)", value: s3 },
                    { name: "🟣 ДОД. РОДОВІ (p1)", value: p1 },
                    { name: "🟢 ДОД. РОДОВІ (p2)", value: p2 },
                    { name: "🟡 ДОД. РОДОВІ (p3)", value: p3 },
                    { name: "🟠 ДОД. РОДОВІ (p4)", value: p4 },
                    { name: "🎨 ТАЛАНТИ ВІД БОГА (b1)", value: b1 },
                    { name: "🌈 ТАЛАНТИ ВІД БОГА (b2)", value: b2 },
                    { name: "📌 ПРИЗНАЧЕННЯ 20-40 (h)", value: h },
                    { name: "📍 ПРИЗНАЧЕННЯ 20-40 (j)", value: j },
                    { name: "🎯 ПРИЗНАЧЕННЯ 20-40 (m)", value: m },
                    { name: "🎲 ПРИЗНАЧЕННЯ 40-60 (n)", value: n },
                    { name: "🎰 ПРИЗНАЧЕННЯ 40-60 (t)", value: t },
                    { name: "🎲 ПРИЗНАЧЕННЯ 40-60 (z)", value: z },
                    { name: "🏆 ПРИЗНАЧЕННЯ 60+ (s)", value: s }
                ];
            }

            // Відображення результатів
            function displayResults() {
                const date = document.getElementById('birthDate').value;
                const points = calculateAllPoints(date);
                
                if (!points) {
                    alert('Будь ласка, введіть коректну дату');
                    return;
                }
                
                let html = '';
                points.forEach(p => {
                    html += `
                        <div class="point-card">
                            <div class="point-name">${p.name}</div>
                            <div class="point-value">${p.value}</div>
                        </div>
                    `;
                });
                
                document.getElementById('pointsList').innerHTML = html;
                document.getElementById('resultArea').style.display = 'block';
                
                // Прокрутка до результату
                document.getElementById('resultArea').scrollIntoView({ behavior: 'smooth' });
            }

            // Збереження результату
            function downloadResult() {
                const element = document.getElementById('pointsList');
                html2canvas(element, {
                    scale: 2,
                    backgroundColor: '#ffffff',
                }).then((canvas) => {
                    const ctx = canvas.getContext('2d');
                    ctx.font = 'bold 22px "Segoe UI"';
                    ctx.fillStyle = '#3d2560';
                    ctx.fillText('© Аліна Таро Фадєєва', 30, canvas.height - 40);
                    
                    const link = document.createElement('a');
                    link.download = `matrytsya-${new Date().toISOString().slice(0,10)}.png`;
                    link.href = canvas.toDataURL('image/png');
                    link.click();
                });
            }

            // Обробники подій
            document.getElementById('calcBtn').addEventListener('click', displayResults);
            document.getElementById('downloadBtn').addEventListener('click', downloadResult);
            
            // Автозапуск при завантаженні
            window.addEventListener('load', displayResults);
        })();
    </script>
</body>
</html>
