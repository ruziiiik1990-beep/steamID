<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Steam ID</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
 body {
    overflow: hidden; /* Убирает все системные ползунки гитхаба */
}

 * { margin: 0; padding: 0; box-sizing: border-box; }
 html, body { overflow: hidden; }
 body {
   font-family: 'Inter', sans-serif;
   background: transparent;
   color: #e0e6f0;
 }

 /* === Profile Table (как на странице пользователя) === */
 .profile-table-wrapper {
   max-width: 900px;
   margin: 0 auto;
   background: #374151;
   border-radius: 16px;
   box-shadow: 0 8px 32px rgba(0,0,0,0.4);
   overflow: hidden;
 }
 .profile-body { padding: 0 24px; }

 .profile-section {
   background: transparent;
   padding: 20px 0;
   border-top: 1px solid rgba(255,255,255,0.08);
 }
 .profile-section:first-child { border-top: none; }

 .profile-section-name {
   font-size: 16px;
   font-weight: 600;
   color: #e0e6f0;
   margin-bottom: 16px;
   display: flex;
   align-items: center;
   gap: 8px;
 }
 .profile-section-name .material-symbols-outlined {
   font-size: 22px;
   color: #66c0f4;
 }
 .profile-section-content {
   color: #c7d0e0;
   font-size: 14px;
   line-height: 1.6;
 }

 /* === Steam Verification внутри profile-section === */
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
 .steam-verify-input:focus { border-color: #66c0f4; }
 .steam-verify-input::placeholder { color: #5a6378; }
 .steam-verify-input:read-only { opacity: 0.7; }

 .profile-label {
   display: inline-flex;
   align-items: center;
   gap: 6px;
   padding: 8px 16px;
   background: rgba(102,192,244,0.1);
   border: 1px solid rgba(102,192,244,0.3);
   color: #66c0f4;
   border-radius: 8px;
   cursor: pointer;
   font-size: 13px;
   font-weight: 500;
   font-family: 'Inter', sans-serif;
   text-decoration: none;
   transition: all 0.2s;
   white-space: nowrap;
 }
 .profile-label:hover { background: rgba(102,192,244,0.2); }
 .profile-label .material-symbols-outlined { font-size: 16px; }

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
 .steam-code-copy:hover { background: rgba(102,192,244,0.15); }

 .steam-instructions {
   font-size: 12px;
   color: #8f9bb3;
   line-height: 1.6;
   margin: 10px 0;
   padding: 10px 12px;
   border-radius: 8px;
   background: rgba(0,0,0,0.2);
 }
 .steam-instructions ol { margin: 0; padding-left: 18px; }
 .steam-instructions li { margin-bottom: 4px; }
 .steam-instructions a { color: #66c0f4; text-decoration: none; }
 .steam-instructions a:hover { text-decoration: underline; }

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
 .steam-status-badge .material-symbols-outlined { font-size: 14px; }

 .steam-verify-hidden { display: none; }

 .steam-link-display {
   font-family: 'Inter', sans-serif;
   font-size: 13px;
   color: #66c0f4;
   text-decoration: none;
 }
 .steam-link-display:hover { text-decoration: underline; }

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
 .steam-verify-success-msg.show { display: flex; }
 .steam-verify-success-msg .material-symbols-outlined { font-size: 18px; }
</style>
</head>
<body>

<div class="profile-table-wrapper">
  <div class="profile-body">
    <div class="profile-section">
      <h3 class="profile-section-name">
        <span class="material-symbols-outlined">stadia_controller</span>
        Steam ID — Верификация профиля
      </h3>
      <div class="profile-section-content">

        <div class="steam-verify-row">
          <label>Steam ID:</label>
          <input type="text" class="steam-verify-input" id="steamIdInput"
            placeholder="Например: 76561198012345678 или STEAM_0:1:2345678" value="">
          <button class="profile-label" id="steamSaveBtn" onclick="steamSaveId()">
            <span class="material-symbols-outlined">save</span>Сохранить
          </button>
        </div>

        <div class="steam-verify-row" id="steamStatusRow" style="display:none;">
          <label>Статус:</label>
          <span class="steam-status-badge unverified" id="steamStatusBadge">
            <span class="material-symbols-outlined">pending</span>
            <span id="steamStatusText">Не подтверждён</span>
          </span>
          <button class="profile-label" id="steamVerifyBtn" onclick="steamShowVerifyPanel()">
            <span class="material-symbols-outlined">verified</span>Подтвердить
          </button>
        </div>

        <div class="steam-verify-row" id="steamVerifiedRow" style="display:none;">
          <label>Steam:</label>
          <a href="" id="steamProfileLink" class="steam-link-display" target="_blank"></a>
          <span class="steam-status-badge verified">
            <span class="material-symbols-outlined">check_circle</span>
            Подтверждён
          </span>
        </div>

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
          <button class="profile-label" onclick="steamConfirmVerify()" id="steamConfirmBtn">
            <span class="material-symbols-outlined">check_circle</span>Я вставил код
          </button>
          <button class="profile-label" style="background:rgba(255,255,255,0.05); color:#8f9bb3; border-color:rgba(255,255,255,0.1);" onclick="steamHideVerifyPanel()">Отмена</button>
          <div class="steam-verify-success-msg" id="steamSuccessMsg">
            <span class="material-symbols-outlined">check_circle</span>
            <span>Steam ID успешно подтверждён! Теперь код можно удалить из профиля Steam.</span>
          </div>
        </div>

      </div>
    </div>
  </div>
</div>

<script type="module">
import { initializeApp } from 'https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js';
import { getDatabase, ref, onValue, set, update } from 'https://www.gstatic.com/firebasejs/10.12.0/firebase-database.js';

const firebaseConfig = {
  databaseURL: 'https://ak4ak-d948e-default-rtdb.firebaseio.com/'
};
const app = initializeApp(firebaseConfig);
const db = getDatabase(app);

const params = new URLSearchParams(window.location.search);
const uid = params.get('uid') || 'guest';
const BACKEND_URL = 'https://steam-verify-backend.onrender.com';

function generateVerifyCode() {
  var p1 = Math.random().toString(36).substring(2, 7).toUpperCase();
  var p2 = Math.random().toString(36).substring(2, 7).toUpperCase();
  return 'APEX-' + p1 + '-' + p2;
}

function getSteamProfileUrl(steamId) {
  steamId = steamId.trim();
  if (steamId.indexOf('STEAM_') === 0) {
    var parts = steamId.split(':');
    if (parts.length === 3) {
      var accountId = parseInt(parts[2]) * 2 + parseInt(parts[1]);
      var base = 76561197960265728;
      if (typeof BigInt !== 'undefined') {
        return 'https://steamcommunity.com/profiles/' + (BigInt(base) + BigInt(accountId)).toString();
      }
      return 'https://steamcommunity.com/profiles/' + (base + accountId);
    }
  }
  if (/^\d{17}$/.test(steamId)) return 'https://steamcommunity.com/profiles/' + steamId;
  return 'https://steamcommunity.com/profiles/' + steamId.replace(/[^a-zA-Z0-9_-]/g, '');
}

function showVerifiedState(steamId) {
  document.getElementById('steamStatusRow').style.display = 'none';
  document.getElementById('steamVerifiedRow').style.display = 'flex';
  var link = document.getElementById('steamProfileLink');
  link.href = getSteamProfileUrl(steamId);
  link.textContent = steamId;
  document.getElementById('steamIdInput').readOnly = true;
  document.getElementById('steamSaveBtn').style.display = 'none';
  sendHeight();
}

function showUnverifiedState() {
  document.getElementById('steamStatusRow').style.display = 'flex';
  document.getElementById('steamVerifiedRow').style.display = 'none';
  var badge = document.getElementById('steamStatusBadge');
  badge.className = 'steam-status-badge unverified';
  badge.innerHTML = '<span class="material-symbols-outlined">pending</span><span id="steamStatusText">Не подтверждён</span>';
  sendHeight();
}

window.steamSaveId = function() {
  var steamId = document.getElementById('steamIdInput').value.trim();
  if (!steamId) { alert('Введите Steam ID'); return; }

  var dataRef = ref(db, 'steamVerification/' + uid);
  set(dataRef, {
    steamId: steamId,
    verified: false,
    verifyCode: generateVerifyCode(),
    timestamp: Date.now()
  }).then(function() {
    document.getElementById('steamStatusRow').style.display = 'flex';
    showUnverifiedState();
    steamShowVerifyPanel();
  }).catch(function(err) {
    alert('Ошибка сохранения: ' + err.message);
  });
};

window.steamShowVerifyPanel = function() {
  var dataRef = ref(db, 'steamVerification/' + uid);
  onValue(dataRef, function(snapshot) {
    var data = snapshot.val() || {};
    if (!data.verifyCode) {
      data.verifyCode = generateVerifyCode();
      update(dataRef, { verifyCode: data.verifyCode });
    }
    document.getElementById('steamVerifyCode').textContent = data.verifyCode;
    document.getElementById('steamSuccessMsg').classList.remove('show');
    document.getElementById('steamVerifyPanel').classList.remove('steam-verify-hidden');
    sendHeight();
  }, { onlyOnce: true });
};

window.steamHideVerifyPanel = function() {
  document.getElementById('steamVerifyPanel').classList.add('steam-verify-hidden');
  sendHeight();
};

window.steamCopyCode = function() {
  var code = document.getElementById('steamVerifyCode').textContent;
  navigator.clipboard.writeText(code).then(function() {
    var btn = document.querySelector('.steam-code-copy');
    var orig = btn.textContent;
    btn.textContent = 'Скопировано!';
    setTimeout(function() { btn.textContent = orig; }, 2000);
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

window.steamConfirmVerify = function() {
  var dataRef = ref(db, 'steamVerification/' + uid);
  onValue(dataRef, function(snapshot) {
    var data = snapshot.val() || {};
    if (!data.steamId || !data.verifyCode) {
      alert('Сначала сохраните Steam ID');
      return;
    }

    fetch(BACKEND_URL + '/verify', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({ steamId: data.steamId, code: data.verifyCode })
    })
    .then(function(r) { return r.json(); })
    .then(function(result) {
      if (result.verified) {
        update(dataRef, { verified: true }).then(function() {
          showVerifiedState(data.steamId);
          document.getElementById('steamSuccessMsg').classList.add('show');
          document.getElementById('steamConfirmBtn').style.display = 'none';
          setTimeout(function() {
            steamHideVerifyPanel();
            document.getElementById('steamConfirmBtn').style.display = '';
          }, 3000);
        });
      } else {
        alert('Код не найден в профиле Steam. Убедитесь, что вы вставили код в поле «О себе» и сохранили профиль.');
      }
    })
    .catch(function(err) {
      var confirmManual = confirm('Не удалось связаться с сервером верификации. Подтвердить вручную?');
      if (confirmManual) {
        update(dataRef, { verified: true }).then(function() {
          showVerifiedState(data.steamId);
          document.getElementById('steamSuccessMsg').classList.add('show');
          document.getElementById('steamConfirmBtn').style.display = 'none';
          setTimeout(function() {
            steamHideVerifyPanel();
            document.getElementById('steamConfirmBtn').style.display = '';
          }, 3000);
        });
      }
    });
  }, { onlyOnce: true });
};

onValue(ref(db, 'steamVerification/' + uid), function(snapshot) {
  var data = snapshot.val();
  if (data && data.steamId) {
    document.getElementById('steamIdInput').value = data.steamId;
    if (data.verified) {
      showVerifiedState(data.steamId);
    } else {
      document.getElementById('steamStatusRow').style.display = 'flex';
      showUnverifiedState();
    }
  }
  sendHeight();
});

function sendHeight() {
  var h = Math.max(
    document.body.scrollHeight,
    document.body.offsetHeight,
    document.documentElement.scrollHeight,
    document.documentElement.offsetHeight
  );
  window.parent.postMessage({ type: 'resize', frame: 'steam', height: h }, '*');
}

window.addEventListener('load', sendHeight);
setTimeout(sendHeight, 500);
setTimeout(sendHeight, 1500);
setTimeout(sendHeight, 3000);
if (window.ResizeObserver) { new ResizeObserver(sendHeight).observe(document.body); }
if (window.MutationObserver) {
  var observer = new MutationObserver(sendHeight);
  observer.observe(document.body, { childList: true, subtree: true, attributes: true });
}
</script>

</body>
</html>
