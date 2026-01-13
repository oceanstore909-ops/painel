<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Gerador VIP - Sem Bot</title>
    <style>
        body { background: #050505; color: #00ff88; font-family: 'Segoe UI', sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .container { background: #111; padding: 30px; border-radius: 12px; border: 1px solid #00ff88; text-align: center; width: 450px; box-shadow: 0 0 30px rgba(0,255,136,0.1); }
        h2 { margin-bottom: 10px; text-transform: uppercase; letter-spacing: 2px; }
        #codeBox { background: #000; color: #00ff88; padding: 15px; border-radius: 5px; margin: 20px 0; font-family: 'Consolas', monospace; font-size: 12px; white-space: pre-wrap; border: 1px solid #222; min-height: 50px; display: flex; align-items: center; justify-content: center; }
        button { background: #00ff88; color: #000; border: none; padding: 15px; width: 100%; border-radius: 5px; font-weight: bold; cursor: pointer; transition: 0.3s; font-size: 16px; }
        button:hover { background: #00cc77; transform: scale(1.02); }
        .footer { margin-top: 15px; font-size: 11px; color: #555; }
    </style>
</head>
<body>

<div class="container">
    <h2>Script Generator</h2>
    <div id="codeBox">Aguardando geração...</div>
    <button onclick="gerarESalvar()">GERAR E COPIAR SCRIPT</button>
    <div class="footer">O IP e HWID serão logados ao executar.</div>
</div>

<script>
    function gerarESalvar() {
        // Gera uma key aleatória começando com VIP-
        const randomStr = Math.random().toString(36).substring(2, 10).toUpperCase();
        const key = "VIP-" + randomStr;
        
        // Monta o código que o usuário vai usar
        const scriptPronto = `script_key = "${key}"\nloadstring(game:HttpGet("https://pastefy.app/juEotrdE/raw"))()`;
        
        document.getElementById("codeBox").innerText = scriptPronto;

        // Copia para a área de transferência
        const el = document.createElement('textarea');
        el.value = scriptPronto;
        document.body.appendChild(el);
        el.select();
        document.execCommand('copy');
        document.body.removeChild(el);

        alert("Script copiado com sucesso! Cole no seu executor.");
    }
</script>

</body>
</html>
