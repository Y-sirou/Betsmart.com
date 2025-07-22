<!DOCTYPE html>
<html lang="fr">
<head><meta charset="UTF-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<title>SmartScore Exact – Officiel</title>
<style>body{font-family:sans-serif;max-width:600px;margin:auto;padding:20px}
h1{text-align:center;color:#006f5f}
.match{border:1px solid #ddd;border-radius:8px;padding:10px;margin:10px 0}
.header{font-weight:bold}
.score{font-size:1.2rem;color:#c00;font-weight:bold}
.sources{font-size:0.9rem;color:#555;margin-top:5px}
</style></head>
<body>
<h1>SmartScore Exact – Officiel</h1>
<p>📅 Mise à jour : <span id="date"></span></p>
<div id="matches">Chargement des résultats …</div>
<script>
document.getElementById('date').innerText = new Date().toLocaleDateString();

const data = [
  {match:'Real Madrid vs Sevilla', comp:'Liga', time:'18:30', score:'2-1',
   sources:['FB24','SofaScore','WinDrawWin','PredictZ']},
  {match:'Man City vs Chelsea', comp:'Premier League', time:'19:00', score:'1-1',
   sources:['BeSoccer','FootyStats','SofaScore']},
  {match:'AC Milan vs Napoli', comp:'Serie A', time:'20:45', score:'1-0',
   sources:['FB24','Score24','PredictZ']},
  {match:'Al Ahly vs Zamalek', comp:'Egypt Premier', time:'21:00', score:'2-1',
   sources:['WinDrawWin','SofaScore','BeSoccer']},
  {match:'Lyon vs PSG', comp:'Ligue 1', time:'21:00', score:'1-2',
   sources:['FB24','SofaScore','PredictZ']}
];

const ctn = document.getElementById('matches');
ctn.innerHTML = '';
data.slice(0,5).forEach(m=>{
  const el=document.createElement('div');el.className='match';
  el.innerHTML = `<div class="header">${m.comp} — ${m.time}</div>
                  <div class="score">${m.match} → ${m.score}</div>
                  <div class="sources">Sources : ${m.sources.join(' | ')}</div>`;
  ctn.appendChild(el);
});
</script>
</body>
</html>
