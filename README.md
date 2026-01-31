<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Avukatlık Ajansı | Kurumsal</title>
<style>
  body {margin:0; font-family:Arial,sans-serif; background:#f5f6f8; padding:20px;}
  header {background:#0f172a; color:#fff; padding:15px; border-radius:10px;}
  .lang {display:flex; gap:10px; justify-content:flex-end;}
  .lang button {padding:6px 12px; border-radius:6px; border:1px solid #ccc; cursor:pointer; background:#fff;}
  h1 {font-size:28px; margin-bottom:10px;}
  h2 {margin-top:20px;}
  ul {padding-left:20px;}
  .btn {margin-top:20px; padding:10px 16px; background:#0f172a; color:#fff; border:none; border-radius:8px; cursor:pointer;}
  @media (max-width:768px) {
    h1 {font-size:22px;}
  }
</style>
</head>
<body>

<header>
  <div class="lang">
    <button onclick="setLang('tr')">TR</button>
    <button onclick="setLang('en')">EN</button>
    <button onclick="setLang('fr')">FR</button>
    <button onclick="setLang('ar')">AR</button>
  </div>
</header>

<main>
  <div id="content"></div>
  <button id="mailBtn" class="btn">Dosyayı Mail ile Gönder</button>
</main>

<script>
const data = {
  tr:{title:"Güvenilir Hukuki Çözümler",subtitle:"Profesyonel ve Etik Avukatlık Hizmetleri",
  about:"Müvekkillerimize yerel ve uluslararası alanda profesyonel hukuki danışmanlık sunuyoruz.",
  services:["Ceza Hukuku","Ticaret Hukuku","Aile Hukuku","Şirket Danışmanlığı"],
  btn:"İletişime Geç"},
  en:{title:"Trusted Legal Solutions",subtitle:"Professional & Ethical Legal Services",
  about:"We provide professional legal consultancy at local and international levels.",
  services:["Criminal Law","Commercial Law","Family Law","Corporate Advisory"],
  btn:"Contact Us"},
  fr:{title:"Solutions Juridiques Fiables",subtitle:"Services Juridiques Professionnels et Éthiques",
  about:"Nous offrons des services juridiques professionnels au niveau local et international.",
  services:["Droit Pénal","Droit Commercial","Droit de la Famille","Conseil aux Entreprises"],
  btn:"Nous Contacter"},
  ar:{title:"حلول قانونية موثوقة",subtitle:"خدمات قانونية مهنية وأخلاقية",
  about:"نقدم استشارات قانونية مهنية على المستوى المحلي والدولي.",
  services:["القانون الجنائي","القانون التجاري","قانون الأسرة","استشارات الشركات"],
  btn:"اتصل بنا"}
};

function setLang(l){
  const c = data[l];
  document.documentElement.lang = l;
  document.body.dir = l==='ar'?'rtl':'ltr';
  document.getElementById('content').innerHTML = `
    <h1>${c.title}</h1>
    <p>${c.subtitle}</p>
    <h2>Hakkımızda</h2>
    <p>${c.about}</p>
    <h2>Hizmetlerimiz</h2>
    <ul>${c.services.map(s=>`<li>${s}</li>`).join('')}</ul>
    <button class="btn">${c.btn}</button>
  `;
}

// Başlangıçta Fransızca
setLang('fr');

// Mail Gönder Butonu
document.getElementById('mailBtn').addEventListener('click',()=>{
  const email = 'Erdogankaya713@gmail.com';
  const subject = 'Avukatlık Sitesi Dosyaları';
  const body = 'Merhaba,\n\nEkli zip dosyasını indirerek siteyi görebilirsin.\n\nLink: https://sandbox:/mnt/data/LawFirmSite_Package.zip';
  window.location.href = `mailto:${email}?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
});
</script>

</body>
</html>
