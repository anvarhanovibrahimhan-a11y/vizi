[Uploading vizitka-clean (2).html…]()
# vizi<!DOCTYPE html>
<html lang="ru" data-theme="light">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Ибрахимхан — визитка</title>
<style>
  :root {
    --bg: #f4f5f8;
    --bg-art:
      radial-gradient(circle at 12% 8%, rgba(129, 140, 248, .38), transparent 42%),
      radial-gradient(circle at 92% 14%, rgba(56, 189, 248, .26), transparent 38%),
      radial-gradient(circle at 88% 92%, rgba(244, 114, 182, .30), transparent 45%),
      radial-gradient(circle at 6% 96%, rgba(167, 139, 250, .24), transparent 40%),
      linear-gradient(180deg, #f8f8fc 0%, #eceef7 100%);
    --dot: rgba(79, 70, 229, .16);
    --card: #ffffff;
    --text: #111827;
    --muted: #6b7280;
    --line: #e5e7eb;
    --soft: #f3f4f6;
    --accent: #4f46e5;
    --accent2: #7c3aed;
    --ok: #22c55e;
  }
  :root[data-theme="dark"] {
    --bg: #0f1115;
    --bg-art:
      radial-gradient(circle at 12% 8%, rgba(99, 102, 241, .28), transparent 42%),
      radial-gradient(circle at 92% 14%, rgba(14, 165, 233, .16), transparent 38%),
      radial-gradient(circle at 88% 92%, rgba(236, 72, 153, .18), transparent 45%),
      linear-gradient(180deg, #0c0e14 0%, #12151d 100%);
    --dot: rgba(255, 255, 255, .07);
    --card: #171a21;
    --text: #f3f4f6;
    --muted: #9ca3af;
    --line: #262b36;
    --soft: #1f2430;
    --accent: #818cf8;
    --accent2: #a78bfa;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 32px 16px;
    position: relative;
    background: var(--bg-art) fixed;
    color: var(--text);
    font-family: system-ui, -apple-system, "Segoe UI", Roboto, sans-serif;
    transition: color .3s;
  }
  /* Тонкая точечная сетка поверх градиента, затухает к краям */
  body::before {
    content: "";
    position: fixed; inset: 0; z-index: 0; pointer-events: none;
    background-image: radial-gradient(var(--dot) 1px, transparent 1px);
    background-size: 22px 22px;
    -webkit-mask-image: radial-gradient(ellipse at center, #000 35%, transparent 80%);
    mask-image: radial-gradient(ellipse at center, #000 35%, transparent 80%);
  }
  .card {
    z-index: 1;
    position: relative;
    width: 100%;
    max-width: 380px;
    background: var(--card);
    border: 1px solid var(--line);
    border-radius: 28px;
    padding: 36px 28px 28px;
    box-shadow: 0 1px 2px rgba(0, 0, 0, .04), 0 12px 32px rgba(0, 0, 0, .06);
    transition: background .3s, border-color .3s;
  }
  .view { display: none; text-align: center; }
  .view.active { display: block; animation: fade .4s ease; }
  @keyframes fade {
    from { opacity: 0; transform: translateY(8px); }
    to   { opacity: 1; transform: none; }
  }

  .theme {
    position: absolute; top: 14px; right: 14px;
    width: 36px; height: 36px; border-radius: 50%;
    border: 1px solid var(--line); background: var(--soft);
    color: var(--text); font-size: 16px; cursor: pointer;
  }

  .avatar {
    position: relative;
    width: 104px; height: 104px;
    margin: 0 auto 18px;
    border-radius: 50%;
    display: grid; place-items: center;
    font-size: 44px; font-weight: 700; color: #fff;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    cursor: pointer; user-select: none;
    transition: transform .3s;
  }
  .avatar:hover { transform: scale(1.04); }
  .avatar.wiggle { animation: wig .6s ease; }
  @keyframes wig {
    0%, 100% { transform: rotate(0); }
    25% { transform: rotate(-8deg); }
    75% { transform: rotate(8deg); }
  }
  .status {
    position: absolute; right: 4px; bottom: 4px;
    width: 18px; height: 18px; border-radius: 50%;
    background: var(--ok); border: 3px solid var(--card);
  }

  h1 { font-size: 30px; font-weight: 700; letter-spacing: -.3px; }
  .role { margin-top: 6px; min-height: 24px; color: var(--muted); font-size: 15px; }
  .caret {
    display: inline-block; width: 2px; height: 1em; margin-left: 2px;
    vertical-align: -2px; background: var(--accent);
    animation: blink 1s steps(1) infinite;
  }
  @keyframes blink { 50% { opacity: 0; } }

  .chips { display: flex; flex-wrap: wrap; justify-content: center; gap: 8px; margin: 20px 0; }
  .chip {
    padding: 6px 13px; font-size: 13px; border-radius: 999px;
    background: var(--soft); color: var(--text);
  }

  .stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; margin-bottom: 20px; }
  .stat { padding: 12px 4px; border-radius: 14px; background: var(--soft); }
  .stat b { display: block; font-size: 20px; font-variant-numeric: tabular-nums; }
  .stat span { font-size: 11px; color: var(--muted); }

  .btn {
    display: inline-flex; align-items: center; justify-content: center; gap: 8px;
    width: 100%; padding: 13px; border: 0; border-radius: 14px;
    font-size: 15px; font-weight: 600; color: #fff;
    background: var(--accent); cursor: pointer;
    transition: opacity .2s, transform .2s;
  }
  .btn:hover { opacity: .92; }
  .btn:active { transform: scale(.98); }
  .btn svg { width: 18px; height: 18px; fill: none; stroke: currentColor; stroke-width: 2; stroke-linecap: round; stroke-linejoin: round; }

  .actions { display: flex; gap: 10px; margin-top: 10px; }
  .like {
    flex: 1;
    display: inline-flex; align-items: center; justify-content: center; gap: 8px;
    padding: 12px; border-radius: 14px;
    border: 1px solid var(--line); background: var(--card); color: var(--text);
    font-size: 15px; font-weight: 600; cursor: pointer;
    transition: background .2s, border-color .2s, color .2s;
  }
  .like.liked { background: #fee2e2; border-color: #fecaca; color: #dc2626; }
  :root[data-theme="dark"] .like.liked { background: #3b1d24; border-color: #5b2a35; color: #fca5a5; }
  .like .heart { display: inline-block; font-size: 17px; }
  .count { font-variant-numeric: tabular-nums; color: var(--muted); font-weight: 500; }
  .share {
    width: 48px; flex: 0 0 48px; padding: 0;
    background: var(--card); color: var(--text); border: 1px solid var(--line);
  }
  .share:hover { background: var(--soft); }
  .share svg { width: 18px; height: 18px; fill: none; stroke: currentColor; stroke-width: 2; }

  .hint { margin-top: 14px; font-size: 12px; color: var(--muted); }

  .back h2 { font-size: 22px; font-weight: 700; }
  .sub { color: var(--muted); font-size: 14px; margin: 4px 0 18px; }
  .rows { display: flex; flex-direction: column; gap: 8px; margin-bottom: 16px; }
  .row {
    justify-content: space-between;
    padding: 12px 14px; text-align: left;
    background: var(--soft); color: var(--text);
  }
  .row:hover { background: var(--line); }
  .row .l { display: flex; align-items: center; gap: 12px; }
  .row svg { width: 18px; height: 18px; flex: 0 0 18px; }
  .row small { display: block; color: var(--muted); font-weight: 400; font-size: 12px; }
  .row em { font-style: normal; font-size: 12px; color: var(--accent); }
  .row > span { display: flex; align-items: center; gap: 12px; }
  .row .l span { display: block; }
  .back .btn.ghost { background: var(--soft); color: var(--text); }

  .toast {
    position: fixed; left: 50%; bottom: 24px;
    transform: translate(-50%, 20px); opacity: 0;
    padding: 10px 18px; border-radius: 999px;
    background: #111827; color: #fff; font-size: 14px;
    transition: all .3s; pointer-events: none;
  }
  .toast.show { opacity: 1; transform: translate(-50%, 0); }

  @media (max-width: 420px) {
    h1 { font-size: 26px; }
    .card { padding: 32px 20px 22px; }
  }
  @media (prefers-reduced-motion: reduce) {
    *, *::before, *::after { animation: none !important; transition: none !important; }
  }
</style>
</head>
<body>
  <main class="card">
    <button class="theme" id="theme" type="button" aria-label="Сменить тему">🌙</button>

    <!-- Лицевая сторона -->
    <section class="view active" id="front">
      <div class="avatar" id="avatar" title="Нажми на меня">И<span class="status" title="На связи"></span></div>

      <h1>Ибрахимхан</h1>
      <p class="role"><span id="typed"></span><span class="caret"></span></p>

      <div class="chips">
        <span class="chip">✨ Дружелюбный</span>
        <span class="chip">🚀 Целеустремлённый</span>
        <span class="chip">💡 Творческий</span>
      </div>

      <div class="stats">
        <div class="stat"><b id="sLikes">0</b><span>лайков</span></div>
        <div class="stat"><b id="sVisits">0</b><span>твоих визитов</span></div>
        <div class="stat"><b id="sTime">0</b><span>сек. на странице</span></div>
      </div>

      <button class="btn" id="flipBtn" type="button">
        <svg viewBox="0 0 24 24"><path d="M22 16.9v3a2 2 0 0 1-2.2 2 19.8 19.8 0 0 1-8.6-3.1 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.1 4.2 2 2 0 0 1 4.1 2h3a2 2 0 0 1 2 1.7c.1 1 .4 1.9.7 2.8a2 2 0 0 1-.5 2.1L8.1 9.9a16 16 0 0 0 6 6l1.3-1.3a2 2 0 0 1 2.1-.4c.9.3 1.8.6 2.8.7a2 2 0 0 1 1.7 2z"/></svg>
        Контакты
      </button>

      <div class="actions">
        <button class="like" id="like" type="button" aria-pressed="false">
          <span class="heart" id="heart">🤍</span>
          <span>Нравится</span>
          <span class="count" id="count">0</span>
        </button>
        <button class="btn share" id="share" type="button" aria-label="Поделиться">
          <svg viewBox="0 0 24 24"><circle cx="18" cy="5" r="3"/><circle cx="6" cy="12" r="3"/><circle cx="18" cy="19" r="3"/><path d="m8.6 13.5 6.8 4m0-11-6.8 4"/></svg>
        </button>
      </div>
      <p class="hint">Двойной клик по карточке — тоже лайк 💜</p>
    </section>

    <!-- Обратная сторона -->
    <section class="view back" id="back">
      <h2>Связаться со мной</h2>
      <p class="sub">Нажми на строку, чтобы скопировать</p>
      <div class="rows">
        <button class="btn row" type="button" data-copy="name@example.com">
          <span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="3" y="5" width="18" height="14" rx="2"/><path d="m3 7 9 6 9-6"/></svg><span>Почта<small>name@example.com</small></span></span><em>копировать</em>
        </button>
        <button class="btn row" type="button" data-copy="+7 700 000 00 00">
          <span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 16.9v3a2 2 0 0 1-2.2 2 19.8 19.8 0 0 1-8.6-3.1 19.5 19.5 0 0 1-6-6A19.8 19.8 0 0 1 2.1 4.2 2 2 0 0 1 4.1 2h3a2 2 0 0 1 2 1.7c.1 1 .4 1.9.7 2.8a2 2 0 0 1-.5 2.1L8.1 9.9a16 16 0 0 0 6 6l1.3-1.3a2 2 0 0 1 2.1-.4c.9.3 1.8.6 2.8.7a2 2 0 0 1 1.7 2z"/></svg><span>Телефон<small>+7 700 000 00 00</small></span></span><em>копировать</em>
        </button>
        <button class="btn row" type="button" data-copy="@username">
          <span class="l"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="m22 3-9.5 18-2.5-7.5L2 11z"/><path d="m10 13.5 4-4"/></svg><span>Telegram<small>@username</small></span></span><em>копировать</em>
        </button>
      </div>
      <button class="btn ghost" id="backBtn" type="button">← Назад</button>
    </section>
  </main>

  <div class="toast" id="toast"></div>

<script>
(function () {
  var root = document.documentElement;
  function $(id) { return document.getElementById(id); }
  function store(k, v) {
    try {
      if (v === undefined) return localStorage.getItem(k);
      localStorage.setItem(k, v);
    } catch (e) {}
    return null;
  }

  /* ---------- Тост ---------- */
  var toast = $('toast'), toastT;
  function showToast(msg) {
    toast.textContent = msg;
    toast.classList.add('show');
    clearTimeout(toastT);
    toastT = setTimeout(function () { toast.classList.remove('show'); }, 2000);
  }

  /* ---------- Тема ---------- */
  var themeBtn = $('theme');
  function setTheme(t) {
    root.setAttribute('data-theme', t);
    themeBtn.textContent = t === 'dark' ? '☀️' : '🌙';
    store('ibr_theme', t);
  }
  setTheme(store('ibr_theme') || 'light');
  themeBtn.addEventListener('click', function () {
    setTheme(root.getAttribute('data-theme') === 'dark' ? 'light' : 'dark');
  });

  /* ---------- Печатающийся текст ---------- */
  var phrases = ['Добро пожаловать!', 'Это моя визитка', 'Поставь лайк ❤️', 'Нажми на мой аватар 😉'];
  var typed = $('typed'), pi = 0, ci = 0, del = false;
  var reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  (function tick() {
    var p = phrases[pi], delay;
    if (reduce) {
      typed.textContent = p;
      pi = (pi + 1) % phrases.length;
      return setTimeout(tick, 2500);
    }
    typed.textContent = p.slice(0, ci);
    delay = del ? 30 : 75;
    if (!del && ci === p.length) { del = true; delay = 1600; }
    else if (del && ci === 0) { del = false; pi = (pi + 1) % phrases.length; delay = 350; }
    ci += del ? -1 : 1;
    setTimeout(tick, delay);
  })();

  /* ---------- Переключение граней (без 3D) ---------- */
  function show(id) {
    $('front').classList.toggle('active', id === 'front');
    $('back').classList.toggle('active', id === 'back');
  }
  $('flipBtn').addEventListener('click', function () { show('back'); });
  $('backBtn').addEventListener('click', function () { show('front'); });

  /* ---------- Копирование контактов ---------- */
  Array.prototype.forEach.call(document.querySelectorAll('[data-copy]'), function (b) {
    b.addEventListener('click', function () {
      var v = b.getAttribute('data-copy');
      if (navigator.clipboard && navigator.clipboard.writeText) {
        navigator.clipboard.writeText(v).then(
          function () { showToast('Скопировано: ' + v + ' ✓'); },
          function () { showToast('Не удалось скопировать'); }
        );
      } else {
        showToast(v);
      }
    });
  });

  /* ---------- Аватар ---------- */
  var avatar = $('avatar');
  avatar.addEventListener('click', function () {
    avatar.classList.remove('wiggle');
    void avatar.offsetWidth;
    avatar.classList.add('wiggle');
  });

  /* ---------- Лайк ---------- */
  var heart = $('heart'), countEl = $('count'), sLikes = $('sLikes'), likeBtn = $('like');
  var count = parseInt(store('ibr_likes'), 10) || 0;
  var liked = store('ibr_liked') === '1';

  function render() {
    countEl.textContent = count;
    sLikes.textContent = count;
    heart.textContent = liked ? '❤️' : '🤍';
    likeBtn.classList.toggle('liked', liked);
    likeBtn.setAttribute('aria-pressed', liked ? 'true' : 'false');
  }
  function setLiked(v) {
    if (liked === v) return;
    liked = v;
    count = Math.max(0, count + (liked ? 1 : -1));
    store('ibr_likes', String(count));
    store('ibr_liked', liked ? '1' : '0');
    render();
    if (liked && count % 10 === 0) showToast('🎉 ' + count + ' лайков!');
  }
  likeBtn.addEventListener('click', function () { setLiked(!liked); });
  $('front').addEventListener('dblclick', function (e) {
    if (e.target.closest('.btn, .like, .theme, .avatar')) return;
    setLiked(true);
  });

  /* ---------- Статистика ---------- */
  var visits = (parseInt(store('ibr_visits'), 10) || 0) + 1;
  store('ibr_visits', String(visits));
  $('sVisits').textContent = visits;
  var sec = 0;
  setInterval(function () {
    if (!document.hidden) { sec++; $('sTime').textContent = sec; }
  }, 1000);
  render();

  /* ---------- Поделиться ---------- */
  $('share').addEventListener('click', function () {
    var url = location.href;
    if (navigator.share) {
      navigator.share({ title: 'Ибрахимхан — визитка', url: url }).catch(function () {});
    } else if (navigator.clipboard && navigator.clipboard.writeText) {
      navigator.clipboard.writeText(url).then(
        function () { showToast('Ссылка скопирована ✓'); },
        function () { showToast('Не удалось скопировать'); }
      );
    } else {
      showToast('Скопируйте ссылку из адресной строки');
    }
  });
})();
</script>
</body>
</html>
