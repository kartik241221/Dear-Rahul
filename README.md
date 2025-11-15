<html lang="en">
let i=0;
function step(){
if(i<=text.length){
typingEl.textContent = text.slice(0,i);
i++;
setTimeout(step,28);
}
}
step();
}
typeText(message);


document.getElementById('openWish').addEventListener('click', ()=>{
document.getElementById('popup').style.display='flex';
document.getElementById('finalMsg').textContent = finalText;
celebrate();
});


const canvas=document.getElementById('confetti');
const ctx=canvas.getContext('2d');
let W=canvas.width=innerWidth;
let H=canvas.height=innerHeight;


const confetti=[];
function spawn(n){
for(let i=0;i<n;i++){
confetti.push({x:Math.random()*W,y:Math.random()*H,vx:(Math.random()*4)-2,vy:(Math.random()*-8),r:5+Math.random()*5,color:`hsl(${Math.random()*360} 80% 60%)`});
}
}


function draw(){
ctx.clearRect(0,0,W,H);
confetti.forEach((p,i)=>{
p.x+=p.vx;
p.y+=p.vy;
p.vy+=0.1;
ctx.fillStyle=p.color;
ctx.fillRect(p.x,p.y,p.r,p.r);
if(p.y>H) confetti.splice(i,1);
});
requestAnimationFrame(draw);
}
draw();


function celebrate(){ spawn(150); }


window.addEventListener('resize',()=>{
W=canvas.width=innerWidth;
H=canvas.height=innerHeight;
});
</script>


<div class="floaters">
<div class="float">🔥</div>
<div class="float">💙</div>
<div class="float">✨</div>
</div>


<div class="sparkles"></div>


</body>
</html>
