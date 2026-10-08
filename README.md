<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Steam ID — Верификация</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    font-family: 'Inter', sans-serif;
    background: transparent;
    color: #e0e6f0;
  }

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
  .steam-verify-input:focus { border-color: #66c0f4; }
  .steam-verify-input::placeholder { color: #5a6378; }
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
  .steam-verify-btn:disabled { opacity: 0.5; cursor: not-allowed; }
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
      placeholder="Например: 76561198012345678 или STEAM_0:1:2345678" value="">
    <button class="steam-verify-btn" id="steamSaveBtn" onclick="steamSaveId()">Сохранить</button>
  </div>

  <!-- Status badge -->
  <div class="steam-verify-row" id="steamStatusRow" style="display:none;">
    <label>Статус:</label>
    <span class="steam-status-badge unverified" id="steamStatusBadge">
      <span class="material-symbols-outlined">pending</span>
      <span id="steamStatusText">Не подтверждён</span>
    </span>
    <button class="steam-verify-btn" style="background:rgba(255,255,255,0.05); color:#8f9bb3;" onclick="steamShowVerifyPanel()">Подтвердить</button>
  </div>

  <!-- Verified link display -->
  <div class="steam-verify-row" id="steamVerifiedRow" style="display:none;">
    <label>Steam:</label>
    <a href="" id="steamProfileLink" class="steam-link-display" target="_blank"></a>
    <span class="steam-status-badge verified">
      <span class="material-symbols-outlined">check_circle</span>
      Подтверждён
    </span>
  </div>

  <!-- Verification panel -->
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

<!-- Firebase SDK -->
<script type="module">
import { initializeApp } from 'https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js';
import { getDatabase, ref, get, set, update, onValue } from 'https://www.gstatic.com/firebasejs/10.12.0/firebase-database.js';

const firebaseConfig = {
  databaseURL: 'https://ak4ak-d948e-default-rtdb.firebaseio.com/'
};

const app = initializeApp(firebaseConfig);
const db = getDatabase(app);

// Получаем userId из URL (?uid=12345) или из postMessage
const urlParams = new URLSearchParams(window.location.search);
let profileUserId = urlParams.get('uid') || '';

// Если uid не передан в URL — ждём postMessage от родительского окна
if (!profileUserId) {
  window.addEventListener('message', function(event) {
    if (event.data && event.data.type === 'setUserId' && event.data.uid) {
      profileUserId = event.data.uid;
      initSteam();
    }
  });
  // Просим родителя отправить uid
  window.parent.postMessage({ type: 'requestUserId' }, '*');
} else {
  initSteam();
}

const BACKEND_URL = 'https://steam-verify-backend.onrender.com';

function initSteam() {
  if (!profileUserId) return;
  loadSteamData();
}

function getSteamRef() {
  return ref(db, 'steamVerification/' + profileUserId);
}

function loadSteamData() {
  if (!profileUserId) return;
  onValue(getSteamRef(), function(snapshot) {
    const data = snapshot.val() || { steamId: '', verified: false, verifyCode: '' };
    applySteamData(data);
  }, function(error) {
    console.error('Firebase error:', error);
  });
}

function applySteamData(data) {
  if (data.steamId) {
    document.getElementById('steamIdInput').value = data.steamId;
    document.getElementById('steamStatusRow').style.display = 'flex';

    if (data.verified) {
      showVerifiedState(data.steamId);
    } else {
      showUnverifiedState();
    }
  } else {
    document.getElementById('steamIdInput').value = '';
    document.getElementById('steamStatusRow').style.display = 'none';
    document.getElementById('steamVerifiedRow').style.display = 'none';
  }
}

function saveSteamData(data) {
  if (!profileUserId) return Promise.resolve();
  return set(getSteamRef(), data);
}

function generateVerifyCode() {
  const part1 = Math.random().toString(36).substring(2, 7).toUpperCase();
  const part2 = Math.random().toString(36).substring(2, 7).toUpperCase();
  return 'APEX-' + part1 + '-' + part2;
}

function getSteamProfileUrl(steamId) {
  steamId = steamId.trim();
  if (steamId.indexOf('STEAM_') === 0) {
    const parts = steamId.split(':');
    if (parts.length === 3) {
      const accountId = parseInt(parts[2]) * 2 + parseInt(parts[1]);
      const base = 76561197960265728;
      if (typeof BigInt !== 'undefined') {
        const result = BigInt(base) + BigInt(accountId);
        return 'https://steamcommunity.com/profiles/' + result.toString();
      } else {
        const result2 = base + accountId;
        return 'https://steamcommunity.com/profiles/' + result2;
      }
    }
  }
  if (/^\d{17}$/.test(steamId)) {
    return 'https://steamcommunity.com/profiles/' + steamId;
  }
  return 'https://steamcommunity.com/profiles/' + steamId.replace(/[^a-zA-Z0-9_-]/g, '');
}

// === Глобальные функции для onclick ===
window.steamSaveId = function() {
  const input = document.getElementById('steamIdInput');
  const steamId = input.value.trim();
  if (!steamId) { alert('Введите Steam ID'); return; }

  const data = { steamId: steamId, verified: false, verifyCode: '' };
  saveSteamData(data).then(function() {
    document.getElementById('steamStatusRow').style.display = 'flex';
    showUnverifiedState();
    steamShowVerifyPanel();
  });
};

window.steamShowVerifyPanel = function() {
  getSteamRef().get().then(function(snapshot) {
    let data = snapshot.val() || { steamId: '', verified: false, verifyCode: '' };
    if (!data.verifyCode) {
      data.verifyCode = generateVerifyCode();
      set(getSteamRef(), data);
    }
    document.getElementById('steamVerifyCode').textContent = data.verifyCode;
    document.getElementById('steamSuccessMsg').classList.remove('show');
    document.getElementById('steamVerifyPanel').classList.remove('steam-verify-hidden');
  });
};

window.steamHideVerifyPanel = function() {
  document.getElementById('steamVerifyPanel').classList.add('steam-verify-hidden');
};

window.steamCopyCode = function() {
  const code = document.getElementById('steamVerifyCode').textContent;
  navigator.clipboard.writeText(code).then(function() {
    const btn = document.querySelector('.steam-code-copy');
    const origText = btn.textContent;
    btn.textContent = 'Скопировано!';
    setTimeout(function() { btn.textContent = origText; }, 2000);
  }).catch(function() {
    const ta = document.createElement('textarea');
    ta.value = code;
    document.body.appendChild(ta);
    ta.select();
    document.execCommand('copy');
    document.body.removeChild(ta);
    alert('Код скопирован: ' + code);
  });
};

window.steamConfirmVerify = function() {
  if (!profileUserId) { alert('Не определён пользователь'); return; }

  getSteamRef().get().then(function(snapshot) {
    const data = snapshot.val();
    if (!data || !data.steamId || !data.verifyCode) {
      alert('Сначала сохраните Steam ID');
      return;
    }

    const btn = document.getElementById('steamConfirmBtn');
    btn.disabled = true;
    btn.textContent = 'Проверка...';

    // Запрос к бэкенду для проверки кода в профиле Steam
    fetch(BACKEND_URL + '/verify', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        steamId: data.steamId,
        code: data.verifyCode
      })
    })
    .then(function(res) { return res.json(); })
    .then(function(result) {
      btn.disabled = false;
      btn.textContent = 'Я вставил код';

      if (result.verified) {
        update(getSteamRef(), { verified: true });
        showVerifiedState(data.steamId);
        document.getElementById('steamSuccessMsg').classList.add('show');
        btn.style.display = 'none';
        setTimeout(function() {
          steamHideVerifyPanel();
          btn.style.display = '';
        }, 3000);
      } else {
        alert('Код не найден в профиле Steam. Убедитесь, что вы вставили код в поле «О себе» и сохранили профиль.');
      }
    })
    .catch(function(err) {
      btn.disabled = false;
      btn.textContent = 'Я вставил код';
      console.error('Backend error:', err);
      // Fallback: верификация без бэкенда (для теста)
      if (confirm('Бэкенд недоступен. Подтвердить без проверки кода?')) {
        update(getSteamRef(), { verified: true });
        showVerifiedState(data.steamId);
        document.getElementById('steamSuccessMsg').classList.add('show');
        btn.style.display = 'none';
        setTimeout(function() {
          steamHideVerifyPanel();
          btn.style.display = '';
        }, 3000);
      }
    });
  });
};

function showVerifiedState(steamId) {
  document.getElementById('steamStatusRow').style.display = 'none';
  document.getElementById('steamVerifiedRow').style.display = 'flex';
  const link = document.getElementById('steamProfileLink');
  link.href = getSteamProfileUrl(steamId);
  link.textContent = steamId;
}

function showUnverifiedState() {
  document.getElementById('steamStatusRow').style.display = 'flex';
  document.getElementById('steamVerifiedRow').style.display = 'none';
  const badge = document.getElementById('steamStatusBadge');
  badge.className = 'steam-status-badge unverified';
  badge.innerHTML = '<span class="material-symbols-outlined">pending</span><span id="steamStatusText">Не подтверждён</span>';
}
</script>

</body>
</html>
