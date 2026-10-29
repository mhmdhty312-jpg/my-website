
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#07111c">
<title>MLK RADIO - اتصال صوتي</title>
<style>
:root{
 --bg:#07111c;--panel:#102131;--green:#42f5a6;
 --blue:#47c8ff;--text:#eff8ff;--muted:#92aaba;
 --red:#ff536c;
}
*{box-sizing:border-box}
body{
 margin:0;background:radial-gradient(ellipse at top,#193d4d,transparent 55%),var(--bg);
 color:var(--text);font-family:Arial,Tahoma,sans-serif;min-height:100vh
}
button,input{font:inherit}
button{cursor:pointer}
.app{max-width:480px;margin:auto;padding:18px 15px 30px}
header{display:flex;justify-content:space-between;align-items:center;gap:10px}
.brand{display:flex;align-items:center;gap:10px}
.logo{width:48px;height:48px;display:grid;place-items:center;
 border-radius:15px;background:#42f5a615;border:1px solid #42f5a155;font-size:25px}
h1{font-size:19px;margin:0}
h1 span{color:var(--green)}
.sub{font-size:11px;color:var(--muted);margin-top:5px}
.status{font-size:10px;color:var(--muted)}
.dot{display:inline-block;width:7px;height:7px;border-radius:50%;background:#e6b45d;margin-left:5px}
.dot.on{background:var(--green);box-shadow:0 0 9px var(--green)}
.banner{margin:20px 0;padding:12px;border-radius:12px;
 border:1px solid #47c8ff35;background:#47c8ff0b;
 font-size:12px;line-height:1.8;color:#b9d9eb}
.card{background:linear-gradient(145deg,#122535,#0c1925);
 border:1px solid #ffffff13;border-radius:18px;padding:16px;margin-top:13px}
.kicker{font-size:11px;color:var(--green)}
h2{font-size:16px;margin:7px 0}
label{display:block;color:#b5c9d6;font-size:12px;margin:15px 0 8px}
input{width:100%;background:#07131e;color:white;border:1px solid #ffffff20;
 border-radius:10px;padding:13px;outline:none}
input:focus{border-color:var(--green)}
input::placeholder{color:#607989}
.ltr{direction:ltr;text-align:center}
.row{display:flex;gap:8px;align-items:center}
.row input{flex:1;min-width:0}
.btn{border:1px solid transparent;border-radius:10px;padding:12px;font-size:12px;font-weight:bold}
.primary{background:linear-gradient(120deg,#2cda91,#6bffc2);color:#05271a}
.ghost{background:#ffffff09;color:white;border-color:#ffffff20}
.secondary{background:#47c8ff0d;color:#9ce2ff;border-color:#47c8ff45}
.danger{background:#ff536c15;color:#ff8b9b;border-color:#ff536c55}
.full{width:100%;margin-top:12px}
.hint{font-size:11px;color:var(--muted);line-height:1.8}
.identity{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-top:12px}
.serial{font-size:29px;letter-spacing:3px;direction:ltr;color:var(--green);margin-top:8px}
.radio{text-align:center}
.visual{width:165px;height:165px;margin:15px auto;position:relative;display:grid;place-items:center}
.ring{position:absolute;inset:0;border:1px solid #42f5a135;border-radius:50%}
.ring.two{inset:14px;border-color:#42f5a155}
.core{width:105px;height:105px;border-radius:50%;display:grid;place-items:center;
 font-size:40px;background:radial-gradient(circle at 35% 25%,#276452,#102a32);
 border:2px solid #42f5a177;box-shadow:0 0 25px #42f5a11a}
.radio.active .ring.one{animation:pulse 1.4s infinite}
@keyframes pulse{0%{transform:scale(.85);opacity:1}100%{transform:scale(1.18);opacity:0}}
.ptt{width:140px;height:140px;border-radius:50%;border:5px solid #ffffff20;
 background:linear-gradient(145deg,#39e99b,#0da66b);color:#05271a;
 display:flex;flex-direction:column;justify-content:center;align-items:center;
 gap:7px;margin:18px auto 12px;touch-action:none;user-select:none}
.ptt span{font-size:27px}.ptt b{font-size:14px}.ptt small{font-size:10px}
.ptt.talking{background:linear-gradient(145deg,#ff7589,#d52b4b);color:white}
button:disabled{opacity:.4;cursor:not-allowed}
.contacts{display:grid;gap:8px;margin-top:12px}
.contact{display:flex;align-items:center;gap:9px;padding:10px;
 border:1px solid #ffffff12;border-radius:12px}
.avatar{width:38px;height:38px;border-radius:12px;background:#47c8ff18;
 display:grid;place-items:center}
.info{flex:1;min-width:0}.name{font-size:13px;font-weight:bold}
.cid{font-size:11px;color:var(--muted);direction:ltr;text-align:right;margin-top:5px}
.empty{text-align:center;color:var(--muted);font-size:12px;padding:16px}
footer{text-align:center;color:#637e90;font-size:10px;margin-top:24px;line-height:2}
dialog{background:#102131;color:white;border:1px solid #42f5a155;
 border-radius:18px;max-width:350px;width:90%;text-align:center;padding:22px}
dialog::backdrop{background:#000b}
</style>
</head>
<body>
<main class="app">
<header>
 <div class="brand">
  <div class="logo">📡</div>
  <div><h1>MLK <span>RADIO</span></h1><div class="sub">شبكة الاتصال الصوتي</div></div>
 </div>
 <div class="status"><i class="dot" id="dot"></i><span id="status">غير متصل</span></div>
</header>

<div class="banner">
 📡 جهاز لاسلكي رقمي — اتصل بالأصدقاء عبر الإنترنت باستخدام الصوت الحقيقي.
 يتطلب تشغيل الخادم وإعداد HTTPS للسماح بالميكروفون.
</div>

<section class="card">
 <div class="kicker">هويتك الرقمية</div>
 <div class="identity">
  <div><div class="sub">رقمك التسلسلي</div><div class="serial" id="myId">--------</div></div>
  <button class="btn ghost" id="copy">نسخ الرقم</button>
 </div>
 <p class="hint">شارك رقمك مع الشخص الذي تريد الاتصال به.</p>
</section>

<section class="card">
 <div class="kicker">اتصال مباشر</div><h2>من تريد الاتصال به؟</h2>
 <label for="target">الرقم التسلسلي للشخص</label>
 <div class="row">
  <input id="target" class="ltr" maxlength="8" inputmode="numeric" placeholder="12345678">
  <button class="btn primary" id="call">اتصال</button>
 </div>
 <p class="hint" id="message">يجب أن يكون الشخص الآخر متصلًا بالموقع.</p>
</section>

<section class="card radio" id="radio">
 <div class="kicker">جهاز التحدث</div>
 <div class="visual"><div class="ring one"></div><div class="ring two"></div>
  <div class="core">🎙️</div></div>
 <h2 id="radioTitle">جاهز للاتصال</h2>
 <p class="hint" id="radioSub">اتصل بشخص أولًا</p>
 <button id="ptt" class="ptt" disabled>
  <span>🎙️</span><b>اضغط للتحدث</b><small>اترك الزر لإيقاف الصوت</small>
 </button>
 <button class="btn danger" id="hangup" disabled>إنهاء الاتصال</button>
 <p class="hint">يُرسل الميكروفون الصوت فقط أثناء الضغط على زر التحدث.</p>
</section>

<section class="card">
 <div class="kicker">دفتر الأرقام</div><h2>جهات الاتصال</h2>
 <label for="personName">اسم الشخص</label>
 <input id="personName" maxlength="35" placeholder="اسم الصديق">
 <label for="personId">الرقم التسلسلي</label>
 <input id="personId" class="ltr" maxlength="8" inputmode="numeric" placeholder="8 أرقام">
 <button class="btn secondary full" id="add">＋ حفظ جهة الاتصال</button>
 <div id="contacts" class="contacts"></div>
</section>
<footer>MLK RADIO · نسخة ويب أولية<br>لا تستخدمه للطوارئ</footer>
</main>

<dialog id="incoming">
 <div style="font-size:35px">📡</div><h2>اتصال وارد</h2>
 <p>المستخدم <b id="caller"></b> يريد التحدث معك.</p>
 <div class="row"><button class="btn ghost" id="decline">رفض</button>
 <button class="btn primary" id="accept">قبول الاتصال</button></div>
</dialog>

<audio id="remoteAudio" autoplay playsinline></audio>
<script src="/socket.io/socket.io.js"></script>
<script>
/*
  هذا الملف يحتاج إلى server.js من المشروع.
  فتحه كملف منفرد لن ينشئ خادم اتصال صوتي.
*/
const $=id=>document.getElementById(id);
const socket=io();
let myId="", pc=null, stream=null, peer="", incoming=null;
let contacts=[];
try{contacts=JSON.parse(localStorage.getItem("mlk_contacts")||"[]")}catch{}

const rtcConfig={iceServers:[
 {urls:"stun:stun.l.google.com:19302"}
 // أضف TURN server موثوقًا عند النشر لتحسين الاتصال خلف بعض الشبكات.
]};
function status(t,ok=false){$("status").textContent=t;$("dot").classList.toggle("on",ok)}
function message(t){$("message").textContent=t}
function radio(t,s){$("radioTitle").textContent=t;$("radioSub").textContent=s}
function drawContacts(){
 const box=$("contacts");box.replaceChildren();
 if(!contacts.length){const e=document.createElement("div");e.className="empty";e.textContent="لا توجد جهات اتصال محفوظة.";box.append(e);return}
 contacts.forEach(c=>{
  const row=document.createElement("div");row.className="contact";
  const av=document.createElement("div");av.className="avatar";av.textContent="👤";
  const info=document.createElement("div");info.className="info";
  const name=document.createElement("div");name.className="name";name.textContent=c.name;
  const id=document.createElement("div");id.className="cid";id.textContent=c.id;
  info.append(name,id);
  const call=document.createElement("button");call.className="btn secondary";call.textContent="اتصال";
  call.onclick=()=>{$("target").value=c.id;startCall(c.id)};
  const del=document.createElement("button");del.className="btn ghost";del.textContent="×";
  del.onclick=()=>{contacts=contacts.filter(x=>x.id!==c.id);saveContacts();drawContacts()};
  row.append(av,info,call,del);box.append(row);
 });
}
function saveContacts(){localStorage.setItem("mlk_contacts",JSON.stringify(contacts))}
async function microphone(){
 if(!navigator.mediaDevices?.getUserMedia)throw Error("الميكروفون يحتاج إلى HTTPS أو localhost.");
 if(!stream){
  stream=await navigator.mediaDevices.getUserMedia({audio:{
   echoCancellation:true,noiseSuppression:true,autoGainControl:true},video:false});
  stream.getAudioTracks().forEach(t=>t.enabled=false);
 }
 return stream;
}
async function makePeer(target){
 pc=new RTCPeerConnection(rtcConfig);
 const s=await microphone();
 s.getTracks().forEach(t=>pc.addTrack(t,s));
 pc.onicecandidate=e=>{if(e.candidate)socket.emit("ice-candidate",{target,candidate:e.candidate})};
 pc.ontrack=e=>{$("remoteAudio").srcObject=e.streams[0];$("remoteAudio").play().catch(()=>message("المس الشاشة لتشغيل الصوت الوارد."))};
 pc.onconnectionstatechange=()=>{
  if(!pc)return;
  if(pc.connectionState==="connected"){
   peer=target;$("ptt").disabled=false;$("hangup").disabled=false;
   radio("متصل الآن","رقم الطرف الآخر: "+target);message("تم ربط الصوت الحقيقي.");
  }
  if(["failed","closed"].includes(pc.connectionState))endCall(false,"انقطع الاتصال. تحقق من الشبكة وTURN.");
 };
 return pc;
}
async function startCall(target){
 if(!/^\d{8}$/.test(target))return alert("أدخل رقمًا من 8 أرقام.");
 if(target===myId)return alert("لا يمكنك الاتصال بنفسك.");
 if(!socket.connected)return alert("خادم الإشارات غير متصل.");
 if(pc)return alert("أنه الاتصال الحالي أولًا.");
 try{
  peer=target;message("جارٍ طلب إذن الميكروفون...");
  await makePeer(target);
  const offer=await pc.createOffer();
  await pc.setLocalDescription(offer);
  socket.emit("call-user",{target,offer:pc.localDescription});
  radio("جارٍ الاتصال...", "في انتظار قبول الطرف الآخر");
  message("تم إرسال طلب الاتصال.");
 }catch(e){endCall(false,"تعذر الاتصال: "+e.message);alert(e.message)}
}
async function acceptCall(){
 if(!incoming)return;
 const data=incoming;
 try{
  peer=data.from;
  await makePeer(data.from);
  await pc.setRemoteDescription(new RTCSessionDescription(data.offer));
  const answer=await pc.createAnswer();
  await pc.setLocalDescription(answer);
  socket.emit("call-answer",{target:data.from,answer:pc.localDescription});
  incoming=null;$("incoming").close();
  radio("جارٍ ربط الصوت...","مع الرقم: "+peer);
 }catch(e){endCall(false,e.message);alert(e.message)}
}
function stopTalking(){
 if(stream)stream.getAudioTracks().forEach(t=>t.enabled=false);
 $("ptt").classList.remove("talking");$("radio").classList.remove("active");
 if(pc&&peer)radio("متصل الآن","رقم الطرف الآخر: "+peer);
}
async function startTalking(e){
 e.preventDefault();
 if(!pc||pc.connectionState!=="connected"){message("انتظر حتى يكتمل اتصال الصوت.");return}
 try{
  await microphone();
  stream.getAudioTracks().forEach(t=>t.enabled=true);
  $("ptt").classList.add("talking");$("radio").classList.add("active");
  radio("أنت تتحدث الآن","اترك الزر لإيقاف إرسال الصوت");
 }catch(e){alert("تعذر تشغيل الميكروفون: "+e.message)}
}
function endCall(notify=true,text="تم إنهاء الاتصال."){
 if(notify&&peer)socket.emit("hangup",{target:peer});
 stopTalking();
 if(pc){pc.onicecandidate=null;pc.close()}
 pc=null;peer="";
 if(stream){stream.getTracks().forEach(t=>t.stop());stream=null}
 $("remoteAudio").srcObject=null;
 $("ptt").disabled=true;$("hangup").disabled=true;
 $("radio").classList.remove("active");
 radio("جاهز للاتصال","اتصل بشخص أولًا");message(text);
}
socket.on("connect",()=>status("متصل بالخادم",true));
socket.on("disconnect",()=>{status("انقطع الاتصال",false);if(pc)endCall(false,"انقطع اتصال الخادم.")});
socket.on("registered",d=>{myId=d.serial;$("myId").textContent=myId});
socket.on("online-count",n=>{});
socket.on("call-error",message);
socket.on("incoming-call",d=>{
 if(pc){socket.emit("hangup",{target:d.from});return}
 incoming=d;$("caller").textContent=d.from;$("incoming").showModal();
});
socket.on("call-answered",async d=>{
 if(!pc||d.from!==peer)return;
 try{await pc.setRemoteDescription(new RTCSessionDescription(d.answer))}
 catch(e){endCall(false,"تعذر إكمال الاتصال: "+e.message)}
});
socket.on("ice-candidate",async d=>{
 if(!pc||d.from!==peer)return;
 try{await pc.addIceCandidate(new RTCIceCandidate(d.candidate))}catch(e){console.warn(e)}
});
socket.on("peer-hangup",d=>{if(d.from===peer)endCall(false,"أنهى الطرف الآخر الاتصال.")});
socket.on("user-offline",d=>{if(d.serial===peer)endCall(false,"غادر الطرف الآخر الموقع.")});

$("call").onclick=()=>startCall($("target").value.trim());
$("copy").onclick=async()=>{
 try{await navigator.clipboard.writeText(myId);$("copy").textContent="تم النسخ ✓"}
 catch{prompt("انسخ رقمك:",myId)}
};
$("add").onclick=()=>{
 const name=$("personName").value.trim(),id=$("personId").value.trim();
 if(!name)return alert("اكتب اسم الشخص.");
 if(!/^\d{8}$/.test(id))return alert("أدخل رقمًا من 8 أرقام.");
 if(id===myId)return alert("هذا رقمك الشخصي.");
 if(contacts.some(c=>c.id===id))return alert("هذا الرقم محفوظ.");
 contacts.push({name,id});saveContacts();drawContacts();
 $("personName").value="";$("personId").value="";
};
$("accept").onclick=acceptCall;
$("decline").onclick=()=>{
 if(incoming)socket.emit("hangup",{target:incoming.from});
 incoming=null;$("incoming").close();
};
$("hangup").onclick=()=>endCall(true);
$("ptt").addEventListener("pointerdown",startTalking);
["pointerup","pointercancel","pointerleave","lostpointercapture"].forEach(ev=>$("ptt").addEventListener(ev,stopTalking));
window.addEventListener("blur",stopTalking);
document.addEventListener("visibilitychange",()=>{if(document.hidden)stopTalking()});
drawContacts();
</script>
</body>
</html>
