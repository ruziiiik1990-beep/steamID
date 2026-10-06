<!-- === STEAM ID — CSS === -->
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
</style>

<!-- === STEAM ID — HTML === -->
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

<!-- === STEAM VERIFICATION SCRIPT === -->
<!-- Firebase SDK -->
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.12.0/firebase-database-compat.js"></script>
<script>
(function() {
 var profileUserId = '$_USER_ID$';
 var profileUsername = '$_USERNAME$';
 var isOwnProfile = '<?if($_IS_OWN_PROFILE$)?>1<?else?>0<?endif?>' === '1';

 // Firebase config
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

 // Path in Firebase Realtime Database: steamIds / $_USER_ID$
 var steamRef = db.ref('steamIds/' + profileUserId);

 window.addEventListener('DOMContentLoaded', function() {
 loadSteamData();
 });

 // Load Steam data from Firebase (real-time)
 function loadSteamData() {
 steamRef.on('value', function(snap) {
 var data = snap.val() || {};
 renderSteamBlock(data);
 });
 }

 function renderSteamBlock(data) {
 var input = document.getElementById('steamIdInput');
 var statusRow = document.getElementById('steamStatusRow');
 var verifiedRow = document.getElementById('steamVerifiedRow');
 var saveBtn = document.getElementById('steamSaveBtn');

 if (data.steamId) {
 input.value = data.steamId;

 if (data.verified) {
 // Show verified state
 statusRow.style.display = 'none';
 verifiedRow.style.display = 'flex';
 var link = document.getElementById('steamProfileLink');
 link.href = getSteamProfileUrl(data.steamId);
 link.textContent = data.steamId;
 } else {
 // Show unverified state
 statusRow.style.display = 'flex';
 verifiedRow.style.display = 'none';
 var badge = document.getElementById('steamStatusBadge');
 badge.className = 'steam-status-badge unverified';
 badge.innerHTML = '<span class="material-symbols-outlined">pending</span><span id="steamStatusText">Не подтверждён</span>';
 }
 } else {
 input.value = '';
 statusRow.style.display = 'none';
 verifiedRow.style.display = 'none';
 }

 // If not own profile — make input read-only, hide buttons
 if (!isOwnProfile) {
 input.readOnly = true;
 if (saveBtn) saveBtn.style.display = 'none';
 }
 }

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
 var result2 = base + accountId;
 return 'https://steamcommunity.com/profiles/' + result2;
 }
 }
 }
 if (/^\d{17}$/.test(steamId)) {
 return 'https://steamcommunity.com/profiles/' + steamId;
 }
 return 'https://steamcommunity.com/profiles/' + steamId.replace(/[^a-zA-Z0-9_-]/g, '');
 }

 // Save Steam ID to Firebase
 window.steamSaveId = function() {
 var input = document.getElementById('steamIdInput');
 var steamId = input.value.trim();
 if (!steamId) {
 alert('Введите Steam ID');
 return;
 }

 steamRef.set({
 steamId: steamId,
 verified: false,
 verifyCode: '',
 username: profileUsername,
 userId: profileUserId,
 savedAt: firebase.database.ServerValue.TIMESTAMP
 });

 // Show verify panel
 steamShowVerifyPanel();
 };

 window.steamShowVerifyPanel = function() {
 var panel = document.getElementById('steamVerifyPanel');

 // Generate and save verify code
 var code = generateVerifyCode();
 steamRef.update({
 verifyCode: code
 });

 document.getElementById('steamVerifyCode').textContent = code;
 document.getElementById('steamSuccessMsg').classList.remove('show');
 document.getElementById('steamConfirmBtn').style.display = '';
 panel.classList.remove('steam-verify-hidden');
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

 // Confirm verification — mark as verified in Firebase
 window.steamConfirmVerify = function() {
 steamRef.update({
 verified: true,
 verifiedAt: firebase.database.ServerValue.TIMESTAMP
 });

 document.getElementById('steamSuccessMsg').classList.add('show');
 document.getElementById('steamConfirmBtn').style.display = 'none';

 setTimeout(function() {
 steamHideVerifyPanel();
 }, 3000);
 };
})();
</script>
<!-- === END STEAM VERIFICATION SCRIPT === -->
