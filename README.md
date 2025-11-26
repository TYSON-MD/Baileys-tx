🚀 TYSON MD – Enhanced Baileys Library

<div align="center">
<img src="https://files.catbox.moe/2gzoau.jpg" width="200" alt="TYSON MD Logo" />
</div><div align="center">
<img src="https://i.imgur.com/AAQz4yN.gif" width="600" />
</div><p align="center">
<b>Modern • Stable • Fast • Enhanced</b><br>
مكتبة بايلز معدلة ومحسّنة لبناء أقوى بوتات واتساب
</p><div align="center">
<img src="https://i.imgur.com/1Q9Z1Zm.gif" width="400" />
</div>
---

✨ Overview • نظرة عامة

<div align="center">
<img src="https://i.imgur.com/tKXq7jt.gif" width="650" />
</div>Baileys-TX هي نسخة مطوّرة من مكتبة Baileys الشهيرة الخاصة بالتعامل مع WhatsApp Multi-Device.
تم تحسينها لضمان:

استقرار أعلى

دعم تسجيل الدخول الثنائي

أداء أقوى

أسرع في معالجة الرسائل



---

<div align="center">
<img src="https://i.imgur.com/wv3sLrC.gif" width="600" />
</div>

---

🛠️ Fixed Issues • المشكلات التي تم حلها

<div align="center">
<img src="https://i.imgur.com/DM7Rk8p.gif" width="450" />
</div>🔧 تحسينات الاتصال الأساسي

🔐 دعم تسجيل الدخول الثنائي

🎭 دعم كامل للوسائط

🔄 إصلاحات الجلسات

⚙️ تحسين سرعة الأحداث



---

🌟 Enhanced Features • المميزات المحسّنة

<div align="center">
<img src="https://i.imgur.com/5O72Uvn.gif" width="500" />
</div>أداء عالي للمجموعات

إرسال واستقبال كل أنواع الوسائط

إدارة الجلسات

تحديثات سريعة

متوافق مع Node.js



---

📦 Installation

<div align="center">
<img src="https://i.imgur.com/kd9zvNW.gif" width="300" />
</div>{
  "dependencies": {
    "@whiskeysockets/Baileys": "github:TYSON-MD/Baileys-tx"
  }
}

npm install @whiskeysockets/Baileys@github:TYSON-MD/Baileys-tx


---

🔗 Connection Examples

<div align="center">
<img src="https://i.imgur.com/CtaTIqm.gif" width="500" />
</div>🔹 QR Login

const { default: makeWASocket, Browsers } = require("@whiskeysockets/Baileys")

const sock = makeWASocket({
    browser: Browsers.ubuntu('MyApp'),
    printQRInTerminal: true
})

🔹 8-Digit Login

if (!sock.authState.creds.registered) {
    const number = '2015XXXXXXXX'
    const code = await sock.requestPairingCode(number)
    console.log('Pairing Code:', code)
}


---

💾 Sessions

const { useMultiFileAuthState } = require("@whiskeysockets/Baileys")

const { state, saveCreds } = await useMultiFileAuthState('auth_info_baileys')
const sock = makeWASocket({ auth: state })

sock.ev.on('creds.update', saveCreds)


---

📨 Message Handler

sock.ev.on('messages.upsert', async ({ messages }) => {
    for (const msg of messages) {
        await sock.sendMessage(msg.key.remoteJid, { text: "تم الاستلام ✔" })
    }
})


---

<div align="center">
<img src="https://i.imgur.com/zQIgDyb.gif" width="650" />
</div>
---

👑 Developer

const TYSON_MD = {
  Developer: "TYSON MD",
  WhatsApp: "https://wa.me/201515378259",
  GitHub: "https://github.com/TYSON-MD",
  Version: "Enhanced Edition"
}


---

<div align="center">
<img src="https://i.imgur.com/btP0MXL.gif" width="600" /><h2>🔥 TYSON MD – Advanced WhatsApp Bot Library 🔥</h2>
<b>Powered with Style — تم تصميمه بواسطه 3lilio ✨</b>
</div>
---
