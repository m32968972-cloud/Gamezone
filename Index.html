<!doctype html>
<html lang="pl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>GAME ZONE</title>
<style>
body{margin:0;background:#101323;color:white;font-family:Arial;text-align:center}
header{padding:25px;background:linear-gradient(135deg,#5126a8,#087eaa)}
h1{font-size:45px}
main{padding:20px;max-width:900px;margin:auto}
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:12px}
.card{background:#202943;padding:25px;border-radius:15px;cursor:pointer}
.card span{font-size:35px}
button{background:#7654e8;color:white;border:0;padding:12px;border-radius:10px;margin:5px}
canvas{background:#080d19;max-width:100%}
#game{display:none;background:#202943;padding:15px;border-radius:15px;margin-top:20px}
</style>
</head>
<body>
<header><h1>GAME ZONE</h1>Wybierz swoją grę!</header>
<main>
<div class="cards" id="menu">
<div class="card" onclick="start('snake')"><span>🐍</span><h3>Snake</h3></div>
<div class="card" onclick="start('tetris')"><span>🧱</span><h3>Tetris</h3></div>
<div class="card" onclick="start('flappy')"><span>🐤</span><h3>Flappy Bird</h3></div>
<div class="card" onclick="start('pong')"><span>🏓</span><h3>Ping Pong</h3></div>
<div class="card" onclick="start('mine')"><span>⛏️</span><h3>Minecraft 2D</h3></div>
</div>
<div id="game">
<button onclick="home()">← MENU</button>
<h2 id="title"></h2>
<p id="status"></p>
<div id="area"></div>
<div id="controls"></div>
</div>
</main>
<script>
let timer=null,handler=null;
const $=id=>document.getElementById(id);
function home(){
clearInterval(timer);
if(handler)document.removeEventListener('keydown',handler);
timer=null;handler=null;
$('game').style.display='none';
$('menu').style.display='grid';
$('area').innerHTML='';
$('controls').innerHTML='';
}
function start(g){
home();
$('menu').style.display='none';
$('game').style.display='block';
$('title').textContent=g.toUpperCase();
({snake,tetris,flappy,pong,mine})[g]();
}
function button(t,f){
let b=document.createElement('button');
b.textContent=t;b.onclick=f;$('controls').append(b);
}
function canvas(w,h){
let c=document.createElement('canvas');
c.width=w;c.height=h;$('area').append(c);
return [c,c.getContext('2d')];
}
function snake(){
let [c,x]=canvas(320,320),s=[{x:8,y:8}],d={x:1,y:0},food={x:12,y:8},score=0;
$('status').textContent='Punkty: 0';
function turn(a,b){if(a!==-d.x||b!==-d.y)d={x:a,y:b}}
handler=e=>{
if(e.key==='ArrowUp')turn(0,-1);
if(e.key==='ArrowDown')turn(0,1);
if(e.key==='ArrowLeft')turn(-1,0);
if(e.key==='ArrowRight')turn(1,0);
};
document.addEventListener('keydown',handler);
[['↑',0,-1],['↓',0,1],['←',-1,0],['→',1,0]].forEach(a=>button(a[0],()=>turn(a[1],a[2])));
timer=setInterval(()=>{
let h={x:s[0].x+d.x,y:s[0].y+d.y};
if(h.x<0||h.y<0||h.x>=20||h.y>=20||s.some(p=>p.x===h.x&&p.y===h.y)){
clearInterval(timer);$('status').textContent='Koniec gry! Wynik: '+score;return;
}
s.unshift(h);
if(h.x===food.x&&h.y===food.y){score++;food={x:Math.floor(Math.random()*20),y:Math.floor(Math.random()*20)}}
else s.pop();
x.fillStyle='#080d19';x.fillRect(0,0,320,320);
x.fillStyle='red';x.fillRect(food.x*16,food.y*16,15,15);
x.fillStyle='#50df91';s.forEach(p=>x.fillRect(p.x*16,p.y*16,15,15));
$('status').textContent='Punkty: '+score;
},140);
}
function tetris(){
let [c,x]=canvas(240,400),grid=Array.from({length:20},()=>Array(10).fill(0));
let shapes=[[[1,1,1,1]],[[1,1],[1,1]],[[0,1,0],[1,1,1]],[[1,0,0],[1,1,1]]],p;
function fresh(){p={a:shapes[Math.floor(Math.random()*shapes.length)].map(r=>r.slice()),x:3,y:0}}
function valid(px,py,a){return a.every((r,y)=>r.every((v,z)=>!v||(px+z>=0&&px+z<10&&py+y<20&&(py+y<0||!grid[py+y][px+z]))))}
function draw(){x.fillStyle='#080d19';x.fillRect(0,0,240,400);grid.forEach((r,y)=>r.forEach((v,z)=>{if(v){x.fillStyle='#8c70ff';x.fillRect(z*24,y*20,23,19)}}));p.a.forEach((r,y)=>r.forEach((v,z)=>{if(v){x.fillStyle='#40d9e8';x.fillRect((p.x+z)*24,(p.y+y)*20,23,19)}}))}
function rotate(){let a=p.a[0].map((_,i)=>p.a.map(r=>r[i]).reverse());if(valid(p.x,p.y,a))p.a=a}
function drop(){if(valid(p.x,p.y+1,p.a))p.y++;else{p.a.forEach((r,y)=>r.forEach((v,z)=>{if(v&&p.y+y>=0)grid[p.y+y][p.x+z]=1}));grid=grid.filter(r=>r.some(v=>!v));while(grid.length<20)grid.unshift(Array(10).fill(0));if(grid[0].some(v=>v)){clearInterval(timer);$('status').textContent='Koniec gry'}fresh()}draw()}
button('←',()=>{if(valid(p.x-1,p.y,p.a))p.x--;draw()});
button('Obróć',()=>{rotate();draw()});
button('→',()=>{if(valid(p.x+1,p.y,p.a))p.x++;draw()});
button('↓',drop);
handler=e=>{if(e.key==='ArrowLeft'&&valid(p.x-1,p.y,p.a))p.x--;if(e.key==='ArrowRight'&&valid(p.x+1,p.y,p.a))p.x++;if(e.key==='ArrowUp')rotate();if(e.key==='ArrowDown')drop();draw()};
document.addEventListener('keydown',handler);
fresh();draw();timer=setInterval(drop,550);
}
function flappy(){
let [c,x]=canvas(320,420),y=190,v=0,pipe=320,score=0,dead=false;
function flap(){if(dead){y=190;v=0;pipe=320;score=0;dead=false}else v=-5.5}
c.onclick=flap;
handler=e=>{if(e.code==='Space')flap()};
document.addEventListener('keydown',handler);
$('status').textContent='Dotknij ekranu lub spacji, aby skoczyć';
timer=setInterval(()=>{
if(dead)return;
v+=.28;y+=v;pipe-=3;if(pipe<-50){pipe=320;score++}
x.fillStyle='#101b35';x.fillRect(0,0,320,420);
x.fillStyle='#42d17b';x.fillRect(pipe,0,48,150);x.fillRect(pipe,275,48,145);
x.fillStyle='#ffd44d';x.beginPath();x.arc(75,y,13,0,7);x.fill();
$('status').textContent='Wynik: '+score;
if(y<0||y>420||(pipe<88&&pipe+48>62&&(y<150||y>275))){dead=true;$('status').textContent='Koniec gry! Dotknij, aby zagrać ponownie'}
},25);
}
function pong(){
let [c,x]=canvas(320,400),px=125,bx=160,by=200,vx=3,vy=3,score=0;
c.onpointermove=e=>{let r=c.getBoundingClientRect();px=Math.max(0,Math.min(250,(e.clientX-r.left)*320/r.width-35))};
handler=e=>{if(e.key==='ArrowLeft')px=Math.max(0,px-20);if(e.key==='ArrowRight')px=Math.min(250,px+20)};
document.addEventListener('keydown',handler);
timer=setInterval(()=>{
bx+=vx;by+=vy;if(bx<8||bx>312)vx=-vx;if(by<8)vy=-vy;
if(by>365&&by<380&&bx>px&&bx<px+70){vy=-Math.abs(vy);score++}
if(by>400){bx=160;by=200;score=0}
x.fillStyle='#080d19';x.fillRect(0,0,320,400);
x.fillStyle='white';x.fillRect(px,370,70,10);x.beginPath();x.arc(bx,by,8,0,7);x.fill();
$('status').textContent='Odbicia: '+score;
},20);
}
function mine(){
let [c,x]=canvas(320,320),blocks=[];
for(let y=0;y<10;y++)for(let z=0;z<10;z++)blocks.push({x:z,y,t:y<3?0:y<6?1:2});
function draw(){x.clearRect(0,0,320,320);blocks.forEach(b=>{x.fillStyle=['#65bd55','#9b7048','#777b88'][b.t];x.fillRect(b.x*32+1,b.y*32+1,30,30);x.strokeStyle='#263247';x.strokeRect(b.x*32+1,b.y*32+1,30,30)})}
c.onclick=e=>{let r=c.getBoundingClientRect(),z=Math.floor((e.clientX-r.left)*320/r.width/32),y=Math.floor((e.clientY-r.top)*320/r.height/32),i=blocks.findIndex(b=>b.x===z&&b.y===y);if(i>=0){blocks.splice(i,1);$('status').textContent='Wydobyte bloki: '+(100-blocks.length);draw()}};
$('status').textContent='Klikaj bloki, aby je wydobywać';draw();
}
</script>
</body>
</html>
