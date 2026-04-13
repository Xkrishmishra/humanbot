<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>HumanBot — Termux Guide by 𝐂ᴏᴅᴇʀ~ᴋʀɪsʜ</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Syne:wght@400;700;800&display=swap');

  :root {
    --bg: #0a0a0f;
    --card: #12121a;
    --border: #1e1e2e;
    --accent: #7c3aed;
    --green: #22c55e;
    --yellow: #facc15;
    --red: #ef4444;
    --blue: #38bdf8;
    --text: #e2e8f0;
    --muted: #64748b;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Syne', sans-serif;
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* Animated BG */
  body::before {
    content: '';
    position: fixed;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(ellipse at 20% 20%, rgba(124,58,237,0.08) 0%, transparent 50%),
                radial-gradient(ellipse at 80% 80%, rgba(56,189,248,0.06) 0%, transparent 50%);
    animation: bgPulse 8s ease-in-out infinite alternate;
    pointer-events: none;
    z-index: 0;
  }

  @keyframes bgPulse {
    0% { transform: scale(1) rotate(0deg); }
    100% { transform: scale(1.1) rotate(2deg); }
  }

  .wrapper { max-width: 800px; margin: 0 auto; padding: 20px 16px 60px; position: relative; z-index: 1; }

  /* HEADER */
  .hero {
    text-align: center;
    padding: 40px 0 30px;
  }

  .hero-badge {
    display: inline-block;
    background: linear-gradient(135deg, rgba(124,58,237,0.2), rgba(56,189,248,0.2));
    border: 1px solid rgba(124,58,237,0.4);
    border-radius: 50px;
    padding: 6px 18px;
    font-size: 12px;
    color: var(--blue);
    letter-spacing: 2px;
    text-transform: uppercase;
    margin-bottom: 16px;
    animation: fadeIn 0.6s ease;
  }

  .hero h1 {
    font-size: clamp(26px, 6vw, 42px);
    font-weight: 800;
    background: linear-gradient(135deg, #a78bfa, #38bdf8, #22c55e);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    line-height: 1.2;
    margin-bottom: 10px;
  }

  .hero p {
    color: var(--muted);
    font-size: 14px;
  }

  .hero-by {
    margin-top: 12px;
    font-size: 13px;
    color: var(--accent);
    font-weight: 700;
  }

  /* STEP CARDS */
  .step-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    margin-bottom: 16px;
    overflow: hidden;
    animation: slideUp 0.5s ease both;
    transition: border-color 0.3s;
  }

  .step-card:hover { border-color: rgba(124,58,237,0.5); }

  @keyframes slideUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .step-card:nth-child(1) { animation-delay: 0.1s; }
  .step-card:nth-child(2) { animation-delay: 0.15s; }
  .step-card:nth-child(3) { animation-delay: 0.2s; }
  .step-card:nth-child(4) { animation-delay: 0.25s; }
  .step-card:nth-child(5) { animation-delay: 0.3s; }
  .step-card:nth-child(6) { animation-delay: 0.35s; }
  .step-card:nth-child(7) { animation-delay: 0.4s; }

  .step-header {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 16px 20px;
    border-bottom: 1px solid var(--border);
  }

  .step-num {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-weight: 800;
    font-size: 14px;
    flex-shrink: 0;
  }

  .num-purple { background: rgba(124,58,237,0.2); color: #a78bfa; border: 1px solid rgba(124,58,237,0.3); }
  .num-blue   { background: rgba(56,189,248,0.15); color: #38bdf8; border: 1px solid rgba(56,189,248,0.3); }
  .num-green  { background: rgba(34,197,94,0.15);  color: #22c55e; border: 1px solid rgba(34,197,94,0.3); }
  .num-yellow { background: rgba(250,204,21,0.15); color: #facc15; border: 1px solid rgba(250,204,21,0.3); }
  .num-red    { background: rgba(239,68,68,0.15);  color: #ef4444; border: 1px solid rgba(239,68,68,0.3); }

  .step-title {
    font-weight: 700;
    font-size: 15px;
    color: var(--text);
  }

  .step-subtitle {
    font-size: 12px;
    color: var(--muted);
    margin-top: 2px;
  }

  .step-body { padding: 16px 20px; }

  .note {
    background: rgba(250,204,21,0.06);
    border-left: 3px solid var(--yellow);
    border-radius: 0 8px 8px 0;
    padding: 10px 14px;
    font-size: 13px;
    color: #fde68a;
    margin-bottom: 14px;
  }

  .info {
    background: rgba(56,189,248,0.06);
    border-left: 3px solid var(--blue);
    border-radius: 0 8px 8px 0;
    padding: 10px 14px;
    font-size: 13px;
    color: #bae6fd;
    margin-bottom: 14px;
  }

  /* CODE BLOCKS */
  .cmd-block {
    background: #0d1117;
    border: 1px solid #1e2030;
    border-radius: 10px;
    margin: 8px 0;
    overflow: hidden;
  }

  .cmd-label {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 8px 14px;
    background: #161b22;
    border-bottom: 1px solid #1e2030;
  }

  .cmd-label span {
    font-size: 11px;
    color: var(--muted);
    font-family: 'JetBrains Mono', monospace;
  }

  .copy-btn {
    background: rgba(124,58,237,0.15);
    border: 1px solid rgba(124,58,237,0.3);
    border-radius: 6px;
    color: #a78bfa;
    font-size: 11px;
    padding: 3px 10px;
    cursor: pointer;
    font-family: 'Syne', sans-serif;
    transition: all 0.2s;
  }

  .copy-btn:hover { background: rgba(124,58,237,0.3); }
  .copy-btn.copied { color: #22c55e; border-color: rgba(34,197,94,0.3); background: rgba(34,197,94,0.1); }

  .cmd-content {
    padding: 14px 16px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.8;
    color: #cdd6f4;
    white-space: pre-wrap;
    word-break: break-all;
  }

  .cmd-content .prompt { color: #22c55e; user-select: none; }
  .cmd-content .comment { color: #6272a4; }
  .cmd-content .pkg { color: #f1fa8c; }
  .cmd-content .flag { color: #ffb86c; }
  .cmd-content .str { color: #50fa7b; }

  /* TAGS */
  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 10px; }
  .tag {
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 50px;
    font-weight: 700;
  }

  .tag-green { background: rgba(34,197,94,0.1); color: #22c55e; border: 1px solid rgba(34,197,94,0.2); }
  .tag-blue  { background: rgba(56,189,248,0.1); color: #38bdf8; border: 1px solid rgba(56,189,248,0.2); }
  .tag-purple{ background: rgba(124,58,237,0.1); color: #a78bfa; border: 1px solid rgba(124,58,237,0.2); }

  /* DIVIDER */
  .divider {
    text-align: center;
    margin: 24px 0 16px;
    position: relative;
    color: var(--muted);
    font-size: 12px;
    letter-spacing: 2px;
    text-transform: uppercase;
  }

  .divider::before, .divider::after {
    content: '';
    position: absolute;
    top: 50%;
    width: 35%;
    height: 1px;
    background: var(--border);
  }

  .divider::before { left: 0; }
  .divider::after  { right: 0; }

  /* FOOTER */
  .footer {
    text-align: center;
    padding: 30px 0 10px;
    color: var(--muted);
    font-size: 13px;
  }

  .footer .brand {
    font-weight: 800;
    background: linear-gradient(135deg, #a78bfa, #38bdf8);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
    font-size: 16px;
    display: block;
    margin-bottom: 6px;
  }

  @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
</style>
</head>
<body>
<div class="wrapper">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-badge">📱 Termux Installation Guide</div>
    <h1>HumanBot Setup<br>Complete Guide</h1>
    <p>Apne phone pe Telegram Bot chalao — bilkul aasaan steps mein</p>
    <div class="hero-by">⚡ by 𝐂ᴏᴅᴇʀ~ᴋʀɪsʜ</div>
  </div>

  <!-- STEP 1 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-purple">1</div>
      <div>
        <div class="step-title">Termux Install Karo</div>
        <div class="step-subtitle">F-Droid se install karna zaroori hai</div>
      </div>
    </div>
    <div class="step-body">
      <div class="note">⚠️ Play Store wala Termux outdated hai — F-Droid se lo!</div>
      <p style="font-size:13px; color: var(--muted); margin-bottom: 10px;">F-Droid open karo aur search karo <strong style="color:var(--text)">"Termux"</strong></p>
      <div class="tags">
        <span class="tag tag-blue">🌐 f-droid.org</span>
        <span class="tag tag-green">✅ Free & Open Source</span>
      </div>
    </div>
  </div>

  <!-- STEP 2 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-blue">2</div>
      <div>
        <div class="step-title">Termux Open & Update</div>
        <div class="step-subtitle">First time setup — packages update karo</div>
      </div>
    </div>
    <div class="step-body">
      <div class="info">💡 Pehli baar open karo, phir ye commands run karo</div>
      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span><span class="comment"># Storage permission do</span>
<span class="prompt">$ </span>termux-setup-storage

<span class="prompt">$ </span><span class="comment"># Packages update karo</span>
<span class="prompt">$ </span>pkg update <span class="flag">-y</span>
<span class="prompt">$ </span>pkg upgrade <span class="flag">-y</span></div>
      </div>
    </div>
  </div>

  <!-- STEP 3 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-green">3</div>
      <div>
        <div class="step-title">Python Install Karo</div>
        <div class="step-subtitle">Python 3 + pip chahiye bot ke liye</div>
      </div>
    </div>
    <div class="step-body">
      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span>pkg install <span class="pkg">python</span> <span class="flag">-y</span>

<span class="prompt">$ </span><span class="comment"># Version check karo</span>
<span class="prompt">$ </span>python --version
<span class="comment">Python 3.11.x ✅</span>

<span class="prompt">$ </span>pip --version
<span class="comment">pip 23.x ✅</span></div>
      </div>
    </div>
  </div>

  <!-- STEP 4 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-yellow">4</div>
      <div>
        <div class="step-title">Bot Library Install Karo</div>
        <div class="step-subtitle">python-telegram-bot install karo</div>
      </div>
    </div>
    <div class="step-body">
      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span>pip install <span class="pkg">python-telegram-bot</span>

<span class="comment"># Ya latest version ke liye:</span>
<span class="prompt">$ </span>pip install <span class="pkg">python-telegram-bot</span><span class="flag">==21.3</span></div>
      </div>
      <div class="tags">
        <span class="tag tag-purple">📦 python-telegram-bot</span>
        <span class="tag tag-green">✅ Async Support</span>
      </div>
    </div>
  </div>

  <!-- STEP 5 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-red">5</div>
      <div>
        <div class="step-title">Bot Token Lo — @BotFather</div>
        <div class="step-subtitle">Telegram pe apna bot banao</div>
      </div>
    </div>
    <div class="step-body">
      <div class="info">💡 Telegram open karo → Search <strong>@BotFather</strong> → /newbot → naam do → token copy karo</div>
      <div class="cmd-block">
        <div class="cmd-label">
          <span>Steps</span>
        </div>
        <div class="cmd-content"><span class="comment">1. Telegram pe @BotFather search karo</span>
<span class="comment">2. /newbot type karo</span>
<span class="comment">3. Bot ka naam do (e.g. MyHumanBot)</span>
<span class="comment">4. Username do (e.g. my_human_bot)</span>
<span class="comment">5. Token milega — copy karo!</span>

<span class="str">Token example:</span>
<span class="pkg">7123456789:AAHxyz_abcdef_SAMPLE_TOKEN_HERE</span></div>
      </div>
    </div>
  </div>

  <!-- STEP 6 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-purple">6</div>
      <div>
        <div class="step-title">Bot File Create & Edit Karo</div>
        <div class="step-subtitle">humanbot.py file banao aur token daalo</div>
      </div>
    </div>
    <div class="step-body">
      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span><span class="comment"># Folder banao</span>
<span class="prompt">$ </span>mkdir humanbot && cd humanbot

<span class="prompt">$ </span><span class="comment"># nano editor se file banao</span>
<span class="prompt">$ </span>nano humanbot.py

<span class="comment"># Paste karo pure code ko
# Ctrl+X → Y → Enter se save karo</span></div>
      </div>
      <div class="note">⚠️ File mein <code style="color:#facc15">YOUR_BOT_TOKEN_HERE</code> ki jagah apna token daalo aur <code style="color:#facc15">123456789</code> ki jagah apna Telegram ID (userinfobot se lo)</div>
    </div>
  </div>

  <!-- STEP 7 -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-green">7</div>
      <div>
        <div class="step-title">Bot Run Karo! 🚀</div>
        <div class="step-subtitle">Background mein bhi chala sakte ho</div>
      </div>
    </div>
    <div class="step-body">
      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash — Normal Run</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span>python humanbot.py

<span class="comment"># Output aayega:
# 🚀 𝐂ᴏᴅᴇʀ~ᴋʀɪsʜ HumanBot starting...
# ✅ Bot is LIVE! Owner ID: XXXXXXX</span></div>
      </div>

      <div class="divider">background mein chalana hai?</div>

      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash — Background (nohup)</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span>pkg install <span class="pkg">nohup</span> <span class="flag">-y</span>

<span class="prompt">$ </span>nohup python humanbot.py <span class="flag">&</span>

<span class="comment"># Bot background mein chalu rahega
# Termux band karo — bot phir bhi chalega!</span></div>
      </div>

      <div class="divider">ya tmux use karo</div>

      <div class="cmd-block">
        <div class="cmd-label">
          <span>bash — Tmux (best method)</span>
          <button class="copy-btn" onclick="copyCmd(this)">Copy</button>
        </div>
        <div class="cmd-content"><span class="prompt">$ </span>pkg install <span class="pkg">tmux</span> <span class="flag">-y</span>

<span class="prompt">$ </span>tmux new <span class="flag">-s</span> <span class="str">bot</span>
<span class="prompt">$ </span>python humanbot.py

<span class="comment"># Detach: Ctrl+B phir D
# Reattach: tmux attach -t bot</span></div>
      </div>
    </div>
  </div>

  <!-- BONUS -->
  <div class="step-card">
    <div class="step-header">
      <div class="step-num num-blue">✨</div>
      <div>
        <div class="step-title">Troubleshooting & Tips</div>
        <div class="step-subtitle">Common errors aur fixes</div>
      </div>
    </div>
    <div class="step-body">
      <div class="cmd-block">
        <div class="cmd-label"><span>Common Fixes</span></div>
        <div class="cmd-content"><span class="comment"># Error: ModuleNotFoundError</span>
<span class="prompt">$ </span>pip install <span class="pkg">python-telegram-bot</span> <span class="flag">--upgrade</span>

<span class="comment"># Error: pip not found</span>
<span class="prompt">$ </span>pkg install <span class="pkg">python-pip</span>

<span class="comment"># Error: Storage permission denied</span>
<span class="prompt">$ </span>termux-setup-storage

<span class="comment"># Apna Telegram ID pata karo</span>
<span class="comment"># @userinfobot pe /start bhejo</span></div>
      </div>
      <div class="tags">
        <span class="tag tag-green">✅ Python 3.8+</span>
        <span class="tag tag-blue">📱 Android 7+</span>
        <span class="tag tag-purple">⚡ F-Droid Termux</span>
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <span class="brand">𝐂ᴏᴅᴇʀ~ᴋʀɪsʜ</span>
    Made with 💙 for the developer community
    <br><br>
    <span style="font-size:11px; opacity:0.5;">@Krishnetwork | HumanBot v2.0</span>
  </div>

</div>

<script>
  function copyCmd(btn) {
    const block = btn.closest('.cmd-block').querySelector('.cmd-content');
    // Remove prompt symbols for clean copy
    let text = block.innerText.replace(/^\$ /gm, '').replace(/^# .*/gm, '').trim();
    navigator.clipboard.writeText(text).then(() => {
      btn.textContent = 'Copied!';
      btn.classList.add('copied');
      setTimeout(() => {
        btn.textContent = 'Copy';
        btn.classList.remove('copied');
      }, 2000);
    });
  }
</script>
</body>
</html>
