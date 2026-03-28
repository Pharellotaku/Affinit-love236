<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Affinity Check</title>
    <style>
        body { background: #0a0a0a; color: white; font-family: sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
        .card { background: #1a1a1a; padding: 25px; border-radius: 20px; text-align: center; width: 85%; max-width: 350px; border: 1px solid #333; }
        h1 { color: #ff4d6d; font-size: 22px; }
        input { width: 100%; padding: 12px; margin: 8px 0; border-radius: 10px; border: 1px solid #444; background: #252525; color: white; text-align: center; box-sizing: border-box; }
        button { background: #ff4d6d; color: white; border: none; padding: 15px; border-radius: 10px; width: 100%; font-weight: bold; margin-top: 10px; cursor: pointer; }
        #result-box { margin-top: 20px; display: none; padding: 15px; }
    </style>
</head>
<body>

<div class="card">
    <h1>✨ Destin & Affinités ✨</h1>
    <input type="text" id="n1" placeholder="Ton prénom">
    <input type="text" id="n2" placeholder="Prénom du crush">
    <button onclick="verifier()">VOIR LE SCORE</button> 
    
    <div id="result-box">
        <div id="score" style="font-size: 40px; font-weight: bold; color: #ff4d6d;"></div>
        <div id="msg"></div>
    </div>
</div>

<script>
    function verifier() {
        const p1 = document.getElementById('n1').value.trim().toLowerCase();
        const p2 = document.getElementById('n2').value.trim().toLowerCase();
        const res = document.getElementById('result-box');
        const sc = document.getElementById('score');
        const ms = document.getElementById('msg');

        if(p1 === "" || p2 === "") {
            alert("Remplis les deux cases !");
            return;
        }

        res.style.display = "block";

        if ((p1 === "pharell" && p2 === "ariana") || (p1 === "ariana" && p2 === "pharell")) {
            sc.innerHTML = "99.9%";
            ms.innerHTML = "<b style='color:#00ffcc;'>Incroyable ! Pharell & Ariana, c'est le destin pur. ❤️✨</b>";
        } else {
            sc.innerHTML = Math.floor(Math.random() * 10) + "%";
            const vannes = ["Espoir fait vivre...", "Jay a plus de flow.", "Même Josué dit non.", "Aaron rigole de toi."];
            ms.innerHTML = "<i>" + vannes[Math.floor(Math.random() * vannes.length)] + "</i>";
        }
    }
</script>

</body>
</html>
