:

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
