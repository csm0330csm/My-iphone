
<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, viewport-fit=cover">
<title>iPhone Mockup</title>
<style>
*{box-sizing:border-box}
html,body{margin:0;width:100%;height:100%;font-family:-apple-system,BlinkMacSystemFont,"Apple SD Gothic Neo",sans-serif;color:#111}
body{overflow:hidden;background:#d8e6ff}
button,input,textarea{font:inherit}
button{cursor:pointer;border:0}
#phone{position:relative;width:100%;height:100dvh;overflow:hidden}
.screen{position:absolute;inset:0;overflow:hidden}
.screen[hidden]{display:none!important}
.wallpaper{background:radial-gradient(ellipse at 25% 20%,#fff 0 8%,transparent 35%),radial-gradient(ellipse at 80% 35%,#ffe0ebcc 0 8%,transparent 35%),radial-gradient(ellipse at 45% 80%,#74a7ffe6 0 15%,transparent 48%),linear-gradient(145deg,#d8e8ff,#c6d8ff 32%,#e8d8f2 62%,#9fc6f7)}
.status{position:absolute;z-index:10;top:0;left:0;right:0;height:43px;padding:12px 25px 0;display:flex;justify-content:space-between;font-size:14px;font-weight:650;pointer-events:none}
.status-right{display:flex;gap:5px;align-items:center}
.battery{width:20px;height:10px;border:1.4px solid;border-radius:3px;position:relative}
.battery:before{content:"";position:absolute;inset:1.5px 3px;background:currentColor;border-radius:1px}
.lock-screen{text-align:center;padding-top:75px}
.date{font-size:16px;margin-top:14px}
.big-time{font-size:clamp(72px,20vw,104px);font-weight:250;letter-spacing:-5px;line-height:1.08}
.lock-notifications{position:absolute;top:43%;left:14px;right:14px;display:flex;flex-direction:column;gap:9px;text-align:left}
.notification{background:#f7f8fce8;backdrop-filter:blur(22px);-webkit-backdrop-filter:blur(22px);border:1px solid #ffffff99;border-radius:19px;padding:12px 14px;box-shadow:0 6px 25px #26416e1a;animation:slideIn .35s ease-out}
.notif-top{display:flex;align-items:center;gap:8px;font-size:12px;color:#666}
.notif-icon{width:27px;height:27px;border-radius:7px;background:#34c759;color:white;display:grid;place-items:center}
.notif-app{font-weight:650;color:#333}
.notif-now{margin-left:auto;font-size:11px}
.notif-title{font-weight:700;font-size:14px;margin-top:5px}
.notif-body{font-size:14px;margin-top:3px;line-height:1.35}
.lock-bottom{position:absolute;bottom:35px;left:0;right:0;display:flex;justify-content:space-between;padding:0 34px}
.round-control{width:48px;height:48px;border-radius:50%;background:#2328372e;color:white;font-size:22px}
.lock-hint{position:absolute;bottom:13px;left:0;right:0;font-size:12px}
.home{padding:66px 21px 90px}
.home-date{font-size:14px;font-weight:600;margin:8px 0 20px;color:#30394c}
.app-grid{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:22px 12px}
.app{display:flex;flex-direction:column;align-items:center;gap:6px;background:none;padding:0;min-width:0}
.app-icon{width:min(17vw,64px);height:min(17vw,64px);border-radius:22%;display:grid;place-items:center;font-size:31px;box-shadow:0 4px 10px #273e5a24;position:relative}
.app-name{font-size:11px;color:#172033;white-space:nowrap}
.badge{position:absolute;right:-5px;top:-5px;background:#ff3b30;color:white;min-width:21px;height:21px;border-radius:11px;padding:0 5px;display:grid;place-items:center;font-size:12px;font-weight:700;border:1px solid white}
.icon-phone{background:linear-gradient(145deg,#6ee28c,#20b957);color:white}
.icon-message{background:linear-gradient(145deg,#63e779,#1cac49);color:white}
.icon-photos{background:white}
.icon-camera{background:linear-gradient(145deg,#5a606a,#17191d);color:white}
.icon-notes{background:linear-gradient(white 0 23%,#ffe77a 23%);color:#333}
.icon-settings{background:linear-gradient(145deg,#cfd4db,#8a929e);color:white}
.icon-safari{background:linear-gradient(145deg,#8fe1ff,#2478ed);color:white}
.icon-music{background:linear-gradient(145deg,#ff8dd2,#ff375f);color:white}
.dock{position:absolute;bottom:22px;left:14px;right:14px;border-radius:27px;padding:12px 16px;background:#f5f7fc73;backdrop-filter:blur(24px);display:flex;justify-content:space-around;gap:14px}
.dock .app-icon{width:min(16vw,60px);height:min(16vw,60px)}
.home-indicator{position:absolute;z-index:30;bottom:7px;left:50%;transform:translateX(-50%);width:135px;height:5px;background:#111;border-radius:5px}
.panel{background:#f5f5f7}
.nav{height:55px;padding:8px 16px;display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid #ddd;background:#fafafcf2;position:relative;z-index:2}
.nav-title{font-weight:700;font-size:17px}
.nav-btn{background:none;color:#087cff;font-size:16px;padding:7px}
.chat-head{height:68px;display:flex;align-items:center;justify-content:center;position:relative;background:#f7f7f9;border-bottom:1px solid #ddd}
.chat-head button{position:absolute;left:10px;background:none;color:#087cff;font-size:16px}
.avatar{width:36px;height:36px;border-radius:50%;background:linear-gradient(145deg,#b7d7ff,#647fa8);display:grid;place-items:center;color:white;font-weight:700}
.chat-name{font-size:13px;font-weight:600;margin-top:3px}
.chat-body{position:absolute;top:123px;bottom:67px;left:0;right:0;padding:14px 12px;overflow:auto;background:#f7f7f9;display:flex;flex-direction:column;gap:10px}
.day-label{text-align:center;font-size:11px;color:#888;margin:8px 0}
.bubble{max-width:79%;padding:10px 13px;border-radius:18px;font-size:15px;line-height:1.35;overflow-wrap:anywhere}
.bubble.in{align-self:flex-start;background:#e5e5ea;border-bottom-left-radius:5px}
.bubble.out{align-self:flex-end;background:#1684ff;color:white;border-bottom-right-radius:5px}
.chat-compose{position:absolute;bottom:0;left:0;right:0;min-height:65px;padding:10px 9px calc(10px + env(safe-area-inset-bottom));display:flex;gap:7px;align-items:center;background:#f8f8fa;border-top:1px solid #ddd}
.chat-compose input{min-width:0;flex:1;border:1px solid #d3d3d8;border-radius:22px;padding:10px 14px;background:white;outline:none}
.send{background:#087cff;color:white;border-radius:50%;width:34px;height:34px;font-weight:700}
.photo-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:2px;padding:2px;overflow:auto}
.photo-grid img{width:100%;aspect-ratio:1;object-fit:cover;background:#ddd}
.memo{margin:15px;padding:16px;border-radius:13px;background:white;min-height:160px;line-height:1.6;white-space:pre-wrap;width:calc(100% - 30px)}
.keypad-wrap{position:absolute;inset:0;display:flex;flex-direction:column;align-items:center;padding-top:100px;background:#f5f6faf5}
.pass-avatar{width:74px;height:74px;border-radius:50%;background:linear-gradient(145deg,#b8d9ff,#7586b5);display:grid;place-items:center;color:white;font-size:30px}
.pass-title{font-size:22px;font-weight:650;margin:18px 0 8px}
.pass-sub{font-size:14px;color:#666;margin-bottom:22px;text-align:center;padding:0 15px}
.pass-dots{display:flex;gap:14px;margin:0 0 30px}
.dot{width:11px;height:11px;border:1px solid #555;border-radius:50%}
.dot.filled{background:#222}
.keypad{display:grid;grid-template-columns:repeat(3,72px);gap:12px 18px}
.key{height:60px;width:72px;border-radius:50%;background:#dfe1e7;font-size:25px}
.key small{display:block;font-size:9px;letter-spacing:1px}
.key.blank{visibility:hidden}
.call-screen{background:linear-gradient(160deg,#202e48,#090d18 75%);color:white;text-align:center;padding-top:105px}
.call-avatar{width:110px;height:110px;border-radius:50%;margin:0 auto 20px;background:linear-gradient(145deg,#c2d9ff,#637aab);display:grid;place-items:center;font-size:42px}
.call-name{font-size:30px;font-weight:400}
.call-status{font-size:16px;color:#d0d5df;margin-top:10px}
.call-actions{position:absolute;bottom:90px;left:0;right:0;display:flex;justify-content:space-evenly;align-items:center}
.call-action{display:flex;flex-direction:column;align-items:center;gap:9px;font-size:12px;color:white;background:none}
.call-circle{width:58px;height:58px;border-radius:50%;background:#ffffff2c;display:grid;place-items:center;font-size:23px}
.call-circle.end{background:#ff3b30}
.popup-layer{position:absolute;z-index:50;top:52px;left:10px;right:10px;display:flex;flex-direction:column;gap:8px;pointer-events:none}
.popup-layer .notification{pointer-events:auto;cursor:pointer}
.toast{position:absolute;z-index:60;bottom:32px;left:50%;transform:translateX(-50%);padding:11px 16px;border-radius:22px;background:#222;color:white;font-size:13px;white-space:nowrap;box-shadow:0 5px 20px #0002;animation:slideIn .25s}
@keyframes slideIn{from{opacity:0;transform:translateY(-12px)}to{opacity:1;transform:translateY(0)}}
@media(min-width:600px){body{display:grid;place-items:center;background:#d8dce5}#phone{width:390px;height:min(844px,94dvh);border-radius:45px;border:8px solid #20232a;box-shadow:0 20px 70px #18243c44}.home-indicator{bottom:7px}}
</style>
</head>
<body>
<div id="phone">
  <div class="status"><span id="statusTime">9:41</span><span class="status-right"><span>▂▄▆</span><span>Wi-Fi</span><span class="battery"></span></span></div>
  <div id="popupLayer" class="popup-layer"></div>

  <section id="lock" class="screen wallpaper lock-screen">
    <div class="date" id="lockDate">10월 19일 월요일</div>
    <div class="big-time" id="lockTime">9:41</div>
    <div id="lockNotifications" class="lock-notifications"></div>
    <div class="lock-bottom">
      <button class="round-control" onclick="toast('손전등은 연출용이에요')">◉</button>
      <button class="round-control" onclick="openScreen('photos')">◎</button>
    </div>
    <div class="lock-hint">위로 쓸어올려 열기</div>
  </section>

  <section id="home" class="screen wallpaper home" hidden>
    <div class="home-date" id="homeDate">월요일, 10월 19일</div>
    <div class="app-grid">
      <button class="app" onclick="openScreen('messages')"><span class="app-icon icon-message">●<span id="messageBadge" class="badge" hidden>1</span></span><span class="app-name">메시지</span></button>
      <button class="app" onclick="openScreen('photos')"><span class="app-icon icon-photos">🌈</span><span class="app-name">사진</span></button>
      <button class="app" onclick="openScreen('phone')"><span class="app-icon icon-phone">☎</span><span class="app-name">전화</span></button>
      <button class="app" onclick="openScreen('notes')"><span class="app-icon icon-notes">≡</span><span class="app-name">메모</span></button>
      <button class="app" onclick="openScreen('settings')"><span class="app-icon icon-settings">⚙</span><span class="app-name">설정</span></button>
      <button class="app" onclick="toast('Safari 화면은 데모에서 생략했어요')"><span class="app-icon icon-safari">◉</span><span class="app-name">Safari</span></button>
      <button class="app" onclick="toast('카메라는 연출용이에요')"><span class="app-icon icon-camera">◎</span><span class="app-name">카메라</span></button>
      <button class="app" onclick="toast('음악 앱은 데모에서 생략했어요')"><span class="app-icon icon-music">♫</span><span class="app-name">음악</span></button>
    </div>
    <div class="dock">
      <button class="app" onclick="openScreen('phone')"><span class="app-icon icon-phone">☎</span></button>
      <button class="app" onclick="openScreen('messages')"><span class="app-icon icon-message">●<span id="dockBadge" class="badge" hidden>1</span></span></button>
      <button class="app" onclick="openScreen('photos')"><span class="app-icon icon-photos">🌈</span></button>
      <button class="app" onclick="openScreen('settings')"><span class="app-icon icon-settings">⚙</span></button>
    </div>
  </section>

  <section id="messages" class="screen panel" hidden>
    <div class="nav"><button class="nav-btn" onclick="openScreen('home')">‹ 홈</button><span class="nav-title">메시지</span><button class="nav-btn" onclick="toast('새 메시지 연출')">＋</button></div>
    <div class="chat-head"><button onclick="openScreen('home')">‹ 뒤로</button><div><div class="avatar">수</div><div class="chat-name">안수호</div></div></div>
    <div id="chatBody" class="chat-body"><div class="day-label">문자 메시지 · 오늘</div><div class="bubble in">운동 중 나중에 연락할게.</div></div>
    <form id="chatForm" class="chat-compose"><input id="chatInput" placeholder="문자 메시지" autocomplete="off"><button class="send" type="submit">↑</button></form>
  </section>

  <section id="photos" class="screen panel" hidden>
    <div class="nav"><button class="nav-btn" onclick="openScreen('home')">‹ 홈</button><span class="nav-title">사진</span><button class="nav-btn" onclick="document.getElementById('photoUpload').click()">＋</button></div>
    <input id="photoUpload" type="file" accept="image/*" multiple hidden>
    <div id="photoGrid" class="photo-grid">
      <img alt="하늘" src="https://images.unsplash.com/photo-1470252649378-9c29740c9fa8?auto=format&fit=crop&w=400&q=80">
      <img alt="바다" src="https://images.unsplash.com/photo-1500375592092-40eb2168fd21?auto=format&fit=crop&w=400&q=80">
      <img alt="꽃" src="https://images.unsplash.com/photo-1490750967868-88aa4486c946?auto=format&fit=crop&w=400&q=80">
      <img alt="야경" src="https://images.unsplash.com/photo-1519608487953-e999c86e7455?auto=format&fit=crop&w=400&q=80">
      <img alt="산" src="https://images.unsplash.com/photo-1464822759023-fed622ff2c3b?auto=format&fit=crop&w=400&q=80">
      <img alt="거리" src="https://images.unsplash.com/photo-1519501025264-65ba15a82390?auto=format&fit=crop&w=400&q=80">
    </div>
  </section>

  <section id="notes" class="screen panel" hidden>
    <div class="nav"><button class="nav-btn" onclick="openScreen('home')">‹ 홈</button><span class="nav-title">메모</span><button class="nav-btn" onclick="saveMemo()">완료</button></div>
    <textarea id="memoText" class="memo" placeholder="메모를 입력하세요">시은아 잠이 오냐..</textarea>
  </section>

  <section id="settings" class="screen panel" hidden>
    <div class="nav"><button class="nav-btn" onclick="openScreen('home')">‹ 홈</button><span class="nav-title">설정</span><span></span></div>
    <div style="padding:20px;line-height:1.8">
      <h3>iPhone 설정</h3><p>이 화면은 웹사이트용 모형입니다.</p>
      <p>데모 암호: <b>1234</b></p>
      <button class="nav-btn" onclick="showPasscode()">암호 입력 화면 보기</button>
      <p style="color:#777;font-size:13px">실제 전화·문자·iOS 알림이 아니라 사이트 안에서 재현되는 연출입니다.</p>
    </div>
  </section>

  <section id="phone" class="screen call-screen" hidden>
    <div class="nav" style="background:transparent;border:0;color:white"><button class="nav-btn" style="color:white" onclick="openScreen('home')">‹ 홈</button><span>최근 통화</span><span></span></div>
    <div style="padding:30px 20px"><div class="call-avatar">수</div><div class="call-name">안수호</div><div class="call-status">휴대전화</div><p style="color:#bbc3d2;margin-top:24px">최근 통화</p><button style="margin-top:18px;padding:12px 22px;border-radius:22px;background:#34c759;color:white" onclick="incomingCall()">전화 걸기</button></div>
  </section>

  <section id="passcode" class="screen" hidden>
    <div class="keypad-wrap"><div class="pass-avatar">◉</div><div class="pass-title">암호 입력</div><div class="pass-sub">iPhone을 잠금 해제하려면 암호를 입력하십시오</div><div id="passDots" class="pass-dots"><span class="dot"></span><span class="dot"></span><span class="dot"></span><span class="dot"></span></div>
      <div class="keypad">
        <button class="key" onclick="pressKey('1')">1<small>&nbsp;</small></button><button class="key" onclick="pressKey('2')">2<small>ABC</small></button><button class="key" onclick="pressKey('3')">3<small>DEF</small></button>
        <button class="key" onclick="pressKey('4')">4<small>GHI</small></button><button class="key" onclick="pressKey('5')">5<small>JKL</small></button><button class="key" onclick="pressKey('6')">6<small>MNO</small></button>
        <button class="key" onclick="pressKey('7')">7<small>PQRS</small></button><button class="key" onclick="pressKey('8')">8<small>TUV</small></button><button class="key" onclick="pressKey('9')">9<small>WXYZ</small></button>
        <button class="key blank"></button><button class="key" onclick="pressKey('0')">0<small>&nbsp;</small></button><button class="key blank"></button>
      </div><button class="nav-btn" style="margin-top:22px;color:#333" onclick="openScreen('lock')">취소</button>
    </div>
  </section>

  <section id="incoming" class="screen call-screen" hidden>
    <div style="font-size:14px;color:#d4d9e4">iPhone</div><div class="call-avatar" style="margin-top:100px">수</div><div class="call-name">안수호</div><div class="call-status">iPhone 전화</div>
    <div class="call-actions"><button class="call-action" onclick="openScreen('home')"><span class="call-circle end">✕</span>거절</button><button class="call-action" onclick="answerCall()"><span class="call-circle" style="background:#34c759">☎</span>응답</button></div>
  </section>

  <section id="activeCall" class="screen call-screen" hidden>
    <div style="font-size:14px;color:#d4d9e4">통화 중</div><div class="call-avatar" style="margin-top:100px">수</div><div class="call-name">안수호</div><div id="callTimer" class="call-status">00:00</div>
    <div class="call-actions"><button class="call-action" onclick="toast('음소거는 연출용이에요')"><span class="call-circle">◉</span>음소거</button><button class="call-action" onclick="openScreen('home')"><span class="call-circle end">☎</span>종료</button><button class="call-action" onclick="toast('키패드는 연출용이에요')"><span class="call-circle">▦</span>키패드</button></div>
  </section>
  <div id="homeIndicator" class="home-indicator" hidden onclick="openScreen('home')"></div>
</div>

<script>
const screens=[...document.querySelectorAll('.screen')];
let current='lock',unread=0,pass='',callStarted=0,callInterval=null,scheduled=false;
const demoMessages=[
 {title:'안수호',body:'지금 뭐 해?',delay:7000},
 {title:'안수호',body:'시은아 잠이 오냐..',delay:18000}
];

function openScreen(id){
 screens.forEach(s=>s.hidden=s.id!==id);
 current=id;
 document.getElementById('homeIndicator').hidden=['lock','passcode','incoming','activeCall'].includes(id);
 if(id==='messages'){unread=0;updateBadge();document.getElementById('chatBody').scrollTop=99999;}
}
function updateBadge(){
 ['messageBadge','dockBadge'].forEach(id=>{
  const el=document.getElementById(id);
  el.hidden=unread===0;el.textContent=unread>9?'9+':unread;
 });
}
function escapeHtml(s){
 return String(s).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
}
function notificationMarkup(title,body){
 return `<div class="notif-top"><span class="notif-icon">●</span><span class="notif-app">메시지</span><span class="notif-now">지금</span></div><div class="notif-title">${escapeHtml(title)}</div><div class="notif-body">${escapeHtml(body)}</div>`;
}
function showNotification(item){
 unread++;updateBadge();
 const lock=document.getElementById('lockNotifications');
 const n=document.createElement('div');
 n.className='notification';n.innerHTML=notificationMarkup(item.title,item.body);
 n.onclick=()=>openScreen('messages');lock.prepend(n);
 const popup=document.createElement('div');
 popup.className='notification';popup.innerHTML=notificationMarkup(item.title,item.body);
 popup.onclick=()=>openScreen('messages');
 const layer=document.getElementById('popupLayer');
 layer.prepend(popup);
 while(layer.children.length>2)layer.lastElementChild.remove();
 setTimeout(()=>{if(popup.isConnected)popup.remove()},6500);
 if(current!=='lock')toast('새 메시지: '+item.body);
 const bubble=document.createElement('div');
 bubble.className='bubble in';bubble.textContent=item.body;
 document.getElementById('chatBody').appendChild(bubble);
}
function scheduleMessages(){
 if(scheduled)return;
 scheduled=true;
 demoMessages.forEach(m=>setTimeout(()=>showNotification(m),m.delay));
}
function toast(message){
 const old=document.querySelector('.toast');if(old)old.remove();
 const el=document.createElement('div');el.className='toast';
 el.textContent=message;document.getElementById('phone').appendChild(el);
 setTimeout(()=>el.remove(),2200);
}
function showPasscode(){pass='';renderDots();openScreen('passcode')}
function pressKey(k){
 if(pass.length>=4)return;
 pass+=k;renderDots();
 if(pass.length===4){
  setTimeout(()=>{
   if(pass==='1234'){openScreen('home');toast('잠금 해제됨')}
   else{pass='';renderDots();toast('암호가 올바르지 않습니다')}
  },180);
 }
}
function renderDots(){
 document.querySelectorAll('#passDots .dot').forEach((d,i)=>d.classList.toggle('filled',i<pass.length));
}
document.getElementById('chatForm').addEventListener('submit',e=>{
 e.preventDefault();
 const input=document.getElementById('chatInput'),v=input.value.trim();
 if(!v)return;
 const b=document.createElement('div');b.className='bubble out';b.textContent=v;
 document.getElementById('chatBody').appendChild(b);input.value='';
 document.getElementById('chatBody').scrollTop=99999;
});
document.getElementById('photoUpload').addEventListener('change',e=>{
 const grid=document.getElementById('photoGrid');
 [...e.target.files].forEach(file=>{
  if(!file.type.startsWith('image/'))return;
  const img=document.createElement('img');img.alt=file.name;
  img.src=URL.createObjectURL(file);grid.prepend(img);
 });
 toast('선택한 사진은 현재 기기에서만 보여요');
});
function saveMemo(){toast('메모 저장은 이 화면의 임시 연출이에요')}
function incomingCall(){openScreen('incoming')}
function answerCall(){
 openScreen('activeCall');callStarted=Date.now();
 if(callInterval)clearInterval(callInterval);
 callInterval=setInterval(()=>{
  const s=Math.floor((Date.now()-callStarted)/1000);
  document.getElementById('callTimer').textContent=String(Math.floor(s/60)).padStart(2,'0')+':'+String(s%60).padStart(2,'0');
 },1000);
}
function updateDate(){
 const d=new Date();
 const time=d.toLocaleTimeString('ko-KR',{hour:'2-digit',minute:'2-digit',hour12:false});
 document.getElementById('statusTime').textContent=time;
 document.getElementById('lockTime').textContent=time;
 document.getElementById('lockDate').textContent=d.toLocaleDateString('ko-KR',{month:'long',day:'numeric',weekday:'long'});
 document.getElementById('homeDate').textContent=d.toLocaleDateString('ko-KR',{weekday:'long',month:'long',day:'numeric'});
}
let touchStartY=0;
document.getElementById('phone').addEventListener('touchstart',e=>{
 touchStartY=e.touches[0].clientY;
},{passive:true});
document.getElementById('phone').addEventListener('touchend',e=>{
 const dy=touchStartY-e.changedTouches[0].clientY;
 if(current==='lock'&&dy>35)showPasscode();
},{passive:true});
document.getElementById('phone').addEventListener('click',e=>{
 if(current==='lock'&&e.target.closest('.lock-screen')&&!e.target.closest('button'))showPasscode();
});
updateDate();
setInterval(updateDate,30000);
updateBadge();
scheduleMessages();
</script>
</body>
</html>
