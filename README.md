<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8">
<title>vitor@brandao</title>
<style>
  body {
    margin: 0;
    padding: 40px;
    background: #0d0e12;
    display: flex;
    justify-content: center;
  }

  .terminal {
    width: 860px;
    background: #181a20;
    border: 1px solid #2a2d36;
    border-radius: 14px;
    padding: 24px 32px;
    font-family: 'Courier New', 'DejaVu Sans Mono', monospace;
    color: #ffffff;
    box-sizing: border-box;
  }

  .dots {
    display: flex;
    gap: 8px;
    margin-bottom: 18px;
  }
  .dot { width: 12px; height: 12px; border-radius: 50%; }
  .dot.red { background: #ff5f56; }
  .dot.yellow { background: #ffbd2e; }
  .dot.green { background: #27c93f; }

  .content {
    display: flex;
    gap: 40px;
  }

  .ascii {
    width: 300px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .ascii-hash {
    font-family: 'Courier New', 'DejaVu Sans Mono', monospace;
    font-size: 9px;
    line-height: 11px;
    white-space: pre;
    color: #d19a66;
    text-align: center;
  }
  .ascii-hash .px {
    display: inline-block;
    animation-name: twinkle;
    animation-timing-function: ease-in-out;
    animation-iteration-count: infinite;
  }

  @keyframes twinkle {
    0%, 100% { opacity: 1; }
    50% { opacity: 0.1; }
  }

  .info { flex: 1; font-size: 15px; line-height: 24px; }
  .user { color: #58592D; font-weight: bold; font-size: 17px; }
  .rule { color: #5c6370; }
  .section { color: #e5c07b; font-weight: bold; margin-top: 14px; text-align: center; }
  .label { color: #F2EBC4; }
  .dots-line { color: #5c6370; }
  .value { color: #A67153; }

  .prompt { margin-top: 24px; color: #98c379; font-size: 15px; }
  .prompt .arrow { color: #ffffff; }
</style>
</head>
<body>

<div class="terminal">
  <div class="dots">
    <span class="dot red"></span>
    <span class="dot yellow"></span>
    <span class="dot green"></span>
  </div>

  <div class="content">
    <div class="ascii"><div class="ascii-hash" id="ascii-art">%%%%           %%%%
  ######     ######
############################
#                          #
#     *              @     #
#   *****         @     @  #
#     *              @     #
#                          #
##                        ##
 ###                    ###
  ####                ####
   #####            #####
    ######        ######
     #######    #######
       ###########</div></div>

    <div class="info">
      <div class="user">vitor@brandao</div>
      <div class="rule">--------------</div>

      <div class="section">General Info</div>
      <div><span class="label">Name: </span><span class="dots-line">...........................</span><span class="value"> Vitor Brandão</span></div>
      <div><span class="label">Birth: </span><span class="dots-line">..........................</span><span class="value"> 02/2008</span></div>
      <div><span class="label">Location: </span><span class="dots-line">......................</span><span class="value"> Brasília-DF, Brazil</span></div>

      <div class="section">Knowledge</div>
      <div><span class="label">Programming: </span><span class="dots-line">..................</span><span class="value"> Python, C, HTML</span></div>
      <div><span class="label">Interests: </span><span class="dots-line">....................</span><span class="value"> Machine Learning</span></div>
      <div><span class="label">Languages: </span><span class="dots-line">....................</span><span class="value"> English, Portuguese</span></div>

      <div class="section">Contact</div>
      <div><span class="label">Email: </span><span class="dots-line">.........................</span><span class="value"> vitorbrandao928@gmail.com</span></div>
      <div><span class="label">GitHub: </span><span class="dots-line">........................</span><span class="value"> github.com/vitorandao</span></div>
    </div>
  </div>

  <div class="prompt">vitor@brandao <span class="arrow">~&gt;</span> <span class="arrow">▌</span></div>
</div>

<script>
  const colorMap = { '#': '#d19a66', '%': '#e5c07b', '@': '#f0c674', '*': '#f0c674' };
  const el = document.getElementById('ascii-art');
  const text = el.textContent;
  el.textContent = '';
  for (const ch of text) {
    if (ch === ' ' || ch === '\n') {
      el.appendChild(document.createTextNode(ch));
    } else {
      const span = document.createElement('span');
      span.textContent = ch;
      span.className = 'px';
      span.style.color = colorMap[ch] || '#d19a66';
      span.style.animationDelay = (Math.random() * 3).toFixed(2) + 's';
      span.style.animationDuration = (0.8 + Math.random() * 1.8).toFixed(2) + 's';
      el.appendChild(span);
    }
  }
</script>

</body>
</html>
