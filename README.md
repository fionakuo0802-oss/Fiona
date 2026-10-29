<!DOCTYPE html>
<html lang="zh-TW">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>釜山 5 天 4 夜手繪行程</title>

<!-- Google Fonts: Huninn (粉圓體) -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Zen+Maru+Gothic:wght@500;700;900&display=swap" rel="stylesheet">

<!-- Tailwind CSS CDN -->
<script src="https://cdn.tailwindcss.com"></script>

<script>
tailwind.config = {
theme: {
extend: {
colors: {
paper: '#FFFCF6',
ink: '#3E3A39',
coral: '#F2A497',
yamabuki: '#F6D27A',
mizuiro: '#A8D3E6',
wakatake: '#B9DAA5',
},
fontFamily: {
huninn: ['"Zen Maru Gothic"', 'sans-serif'],
},
boxShadow: {
'sketch': '4px 4px 0px #3E3A39',
'sketch-sm': '2px 2px 0px #3E3A39',
'sketch-lg': '6px 6px 0px #3E3A39',
}
}
}
}
</script>

<style>
body {
background-color: #FFFCF6;
color: #3E3A39;
font-family: 'Zen Maru Gothic', sans-serif;
-webkit-tap-highlight-color: transparent;
}

.border-hand {
border: 3px solid #3E3A39;
}

@keyframes float-slow {
0%, 100% { transform: translateY(0px) rotate(0deg); }
50% { transform: translateY(-8px) rotate(1deg); }
}

@keyframes float-reverse {
0%, 100% { transform: translateY(0px) rotate(0deg); }
50% { transform: translateY(6px) rotate(-1deg); }
}

.animate-float {
animation: float-slow 4s ease-in-out infinite;
}

.animate-float-delayed {
animation: float-reverse 5s ease-in-out infinite 1s;
}

.tab-btn {
transition: all 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
}

.tab-btn:active {
transform: scale(0.95);
}

@media (prefers-reduced-motion: reduce) {
.animate-float, .animate-float-delayed {
animation: none !important;
}
}
</style>
</head>
<body class="min-h-screen pb-20">

<!-- 頂端導覽列 -->
<nav class="sticky top-0 z-50 bg-[#FFFCF6]/90 backdrop-blur-md border-b-4 border-ink px-4 py-3">
<div class="max-w-md mx-auto flex justify-between items-center">
<div class="flex items-center gap-2">
<span class="text-2xl">🌊</span>
<span class="font-black text-xl tracking-wide">釜山繪本之旅</span>
</div>
<div class="flex gap-1 text-sm font-bold">
<a href="#flight" class="px-2 py-1 bg-yamabuki border-2 border-ink rounded-lg shadow-sketch-sm">航班</a>
<a href="#days" class="px-2 py-1 bg-coral text-white border-2 border-ink rounded-lg shadow-sketch-sm">行程</a>
<a href="#todo" class="px-2 py-1 bg-wakatake border-2 border-ink rounded-lg shadow-sketch-sm">準備</a>
</div>
</div>
</nav>

<main class="max-w-md mx-auto px-4 pt-6 space-y-8">

<!-- 首頁 Header 卡片與倒數 -->
<section class="bg-paper border-hand rounded-3xl p-5 shadow-sketch relative overflow-hidden">
<!-- 插圖區 -->
<div class="relative h-40 bg-mizuiro/30 rounded-2xl border-2 border-ink mb-4 p-2 flex items-end justify-between overflow-hidden">
<!-- 太陽 -->
<svg class="absolute top-2 right-4 w-12 h-12 text-yamabuki animate-float" fill="currentColor" viewBox="0 0 24 24">
<circle cx="12" cy="12" r="8" stroke="#3E3A39" stroke-width="2"/>
<path d="M12 2v2m0 16v2M2 12h2m16 0h2" stroke="#3E3A39" stroke-width="2" stroke-linecap="round"/>
</svg>

<!-- 海浪與橋 -->
<svg class="absolute bottom-0 left-0 w-full h-16 text-mizuiro" viewBox="0 0 100 30" preserveAspectRatio="none">
<path d="M0 20 Q 25 10, 50 20 T 100 20 L 100 30 L 0 30 Z" fill="currentColor" stroke="#3E3A39" stroke-width="1.5"/>
</svg>

<!-- 膠囊列車 SVG -->
<div class="relative z-10 animate-float-delayed flex items-center bg-coral text-white border-2 border-ink px-3 py-1.5 rounded-xl shadow-sketch-sm">
<span class="text-xl mr-1">🚃</span>
<span class="font-bold text-xs">海雲台膠囊列車</span>
</div>

<div class="relative z-10 bg-white/90 border-2 border-ink px-2 py-1 rounded-lg text-xs font-bold">
4人同行 🇰🇷
</div>
</div>

<div class="text-center space-y-1">
<h1 class="text-2xl font-black text-ink">釜山 5 天 4 夜隨手記</h1>
<p class="text-xs text-ink/70 font-bold">2027/09/01 (三) ～ 2027/09/05 (日)</p>
</div>

<!-- 倒數計時卡 -->
<div class="mt-4 bg-yamabuki/40 border-2 border-ink rounded-2xl p-3 text-center">
<p class="text-xs font-bold text-ink/80 mb-1">距離出發還有</p>
<div id="countdown" class="text-xl font-black text-ink flex justify-center gap-2">
<!-- JS 自動計算倒數 -->
計算中...
</div>
</div>
</section>

<!-- 航班資訊 -->
<section id="flight" class="space-y-3">
<h2 class="text-lg font-black flex items-center gap-2">
<span class="bg-coral text-white p-1 rounded-lg border-2 border-ink">✈️</span> 航班資訊
</h2>
<div class="grid grid-cols-1 gap-3">
<!-- 去程 -->
<div class="bg-white border-hand rounded-2xl p-4 shadow-sketch relative">
<span class="absolute -top-3 left-4 bg-wakatake border-2 border-ink px-2 py-0.5 rounded-full text-xs font-bold">去程 09/01</span>
<div class="flex justify-between items-center mt-1">
<div>
<p class="text-xs font-bold text-ink/60">中華航空 CI190</p>
<p class="text-lg font-black">06:15 桃園 T1</p>
</div>
<div class="text-center text-xs font-bold text-ink/40">➔ 2h 15m ➔</div>
<div class="text-right">
<p class="text-xs font-bold text-ink/60">抵達釜山</p>
<p class="text-lg font-black">09:30 金海 T1</p>
</div>
</div>
</div>
<!-- 回程 -->
<div class="bg-white border-hand rounded-2xl p-4 shadow-sketch relative">
<span class="absolute -top-3 left-4 bg-coral text-white border-2 border-ink px-2 py-0.5 rounded-full text-xs font-bold">回程 09/05</span>
<div class="flex justify-between items-center mt-1">
<div>
<p class="text-xs font-bold text-ink/60">中華航空 CI187</p>
<p class="text-lg font-black">20:00 金海 T1</p>
</div>
<div class="text-center text-xs font-bold text-ink/40">➔ 2h 20m ➔</div>
<div class="text-right">
<p class="text-xs font-bold text-ink/60">抵達桃園</p>
<p class="text-lg font-black">21:20 桃園 T1</p>
</div>
</div>
</div>
</div>
</section>

<!-- 行程頁籤與時間軸 -->
<section id="days" class="space-y-4">
<h2 class="text-lg font-black flex items-center gap-2">
<span class="bg-mizuiro p-1 rounded-lg border-2 border-ink">🗓️</span> 每日行程
</h2>

<!-- Day 切換按鈕 -->
<div class="flex gap-1.5 overflow-x-auto pb-2 scrollbar-none" id="tab-container">
<!-- JS 動態生成按鈕 -->
</div>

<!-- 時間軸內容卡片 -->
<div id="timeline-content" class="space-y-3">
<!-- JS 動態渲染行程列表 -->
</div>
</section>

<!-- 住宿資訊卡片 -->
<section class="space-y-3">
<h2 class="text-lg font-black flex items-center gap-2">
<span class="bg-yamabuki p-1 rounded-lg border-2 border-ink">🏨</span> 住宿安排
</h2>
<div class="space-y-2">
<div class="bg-white border-hand rounded-2xl p-3.5 shadow-sketch flex gap-3 items-center">
<div class="text-2xl bg-yamabuki/30 p-2 rounded-xl border-2 border-ink">🏬</div>
<div class="text-xs">
<span class="bg-yamabuki px-2 py-0.5 border border-ink rounded-full font-bold">Day 1 ~ Day 3</span>
<p class="font-bold text-sm mt-1">西面民宿 (★5.0)</p>
<p class="text-ink/70">1 間臥室 · 4 張床 · 1 間衛浴</p>
</div>
</div>
<div class="bg-white border-hand rounded-2xl p-3.5 shadow-sketch flex gap-3 items-center">
<div class="text-2xl bg-mizuiro/30 p-2 rounded-xl border-2 border-ink">🌊</div>
<div class="text-xs">
<span class="bg-mizuiro px-2 py-0.5 border border-ink rounded-full font-bold">Day 3 ~ Day 5</span>
<p class="font-bold text-sm mt-1">海雲台海景民宿 (★5.0)</p>
<p class="text-ink/70">2 間臥室 · 3 張床 · 1.5 間衛浴</p>
</div>
</div>
</div>
</section>

<!-- 預算與行前提醒 -->
<section id="todo" class="space-y-3">
<h2 class="text-lg font-black flex items-center gap-2">
<span class="bg-wakatake p-1 rounded-lg border-2 border-ink">📝</span> 行前準備與預算估算
</h2>

<div class="bg-white border-hand rounded-2xl p-4 shadow-sketch space-y-3 text-xs">
<h3 class="font-bold text-sm border-b-2 border-ink/20 pb-1">💡 重要提醒</h3>
<ul class="list-disc list-inside space-y-1 font-bold text-ink/80">
<li>電子入境卡 E-Arrival Card（入境前 3 天內填寫）</li>
<li>轉接頭：220V 圓形雙孔</li>
<li>換匯：攜帶台幣至西面換錢所匯率較好</li>
</ul>

<h3 class="font-bold text-sm border-b-2 border-ink/20 pb-1 pt-2">💰 個人預估費用</h3>
<div class="grid grid-cols-2 gap-2 font-bold text-ink/80">
<div>機票：NT$ 10,000</div>
<div>住宿：NT$ 5,000</div>
<div>機埸巴士：₩17,000</div>
<div>地鐵/公車：約 ₩12,200</div>
<div>斜坡滑車：NT$ 900</div>
<div>釜山 Pass：NT$ 920</div>
<div>膠囊列車：₩15,000</div>
<div>預估餐費：NT$ 4,500</div>
</div>
</div>
</section>

<!-- 互動計算機 -->
<section class="bg-paper border-hand rounded-2xl p-4 shadow-sketch space-y-2">
<h3 class="font-bold text-sm flex items-center gap-1">
<span>🧮</span> 韓元轉台幣速算 (匯率約 0.024)
</h3>
<div class="flex gap-2">
<input type="number" id="krw-input" placeholder="輸入韓元 ₩" class="w-full border-2 border-ink rounded-xl px-3 py-1.5 text-sm font-bold bg-white focus:outline-none">
<div class="whitespace-nowrap bg-yamabuki border-2 border-ink px-3 py-1.5 rounded-xl font-bold text-sm flex items-center" id="twd-result">
≈ NT$ 0
</div>
</div>
</section>

</main>

<!-- 行程資料與邏輯腳本 -->
<script>
// 行程資料集
const itineraryData = [
{
day: 1,
date: '09/01 (三)',
title: '抵達釜山與荒嶺山夜景',
events: [
{ time: '03:45', name: '桃園機場集合', trans: '集合', mode: 'normal' },
{ time: '09:30', name: '抵達金海國際機場', trans: '航班', mode: 'normal' },
{ time: '10:30', name: '搭機場巴士至西面住宿寄放行李', trans: '機場巴士', mode: 'normal' },
{ time: '12:30', name: '午餐（西面美食）', trans: '步行', mode: 'normal' },
{ time: '13:30', name: '西面商圈逛街', trans: '步行', mode: 'must' },
{ time: '16:30', name: '晚餐：橋村炸雞', trans: '美食', mode: 'must' },
{ time: '18:00', name: '搭 Uber 前往荒嶺山展望台', trans: 'Uber', mode: 'normal' },
{ time: '18:30', name: '荒嶺山展望台看釜山夜景', trans: '景點', mode: 'must' },
{ time: '20:00', name: '搭 Uber 返回西面住宿', trans: 'Uber', mode: 'normal' }
]
},
{
day: 2,
date: '09/02 (四)',
title: '白淺灘與多大浦夕陽',
events: [
{ time: '08:30', name: '前往白淺灘文化村', trans: '地鐵/公車', mode: 'normal' },
{ time: '09:30', name: '白淺灘文化村散步拍照', trans: '景點', mode: 'must' },
{ time: '12:00', name: '搭 Uber 前往松島纜車', trans: 'Uber', mode: 'normal' },
{ time: '12:20', name: '松島海上纜車', trans: '纜車', mode: 'must' },
{ time: '13:30', name: '午餐：海底貝殼王國', trans: '美食', mode: 'must' },
{ time: '14:30', name: '搭 Uber 前往192希望單軌電梯', trans: 'Uber', mode: 'normal' },
{ time: '15:00', name: '192希望單軌電梯', trans: '景點', mode: 'normal' },
{ time: '16:20', name: '搭地鐵前往多大浦', trans: '地鐵', mode: 'normal' },
{ time: '17:15', name: '多大浦海水浴場看日落', trans: '景點', mode: 'must' },
{ time: '19:20', name: '搭地鐵返回西面', trans: '地鐵', mode: 'normal' },
{ time: '20:30', name: '晚餐：돼지나무 사랑걸렸네', trans: '美食', mode: 'normal' }
]
},
{
day: 3,
date: '09/03 (五)',
title: '甘川文化村與天空膠囊列車',
events: [
{ time: '09:40', name: '退房寄放行李', trans: '準備', mode: 'normal' },
{ time: '10:00', name: '搭 Uber 前往甘川文化村', trans: 'Uber', mode: 'normal' },
{ time: '10:30', name: '甘川文化村（尋找小王子）', trans: '景點', mode: 'must' },
{ time: '12:30', name: '午餐：街頭輕食小吃', trans: '美食', mode: 'normal' },
{ time: '13:30', name: '返西面拿行李移動至海雲台', trans: '地鐵', mode: 'normal' },
{ time: '15:00', name: '走路至尾浦搭海濱列車', trans: '步行', mode: 'normal' },
{ time: '15:45', name: '海濱列車前往青沙浦', trans: '列車', mode: 'normal' },
{ time: '16:10', name: '青沙浦天空步道與平交道拍照', trans: '景點', mode: 'must' },
{ time: '18:00', name: '天空膠囊列車（青沙浦➔尾浦）', trans: '膠囊列車', mode: 'must' },
{ time: '18:30', name: '海雲台商圈逛街', trans: '步行', mode: 'normal' },
{ time: '20:00', name: '晚餐：海雲台美食', trans: '美食', mode: 'normal' }
]
},
{
day: 4,
date: '09/04 (六)',
title: '斜坡滑車與廣安里無人機秀',
events: [
{ time: '09:30', name: '搭 Uber 前往斜坡滑車', trans: 'Uber', mode: 'normal' },
{ time: '10:00', name: 'Skyline Luge 斜坡滑車', trans: '體驗', mode: 'must' },
{ time: '12:00', name: '午餐：재성밀면（小麦麵）', trans: '美食', mode: 'normal' },
{ time: '13:20', name: '釜山樂天世界冒險樂園', trans: '樂園', mode: 'must' },
{ time: '17:30', name: '搭 Uber 前往廣安里', trans: 'Uber', mode: 'normal' },
{ time: '18:20', name: '廣安里海灘逛街與咖啡廳', trans: '步行', mode: 'normal' },
{ time: '19:50', name: '廣安里無人機燈光秀', trans: '表演', mode: 'must' },
{ time: '20:30', name: '晚餐：水營豬肉湯飯', trans: '美食', mode: 'must' },
{ time: '21:30', name: '搭地鐵返回海雲台住宿', trans: '地鐵', mode: 'normal' }
]
},
{
day: 5,
date: '09/05 (日)',
title: 'F1963 複合文創與返家',
events: [
{ time: '10:30', name: '海雲台退房寄放行李', trans: '準備', mode: 'normal' },
{ time: '10:40', name: '搭 Uber 前往 F1963', trans: 'Uber', mode: 'normal' },
{ time: '11:10', name: 'F1963 藝術園區與二手書簡', trans: '景點', mode: 'must' },
{ time: '12:30', name: '午餐（園區內餐廳）', trans: '美食', mode: 'normal' },
{ time: '13:30', name: '返回海雲台周邊最後補貨', trans: 'Uber', mode: 'normal' },
{ time: '15:00', name: '搭乘機場巴士前往金海機場', trans: '機場巴士', mode: 'normal' },
{ time: '17:00', name: '抵達金海機場辦理登機與託運', trans: '機場', mode: 'normal' },
{ time: '21:20', name: '平安抵達桃園國際機場', trans: '返家', mode: 'normal' }
]
}
];

let activeDay = 1;

// 初始化倒數計時
function updateCountdown() {
const targetDate = new Date('2027-09-01T06:15:00');
const now = new Date();
const diff = targetDate - now;

if (diff <= 0) {
document.getElementById('countdown').innerText = "旅程啟航中！🎉";
return;
}

const days = Math.floor(diff / (1000 * 60 * 60 * 24));
const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);

document.getElementById('countdown').innerHTML = `
<span class="bg-white border border-ink px-2 py-0.5 rounded-lg">${days} 天</span>
<span class="bg-white border border-ink px-2 py-0.5 rounded-lg">${hours} 小時</span>
`;
}

// 渲染 Day 頁籤
function renderTabs() {
const container = document.getElementById('tab-container');
container.innerHTML = itineraryData.map(d => {
const isActive = d.day === activeDay;
const bgClass = isActive ? 'bg-coral text-white shadow-sketch' : 'bg-white text-ink border-2 border-ink';
return `
<button onclick="switchDay(${d.day})" class="tab-btn px-3.5 py-2 rounded-xl text-xs font-bold whitespace-nowrap border-hand ${bgClass}">
Day ${d.day} (${d.date.split(' ')[0]})
</button>
`;
}).join('');
}

// 切換 Day
function switchDay(day) {
activeDay = day;
renderTabs();
renderTimeline();
}

// 渲染時間軸
function renderTimeline() {
const container = document.getElementById('timeline-content');
const currentData = itineraryData.find(d => d.day === activeDay);

container.innerHTML = `
<div class="bg-yamabuki/20 border-hand rounded-xl p-2.5 text-xs font-bold mb-3 flex justify-between items-center">
<span>📍 ${currentData.title}</span>
<span class="text-ink/60">${currentData.date}</span>
</div>
${currentData.events.map(e => `
<div class="bg-white border-hand rounded-2xl p-3.5 shadow-sketch space-y-2 relative">
<div class="flex justify-between items-start">
<div class="flex items-center gap-2">
<span class="bg-ink text-white font-black text-xs px-2 py-0.5 rounded-md">${e.time}</span>
<span class="font-bold text-sm text-ink">${e.name}</span>
</div>
${e.mode === 'must' ? '<span class="bg-coral text-white text-[10px] font-black px-1.5 py-0.5 rounded border border-ink">必去</span>' : ''}
</div>

<div class="flex justify-between items-center text-xs pt-1 border-t border-ink/10">
<span class="bg-mizuiro/50 px-2 py-0.5 rounded-md font-bold text-ink/80 border border-ink/30">🚌 ${e.trans}</span>
<a href="https://www.google.com/maps/search/?api=1&query=${encodeURIComponent('釜山 ' + e.name)}" target="_blank" class="bg-paper border border-ink px-2 py-1 rounded-lg font-bold flex items-center gap-1 hover:bg-yamabuki transition-colors">
🗺️ 地圖導航
</a>
</div>
</div>
`).join('')}
`;
}

// 匯率計算機
document.getElementById('krw-input').addEventListener('input', function(e) {
const val = parseFloat(e.target.value) || 0;
const twd = Math.round(val * 0.024);
document.getElementById('twd-result').innerText = `≈ NT$ ${twd.toLocaleString()}`;
});

// 初始化執行
updateCountdown();
setInterval(updateCountdown, 60000);
renderTabs();
renderTimeline();
</script>
</body>
</html>


