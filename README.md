<style>
/* === Steam Verification Block === */
 .steam-verify-block {
 margin-top: 16px;
 padding: 16px;
 border-radius: 12px;
 background: rgba(43, 47, 56, 0.6);
 border: 1px solid rgba(255,255,255,0.08);
 }
 .steam-verify-title {
 display: flex;
 align-items: center;
 gap: 8px;
 font-size: 15px;
 font-weight: 600;
 color: #c7d0e0;
 margin-bottom: 12px;
 }
 .steam-verify-title .material-symbols-outlined {
 font-size: 20px;
 color: #66c0f4;
 }
 .steam-verify-row {
 display: flex;
 align-items: center;
 gap: 10px;
 margin-bottom: 10px;
 flex-wrap: wrap;
 }
 .steam-verify-row label {
 font-size: 13px;
 color: #8f9bb3;
 min-width: 80px;
 }
 .steam-verify-input {
 flex: 1;
 min-width: 180px;
 padding: 8px 12px;
 border-radius: 8px;
 border: 1px solid rgba(255,255,255,0.12);
 background: rgba(0,0,0,0.3);
 color: #e0e6f0;
 font-size: 13px;
 font-family: 'Inter', sans-serif;
 outline: none;
 transition: border-color 0.2s;
 }
 .steam-verify-input:focus {
 border-color: #66c0f4;
 }
 .steam-verify-input::placeholder {
 color: #5a6378;
 }
 .steam-verify-btn {
 padding: 8px 16px;
 border-radius: 8px;
 border: none;
 background: linear-gradient(135deg, #1b2838, #2a475e);
 color: #c7d0e0;
 font-size: 13px;
 font-weight: 500;
 cursor: pointer;
 font-family: 'Inter', sans-serif;
 transition: all 0.2s;
 white-space: nowrap;
 }
 .steam-verify-btn:hover {
 background: linear-gradient(135deg, #2a475e, #66c0f4);
 color: #fff;
 }
 .steam-verify-btn:disabled {
 opacity: 0.5;
 cursor: not-allowed;
 }
 .steam-code-display {
 display: flex;
 align-items: center;
 gap: 10px;
 margin: 10px 0;
 padding: 12px 14px;
 border-radius: 8px;
 background: rgba(102, 192, 244, 0.08);
 border: 1px dashed rgba(102, 192, 244, 0.3);
 }
 .steam-code-text {
 font-family: 'Courier New', monospace;
 font-size: 16px;
 font-weight: 700;
 color: #66c0f4;
 letter-spacing: 1px;
 flex: 1;
 user-select: all;
 }
 .steam-code-copy {
 padding: 4px 10px;
 border-radius: 6px;
 border: 1px solid rgba(102,192,244,0.3);
 background: transparent;
 color: #66c0f4;
 font-size: 12px;
 cursor: pointer;
 font-family: 'Inter', sans-serif;
 transition: all 0.2s;
 }
 .steam-code-copy:hover {
 background: rgba(102,192,244,0.15);
 }
 .steam-instructions {
 font-size: 12px;
 color: #8f9bb3;
 line-height: 1.6;
 margin: 10px 0;
 padding: 10px 12px;
 border-radius: 8px;
 background: rgba(0,0,0,0.2);
 }
 .steam-instructions ol {
 margin: 0;
 padding-left: 18px;
 }
 .steam-instructions li {
 margin-bottom: 4px;
 }
 .steam-instructions a {
 color: #66c0f4;
 text-decoration: none;
 }
 .steam-instructions a:hover {
 text-decoration: underline;
 }
 .steam-status-badge {
 display: inline-flex;
 align-items: center;
 gap: 5px;
 padding: 3px 10px;
 border-radius: 20px;
 font-size: 12px;
 font-weight: 500;
 }
 .steam-status-badge.verified {
 background: rgba(76, 175, 80, 0.15);
 color: #4caf50;
 border: 1px solid rgba(76, 175, 80, 0.3);
 }
 .steam-status-badge.unverified {
 background: rgba(255, 152, 0, 0.15);
 color: #ff9800;
 border: 1px solid rgba(255, 152, 0, 0.3);
 }
 .steam-status-badge .material-symbols-outlined {
 font-size: 14px;
 }
 .steam-verify-hidden {
 display: none;
 }
 .steam-link-display {
 font-family: 'Inter', sans-serif;
 font-size: 13px;
 color: #66c0f4;
 text-decoration: none;
 }
 .steam-link-display:hover {
 text-decoration: underline;
 }
 .steam-verify-success-msg {
 display: none;
 padding: 10px 14px;
 border-radius: 8px;
 background: rgba(76, 175, 80, 0.1);
 border: 1px solid rgba(76, 175, 80, 0.25);
 color: #4caf50;
 font-size: 13px;
 margin-top: 10px;
 align-items: center;
 gap: 8px;
 }
 .steam-verify-success-msg.show {
 display: flex;
 }
 .steam-verify-success-msg .material-symbols-outlined {
 font-size: 18px;
 }

/* === Achievements Section === */
 .ach-section {
 padding: 20px 24px;
 border-top: 1px solid rgba(255,255,255,0.08);
 }
 .ach-header {
 display: flex;
 align-items: center;
 gap: 8px;
 font-size: 16px;
 font-weight: 600;
 color: #e0e6f0;
 margin-bottom: 16px;
 }
 .ach-header .material-symbols-outlined {
 font-size: 22px;
 color: #66c0f4;
 }
 .ach-grid {
 display: flex;
 flex-wrap: wrap;
 gap: 12px;
 }
 .ach-item {
 position: relative;
 cursor: pointer;
 transition: transform 0.2s ease;
 }
 .ach-item:hover {
 transform: scale(1.08);
 }
 .ach-item img {
 width: 70px;
 height: 70px;
 object-fit: cover;
 border-radius: 10px;
 border: 2px solid rgba(255,255,255,0.15);
 display: block;
 }
 
 .ach-delete-btn {
 position: absolute;
 top: -4px;
 right: -4px;
 width: 18px;
 height: 18px;
 border-radius: 50%;
 background: #dc2626;
 color: #fff;
 border: none;
 font-size: 12px;
 line-height: 18px;
 text-align: center;
 cursor: pointer;
 display: none;
 z-index: 10;
 padding: 0;
 }
 .ach-item:hover .ach-delete-btn {
 display: block;
 }

 .ach-tooltip {
 position: absolute;
 bottom: calc(100% + 12px);
 left: 50%;
 transform: translateX(-50%) translateY(8px) scale(0.8);
 opacity: 0;
 background: #1a1a2e;
 color: #fff;
 padding: 12px 16px;
 border-radius: 12px;
 font-size: 13px;
 line-height: 1.5;
 max-width: 260px;
 min-width: 160px;
 box-shadow: 0 6px 20px rgba(0,0,0,0.6);
 pointer-events: none;
 z-index: 100;
 transition: all 0.35s cubic-bezier(0.175, 0.885, 0.32, 1.275);
 white-space: normal;
 text-align: center;
 }
 .ach-tooltip::after {
 content: '';
 position: absolute;
 top: 100%;
 left: 50%;
 transform: translateX(-50%);
 border: 7px solid transparent;
 border-top-color: #1a1a2e;
 }
 .ach-item.active .ach-tooltip {
 transform: translateX(-50%) translateY(0) scale(1);
 opacity: 1;
 }
 .ach-tooltip .ach-title {
 display: block;
 font-weight: 700;
 color: #66c0f4;
 margin-bottom: 4px;
 font-size: 14px;
 }
 .ach-empty {
 color: #6b7280;
 font-size: 13px;
 font-style: italic;
 }

 /* === Admin Panel === */
 .ach-admin-btn {
 display: inline-flex;
 align-items: center;
 gap: 6px;
 margin-top: 16px;
 padding: 8px 16px;
 background: rgba(102,192,244,0.1);
 border: 1px solid rgba(102,192,244,0.3);
 color: #66c0f4;
 border-radius: 8px;
 cursor: pointer;
 font-size: 13px;
 font-weight: 500;
 font-family: 'Inter', sans-serif;
 transition: all 0.2s;
 }
 .ach-admin-btn:hover {
 background: rgba(102,192,244,0.2);
 }
 .ach-admin-panel {
 display: none;
 margin-top: 16px;
 padding: 16px;
 background: rgba(0,0,0,0.3);
 border-radius: 12px;
 border: 1px dashed rgba(102,192,244,0.25);
 }
 .ach-admin-panel.visible {
 display: block;
 }
 .ach-admin-panel h4 {
 margin: 0 0 12px 0;
 color: #e0e6f0;
 font-size: 14px;
 }
 .ach-img-picker {
 display: flex;
 flex-wrap: wrap;
 gap: 8px;
 margin-bottom: 12px;
 }
 .ach-img-option {
 width: 56px;
 height: 56px;
 border-radius: 8px;
 border: 3px solid transparent;
 cursor: pointer;
 object-fit: cover;
 transition: all 0.2s;
 }
 .ach-img-option:hover {
 border-color: rgba(102,192,244,0.5);
 transform: scale(1.1);
 }
 .ach-img-option.selected {
 border-color: #66c0f4;
 box-shadow: 0 0 12px rgba(102,192,244,0.4);
 }
 .ach-admin-input {
 width: 100%;
 box-sizing: border-box;
 padding: 8px 12px;
 margin-bottom: 10px;
 border-radius: 8px;
 border: 1px solid rgba(255,255,255,0.12);
 background: rgba(0,0,0,0.3);
 color: #e0e6f0;
 font-size: 13px;
 font-family: 'Inter', sans-serif;
 outline: none;
 }
 .ach-admin-input:focus {
 border-color: #66c0f4;
 }
 .ach-admin-input::placeholder {
 color: #5a6378;
 }
 .ach-add-btn {
 padding: 10px 20px;
 border-radius: 8px;
 border: none;
 background: linear-gradient(135deg, #1b2838, #2a475e);
 color: #c7d0e0;
 font-size: 13px;
 font-weight: 600;
 cursor: pointer;
 font-family: 'Inter', sans-serif;
 transition: all 0.2s;
 }
 .ach-add-btn:hover {
 background: linear-gradient(135deg, #2a475e, #66c0f4);
 color: #fff;
 }
</style>


<!-- ===================== HTML ===================== -->
<!-- === ACHIEVEMENTS SECTION === -->
 <div class="ach-section">
 <div class="ach-header">
 <span class="material-symbols-outlined">military_tech</span>
 Достижения
 </div>
 <div class="ach-grid" id="achGrid">
 <div class="ach-empty" id="achEmpty">Достижений пока нет</div>
 </div>
 <?if($GROUP_ID$ = '4')?>
 <button class="ach-admin-btn" onclick="achToggleAdmin()">
 <span class="material-symbols-outlined" style="font-size:16px;">add_circle</span>
 Добавить достижение
 </button>
 <div class="ach-admin-panel" id="achAdminPanel">
 <h4>Выберите картинку достижения:</h4>
 <div class="ach-img-picker" id="achImgPicker">
 <img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_2-fotor-bg-remover-20260926224846.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_2-fotor-bg-remover-20260926224846.png')" alt="Достижение 1">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_8-fotor-bg-remover-20260926224924.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_8-fotor-bg-remover-20260926224924.png')" alt="Достижение 2">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_4-fotor-bg-remover-2026092622505.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_4-fotor-bg-remover-2026092622505.png')" alt="Достижение 3">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/2de846dbc4a11f1ac4d768cfd41a853_1.jpeg" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/2de846dbc4a11f1ac4d768cfd41a853_1.jpeg')" alt="Достижение 4">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_4-fotor-bg-remover-20260926223859.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_4-fotor-bg-remover-20260926223859.png')" alt="Достижение 5">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_9-fotor-bg-remover-2026092615118.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_9-fotor-bg-remover-2026092615118.png')" alt="Достижение 6">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_7-fotor-bg-remover-2026092615157.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_7-fotor-bg-remover-2026092615157.png')" alt="Достижение 7">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_15-fotor-bg-remover-202609304119.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_15-fotor-bg-remover-202609304119.png')" alt="Достижение 8">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/osen-fotor-bg-remover-2026092603655.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/osen-fotor-bg-remover-2026092603655.png')" alt="Достижение 9">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_3-fotor-bg-remover-2026092622425.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_3-fotor-bg-remover-2026092622425.png')" alt="Достижение 10">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_7-fotor-bg-remover-20260926224621.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_7-fotor-bg-remover-20260926224621.png')" alt="Достижение 11">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/1_kusok_chak_chak-fotor-bg-remover-20260929235845.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/1_kusok_chak_chak-fotor-bg-remover-20260929235845.png')" alt="Достижение 12">
<img class="ach-img-option" src="https://4ak4ak.moy.su/dostizhenia/Screenshot_1.png" onclick="achSelectImg(this, 'https://4ak4ak.moy.su/dostizhenia/Screenshot_1.png')" alt="Достижение 13">

 </div>
 <input type="hidden" id="achSelectedImg" value="">
 <input type="text" class="ach-admin-input" id="achTitle" placeholder="Название достижения (например: Легенда)">
 <input type="text" class="ach-admin-input" id="achDesc" placeholder="За что выдано (например: За 1000 часов в игре)">
 <button class="ach-add-btn" onclick="achAdd()">Добавить достижение</button>
 <button class="ach-admin-btn" style="margin-left:8px;" onclick="achToggleAdmin()">Отмена</button>
 </div>
 <?endif?>
 </div>
 <!-- === END ACHIEVEMENTS SECTION === -->

<!-- === STEAM VERIFICATION BLOCK === -->
 <div class="steam-verify-block" id="steamVerifyBlock">
 <div class="steam-verify-title">
 <span class="material-symbols-outlined">stadia_controller</span>
 Steam ID — Верификация профиля
 </div>

 <!-- Row: Steam ID input + status -->
 <div class="steam-verify-row">
 <label>Steam ID:</label>
 <input type="text" class="steam-verify-input" id="steamIdInput"
 placeholder="Например: 76561198012345678 или STEAM_0:1:2345678"
 value="">
 <button class="steam-verify-btn" id="steamSaveBtn" onclick="steamSaveId()">Сохранить</button>
 </div>

 <!-- Status badge -->
 <div class="steam-verify-row" id="steamStatusRow" style="display:none;">
 <label>Статус:</label>
 <span class="steam-status-badge unverified" id="steamStatusBadge">
 <span class="material-symbols-outlined">pending</span>
 <span id="steamStatusText">Не подтверждён</span>
 </span>
 <?if($_IS_OWN_PROFILE$)?><button class="steam-verify-btn" style="background:rgba(255,255,255,0.05); color:#8f9bb3;" onclick="steamShowVerifyPanel()">Подтвердить</button><?endif?>
 </div>

 <!-- Verified link display (shown when verified) -->
 <div class="steam-verify-row" id="steamVerifiedRow" style="display:none;">
 <label>Steam:</label>
 <a href="" id="steamProfileLink" class="steam-link-display" target="_blank"></a>
 <span class="steam-status-badge verified">
 <span class="material-symbols-outlined">check_circle</span>
 Подтверждён
 </span>
 </div>

 <!-- Verification panel (shown after entering Steam ID) -->
 <div id="steamVerifyPanel" class="steam-verify-hidden">
 <div class="steam-code-display">
 <span class="steam-code-text" id="steamVerifyCode">APEX-XXXX-XXXX</span>
 <button class="steam-code-copy" onclick="steamCopyCode()">Копировать</button>
 </div>
 <div class="steam-instructions">
 <b>Как подтвердить Steam ID:</b>
 <ol>
 <li>Скопируйте код выше</li>
 <li>Откройте <a href="https://steamcommunity.com/profiles/me/edit" target="_blank">настройки профиля Steam</a></li>
 <li>Вставьте код в поле «О себе» (Summary)</li>
 <li>Сохраните профиль Steam</li>
 <li>Нажмите кнопку «Я вставил код» ниже</li>
 </ol>
 </div>
 <button class="steam-verify-btn" onclick="steamConfirmVerify()" id="steamConfirmBtn">Я вставил код</button>
 <button class="steam-verify-btn" style="background:rgba(255,255,255,0.05); color:#8f9bb3;" onclick="steamHideVerifyPanel()">Отмена</button>
 <div class="steam-verify-success-msg" id="steamSuccessMsg">
 <span class="material-symbols-outlined">check_circle</span>
 <span>Steam ID успешно подтверждён! Теперь код можно удалить из профиля Steam.</span>
 </div>
 </div>
 </div>
 <!-- === END STEAM VERIFICATION BLOCK === -->

<!-- ===================== FIREBASE SDK ===================== -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-database-compat.js"></script>


<!-- ===================== JAVASCRIPT ===================== -->
<script>
// ====================================================================
// FIREBASE INIT
// ====================================================================
var firebaseConfig = {
  apiKey: "AIzaSyCNQ0WFAiQjnISQjXJnHoln-wI64G2BqWs",
  authDomain: "ak4ak-d948e.firebaseapp.com",
  databaseURL: "https://ak4ak-d948e-default-rtdb.firebaseio.com",
  projectId: "ak4ak-d948e",
  storageBucket: "ak4ak-d948e.firebasestorage.app",
  messagingSenderId: "787151252619",
  appId: "1:787151252619:web:05eff65dc74b01d6e8f88e",
  measurementId: "G-DBB4YBNF2Q"
};
firebase.initializeApp(firebaseConfig);
var db = firebase.database();

// ====================================================================
// ПЕРЕМЕННЫЕ UCOZ
// ====================================================================
var profileUserId = '$_USER_ID$';
var profileUserName = '$USERNAME$';
var isOwnProfile = '<?if($_IS_OWN_PROFILE$)?>1<?else?>0<?endif?>' === '1';
var achIsAdmin = '<?if($GROUP_ID$="4")?>1<?else?>0<?endif?>' === '1';
var BACKEND_URL = 'https://steam-verify-backend.onrender.com';


// ====================================================================
// ДОСТИЖЕНИЯ — Firebase Realtime Database
// Путь: achievements/$_USER_ID$
// Структура: [ { img, title, desc, addedAt }, ... ]
// ====================================================================
(function() {
  var selectedImgUrl = '';
  var achRef = db.ref('achievements/' + profileUserId);

  window.addEventListener('DOMContentLoaded', function() {
    achRef.on('value', function(snapshot) {
      achRender(snapshot.val() || []);
    }, function(err) {
      console.error('Firebase achievements error:', err);
    });
  });

  function achSaveData(data) {
    // Сохраняем весь массив достижений в Firebase
    achRef.set(data);
  }

  function achGetData(callback) {
    achRef.once('value', function(snapshot) {
      callback(snapshot.val() || []);
    });
  }

  function achRender(data) {
    // data может быть объектом или массивом — нормализуем
    var items = [];
    if (Array.isArray(data)) {
      items = data;
    } else if (data && typeof data === 'object') {
      Object.keys(data).forEach(function(key) {
        items.push(data[key]);
      });
    }

    var grid = document.getElementById('achGrid');
    var empty = document.getElementById('achEmpty');
    if (!grid) return;

    if (items.length === 0) {
      if (empty) empty.style.display = 'block';
      grid.innerHTML = '';
      return;
    }
    if (empty) empty.style.display = 'none';
    grid.innerHTML = '';

    items.forEach(function(item, index) {
      var div = document.createElement('div');
      div.className = 'ach-item';
      div.onclick = function() { achToggleTooltip(this); };

      var deleteBtn = '';
      if (achIsAdmin) {
        deleteBtn = '<button class="ach-delete-btn" onclick="achDelete(' + index + '); event.stopPropagation();" title="Удалить">&times;</button>';
      }

      div.innerHTML = '<img src="' + (item.img || '') + '" alt="' + (item.title || '') + '">' +
        deleteBtn +
        '<div class="ach-tooltip">' +
        '<span class="ach-title">' + (item.title || '') + '</span>' +
        (item.desc || '') +
        '</div>';
      grid.appendChild(div);
    });
  }

  window.achToggleTooltip = function(el) {
    document.querySelectorAll('.ach-item').forEach(function(item) {
      if (item !== el) item.classList.remove('active');
    });
    el.classList.toggle('active');
  };

  window.achToggleAdmin = function() {
    var panel = document.getElementById('achAdminPanel');
    panel.classList.toggle('visible');
  };

  window.achSelectImg = function(el, url) {
    selectedImgUrl = url;
    document.querySelectorAll('.ach-img-option').forEach(function(opt) {
      opt.classList.remove('selected');
    });
    el.classList.add('selected');
    document.getElementById('achSelectedImg').value = url;
  };

  window.achAdd = function() {
    var img = document.getElementById('achSelectedImg').value;
    var title = document.getElementById('achTitle').value.trim();
    var desc = document.getElementById('achDesc').value.trim();

    if (!img) {
      alert('Выберите картинку достижения!');
      return;
    }
    if (!title) {
      alert('Введите название достижения!');
      return;
    }

    var newItem = {
      img: img,
      title: title,
      desc: desc,
      addedAt: Date.now()
    };

    // Читаем текущий массив, добавляем, сохраняем
    achGetData(function(data) {
      data.push(newItem);
      achSaveData(data);
    });

    // Сброс формы
    document.getElementById('achTitle').value = '';
    document.getElementById('achDesc').value = '';
    document.getElementById('achSelectedImg').value = '';
    selectedImgUrl = '';
    document.querySelectorAll('.ach-img-option').forEach(function(opt) {
      opt.classList.remove('selected');
    });
    document.getElementById('achAdminPanel').classList.remove('visible');
  };

  window.achDelete = function(index) {
    if (!confirm('Удалить это достижение?')) return;
    achGetData(function(data) {
      data.splice(index, 1);
      achSaveData(data);
    });
  };

  // Закрытие тултипа по клику вне
  document.addEventListener('click', function(e) {
    if (!e.target.closest('.ach-item')) {
      document.querySelectorAll('.ach-item').forEach(function(item) {
        item.classList.remove('active');
      });
    }
  });
})();


// ====================================================================
// STEAM ID ВЕРИФИКАЦИЯ — Firebase + бэкенд steam-verify-backend.onrender.com
// Путь в Firebase: steamIds/$_USER_ID$
// Структура: { steamId, verified, verifyCode, username, userId, savedAt, verifiedAt }
// ====================================================================
(function() {
  var steamRef = db.ref('steamIds/' + profileUserId);

  window.addEventListener('DOMContentLoaded', function() {
    // Слушаем изменения в реальном времени
    steamRef.on('value', function(snapshot) {
      var data = snapshot.val();
      steamRender(data);
    }, function(err) {
      console.error('Firebase steamIds error:', err);
    });
  });

  function generateVerifyCode() {
    var part1 = Math.random().toString(36).substring(2, 7).toUpperCase();
    var part2 = Math.random().toString(36).substring(2, 7).toUpperCase();
    return 'APEX-' + part1 + '-' + part2;
  }

  function getSteamProfileUrl(steamId) {
    steamId = steamId.trim();
    if (steamId.indexOf('STEAM_') === 0) {
      var parts = steamId.split(':');
      if (parts.length === 3) {
        var accountId = parseInt(parts[2]) * 2 + parseInt(parts[1]);
        var base = 76561197960265728;
        if (typeof BigInt !== 'undefined') {
          var result = BigInt(base) + BigInt(accountId);
          return 'https://steamcommunity.com/profiles/' + result.toString();
        } else {
          return 'https://steamcommunity.com/profiles/' + (base + accountId);
        }
      }
    }
    if (/^\d{17}$/.test(steamId)) {
      return 'https://steamcommunity.com/profiles/' + steamId;
    }
    return 'https://steamcommunity.com/profiles/' + steamId.replace(/[^a-zA-Z0-9_-]/g, '');
  }

  function steamRender(data) {
    if (!data) data = {};

    var input = document.getElementById('steamIdInput');
    var saveBtn = document.getElementById('steamSaveBtn');
    var statusRow = document.getElementById('steamStatusRow');
    var verifiedRow = document.getElementById('steamVerifiedRow');

    if (!input) return;

    // Заполняем инпут
    if (data.steamId) {
      input.value = data.steamId;
    }

    // Скрываем элементы управления для чужого профиля
    if (!isOwnProfile) {
      input.readOnly = true;
      if (saveBtn) saveBtn.style.display = 'none';
    }

    if (data.verified && data.steamId) {
      // Подтверждён
      statusRow.style.display = 'none';
      verifiedRow.style.display = 'flex';
      var link = document.getElementById('steamProfileLink');
      link.href = getSteamProfileUrl(data.steamId);
      link.textContent = data.steamId;
    } else if (data.steamId) {
      // Сохранён, но не подтверждён
      statusRow.style.display = 'flex';
      verifiedRow.style.display = 'none';

      var badge = document.getElementById('steamStatusBadge');
      badge.className = 'steam-status-badge unverified';
      badge.innerHTML = '<span class="material-symbols-outlined">pending</span><span id="steamStatusText">Не подтверждён</span>';
    } else {
      // Нет данных
      statusRow.style.display = 'none';
      verifiedRow.style.display = 'none';
    }
  }

  // Сохранение Steam ID в Firebase
  window.steamSaveId = function() {
    var input = document.getElementById('steamIdInput');
    var steamId = input.value.trim();
    if (!steamId) {
      alert('Введите Steam ID');
      return;
    }

    var verifyCode = generateVerifyCode();

    steamRef.set({
      steamId: steamId,
      verified: false,
      verifyCode: verifyCode,
      username: profileUserName,
      userId: profileUserId,
      savedAt: firebase.database.ServerValue.TIMESTAMP
    });

    // Показываем панель верификации
    document.getElementById('steamVerifyCode').textContent = verifyCode;
    document.getElementById('steamSuccessMsg').classList.remove('show');
    document.getElementById('steamVerifyPanel').classList.remove('steam-verify-hidden');
  };

  window.steamShowVerifyPanel = function() {
    steamRef.once('value', function(snapshot) {
      var data = snapshot.val() || {};
      var verifyCode = data.verifyCode;

      if (!verifyCode) {
        verifyCode = generateVerifyCode();
        steamRef.update({ verifyCode: verifyCode });
      }

      document.getElementById('steamVerifyCode').textContent = verifyCode;
      document.getElementById('steamSuccessMsg').classList.remove('show');
      document.getElementById('steamVerifyPanel').classList.remove('steam-verify-hidden');
    });
  };

  window.steamHideVerifyPanel = function() {
    document.getElementById('steamVerifyPanel').classList.add('steam-verify-hidden');
  };

  window.steamCopyCode = function() {
    var code = document.getElementById('steamVerifyCode').textContent;
    navigator.clipboard.writeText(code).then(function() {
      var btn = document.querySelector('.steam-code-copy');
      var origText = btn.textContent;
      btn.textContent = 'Скопировано!';
      setTimeout(function() { btn.textContent = origText; }, 2000);
    }).catch(function() {
      var ta = document.createElement('textarea');
      ta.value = code;
      document.body.appendChild(ta);
      ta.select();
      document.execCommand('copy');
      document.body.removeChild(ta);
      alert('Код скопирован: ' + code);
    });
  };

  // Подтверждение через бэкенд steam-verify-backend.onrender.com
  window.steamConfirmVerify = function() {
    steamRef.once('value', function(snapshot) {
      var data = snapshot.val();
      if (!data || !data.steamId || !data.verifyCode) {
        alert('Сначала сохраните Steam ID');
        return;
      }

      var btn = document.getElementById('steamConfirmBtn');
      var originalText = btn.textContent;
      btn.textContent = 'Проверяем...';
      btn.disabled = true;

      // Запрос к бэкенду на Render
      fetch(BACKEND_URL + '/verify', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          steamId: data.steamId,
          code: data.verifyCode
        })
      })
      .then(function(response) { return response.json(); })
      .then(function(result) {
        btn.textContent = originalText;
        btn.disabled = false;

        if (result.verified === true) {
          // Бэкенд подтвердил — пишем в Firebase
          steamRef.update({
            verified: true,
            verifiedAt: firebase.database.ServerValue.TIMESTAMP
          });

          document.getElementById('steamSuccessMsg').classList.add('show');
          document.getElementById('steamConfirmBtn').style.display = 'none';

          setTimeout(function() {
            steamHideVerifyPanel();
            document.getElementById('steamConfirmBtn').style.display = '';
          }, 3000);
        } else {
          // Бэкенд не нашёл код
          alert('Код не найден в профиле Steam. Убедитесь, что вы вставили код в поле «О себе» и сохранили профиль. ' + (result.message || ''));
        }
      })
      .catch(function(err) {
        btn.textContent = originalText;
        btn.disabled = false;
        console.error('Backend error:', err);
        // Если бэкенд недоступен — fallback на ручное подтверждение
        if (confirm('Бэкенд недоступен. Подтвердить вручную? (только для теста)')) {
          steamRef.update({
            verified: true,
            verifiedAt: firebase.database.ServerValue.TIMESTAMP
          });
          document.getElementById('steamSuccessMsg').classList.add('show');
          document.getElementById('steamConfirmBtn').style.display = 'none';
          setTimeout(function() {
            steamHideVerifyPanel();
            document.getElementById('steamConfirmBtn').style.display = '';
          }, 3000);
        }
      });
    });
  };
})();
</script>
