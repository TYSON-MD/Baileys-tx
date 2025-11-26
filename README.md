
<!-- 🚀 TYSON MD - Enhanced Baileys Library -->
<div align="center" style="margin-bottom: 25px;">
    <h1 style="font-size: 28px; margin-bottom: 10px;">🚀 TYSON MD - Enhanced Baileys Library</h1>
</div>

<!-- Logo -->
<div align="center" style="margin-bottom: 20px;">
    <img src="https://files.catbox.moe/2gzoau.jpg" width="200" alt="TYSON MD Logo" />
</div>

<!-- Title Section -->
<div align="center" style="margin-bottom: 30px;">
    ✨ <b>𝐁𝐚𝐲𝐥𝐞𝐬 𝐋𝐢𝐛𝐫𝐚𝐫𝐲 𝐄𝐧𝐡𝐚𝐧𝐜𝐞𝐝 • مـكـتـبـة بـايـلـيـز الـمـعـدله</b> ✨
    <br>
    <em>𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐝 𝐛𝐲 • تـم الـتـطـويـر بـواسـطـة</em> <b>𝐓𝐘𝐒𝐎𝐍-𝐌𝐃</b>
</div>

<!-- Main GIF -->
<div align="center" style="margin-bottom: 10px;">
    <img src="https://i.imgur.com/tKXq7jt.gif" width="450" />
</div>

<!-- Moving Strip -->
<div align="center" style="margin-bottom: 30px;">
    <img src="https://i.imgur.com/3ZQ3ZQp.gif" width="400" alt="animated strip" />
</div>

<!-- Short Description -->
<div align="center" style="max-width: 500px; font-size: 15px; margin-bottom: 40px;">
    🔹 استقرار أعلى <br>
    🔹 دعم تسجيل الدخول الثنائي <br>
    🔹 أداء أقوى <br>
    🔹 سرعة في معالجة الرسائل
</div>

---

## 🛠️ 𝐅𝐢𝐱𝐞𝐝 𝐈𝐬𝐬𝐮𝐞𝐬 • الـمـشـاكـل الـمحـلوله

· 🔧 **lid** - إصلاحات الاتصال الأساسية  
· 🔐 **Sessions** - دعم الجلسات والمصادقة المزدوجة  
&nbsp;&nbsp;&nbsp;· 📱 تسجيل الدخول QR  
&nbsp;&nbsp;&nbsp;· 🔢 تسجيل الدخول بكود 8 أرقام  

---

## 🌟 𝐄𝐧𝐡𝐚𝐧𝐜𝐞𝐝 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬 • الـمـيـزات الـمـحـسـنـة

· ⚡ أداء محسن للمجموعات  
· 🎭 دعم كامل للوسائط  
· 🔄 إدارة متقدمة للجلسات  

---

## 📥 𝐇𝐨𝐰 𝐭𝐨 𝐔𝐩𝐝𝐚𝐭𝐞 • كـيـفـيـة الـتـحـديـث

**package.json**
```json
{
  "dependencies": {
    "@whiskeysockets/Baileys": "github:TYSON-MD/Baileys-tx"
  }
}

Installation

npm install @whiskeysockets/Baileys@github:TYSON-MD/Baileys-tx


---

🔗 𝐂𝐨𝐧𝐧𝐞𝐜𝐭𝐢𝐨𝐧 𝐌𝐞𝐭𝐡𝐨𝐝𝐬 • طرق الاتصال

📱 QR-CODE Login

const { default: makeWASocket, Browsers } = require("@whiskeysockets/Baileys")

const sock = makeWASocket({
    browser: Browsers.ubuntu('My App • تطبيقي'),
    printQRInTerminal: true
})

🔢 Pairing Code

const sock = makeWASocket({ printQRInTerminal: false })

if (!sock.authState.creds.registered) {
    const number = 'XXXXXXXXXXX'
    const code = await sock.requestPairingCode(number)
    console.log('🔑 كود الاقتران:', code)
}


---

💾 𝐒𝐞𝐬𝐬𝐢𝐨𝐧 𝐒𝐭𝐨𝐫𝐚𝐠𝐞 • حفظ الجلسات

const { useMultiFileAuthState } = require("@whiskeysockets/Baileys")

const { state, saveCreds } = await useMultiFileAuthState('auth_info_baileys')
const sock = makeWASocket({ auth: state })

sock.ev.on('creds.update', saveCreds)


---

📨 𝐌𝐞𝐬𝐬𝐚𝐠𝐞 𝐇𝐚𝐧𝐝𝐥𝐢𝐧𝐠 • التعامل مع الرسائل

sock.ev.on('messages.upsert', ({ messages }) => {
    for (const message of messages) {
        console.log('📩 رسالة جديدة:', message)
        await sock.sendMessage(message.key.remoteJid, { 
            text: '🎯 تم الاستلام!' 
        })
    }
})


---

👑 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫 • المطور

const TYSON_MD = {
  "Creator": "TYSON MD",
  "Whatsapp": "https://wa.me/201515378259",
  "GitHub": "github.com./TYSON-MD/Baileys-tx",
  "Version": "Enhanced Edition"
};


---

<div align="center" style="margin-top: 30px;">
<b>🎯 𝐓𝐘𝐒𝐎𝐍 𝐌𝐃 - Powerful WhatsApp Bot Library 🚀</b><br>
<em>مكتبة بوتات واتساب مطوّرة</em>
</div>
```
