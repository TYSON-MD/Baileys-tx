🚀 TYSON MD - Enhanced Baileys Library

<div align="center">
<img src="https://files.catbox.moe/2gzoau.jpg" width="200" alt="TYSON MD Logo" />
</div>

<div align="center">
✨ <b>Bayles-tx 𝐋𝐢𝐛𝐫𝐚𝐫𝐲 𝐄𝐧𝐡𝐚𝐧𝐜𝐞𝐝 • مـكـتـبـة بـايـلـيـز الـمـعـدله</b> ✨
<br>
<em>𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐝 𝐛𝐲 • تـم الـتـطـويـر بـواسـطـة</em> <b>𝐓𝐘𝐒𝐎𝐍-𝐌𝐃</b>
</div>


<div style="max-width: 500px; text-align: center; font-size: 15px;">
🔹 استقرار أعلى  
🔹 دعم تسجيل الدخول الثنائي  
🔹 أداء أقوى  
🔹 سرعة في معالجة الرسائل  
</div>

</div>

🛠️ 𝐅𝐢𝐱𝐞𝐝 𝐈𝐬𝐬𝐮𝐞𝐬 • الـمـشـاكـل الـمحـلوله

· 🔧 lid - 𝐂𝐨𝐫𝐞 𝐜𝐨𝐧𝐧𝐞𝐜𝐭𝐢𝐨𝐧 𝐟𝐢𝐱𝐞𝐬 • إصـلاحـات الاتـصـال الأسـاسـيـة
· 🔐 𝐒𝐞𝐬𝐬𝐢𝐨𝐧𝐬 • الجـلـسـات - 𝐃𝐮𝐚𝐥 𝐚𝐮𝐭𝐡𝐞𝐧𝐭𝐢𝐜𝐚𝐭𝐢𝐨𝐧 𝐬𝐮𝐩𝐩𝐨𝐫𝐭 • دعـم المـصـادقـة المـزدوجـة:
  · 📱 𝐐𝐑 𝐜𝐨𝐝𝐞 𝐥𝐨𝐠𝐢𝐧 • تسـجـيـل الـدخـول بـرمـز QR
  · 🔢 𝟖-𝐝𝐢𝐠𝐢𝐭 𝐜𝐨𝐝𝐞 𝐥𝐨𝐠𝐢𝐧 • تسـجـيـل الـدخـول بـرمـز 8 أرقـام

🌟 𝐄𝐧𝐡𝐚𝐧𝐜𝐞𝐝 𝐅𝐞𝐚𝐭𝐮𝐫𝐞𝐬 • الـمـيـزات الـمـحـسـنـة

· ⚡ 𝐈𝐦𝐩𝐫𝐨𝐯𝐞𝐝 𝐠𝐫𝐨𝐮𝐩 𝐩𝐞𝐫𝐟𝐨𝐫𝐦𝐚𝐧𝐜𝐞 • أداء محـسـن للمجـمـوعـات
· 🎭 𝐅𝐮𝐥𝐥 𝐦𝐞𝐝𝐢𝐚 𝐬𝐮𝐩𝐩𝐨𝐫𝐭 • دعـم كـامـل للـوسـائـط
· 🔄 𝐀𝐝𝐯𝐚𝐧𝐜𝐞𝐝 𝐬𝐞𝐬𝐬𝐢𝐨𝐧 𝐦𝐚𝐧𝐚𝐠𝐞𝐦𝐞𝐧𝐭 • إدارة متقـدمـة للجـلـسـات

📥 𝐇𝐨𝐰 𝐭𝐨 𝐔𝐩𝐝𝐚𝐭𝐞 • كـيـفـيـة الـتـحـديـث

في ملف package.json:

```json
{
  "dependencies": {
    "@whiskeysockets/Baileys": "github:TYSON-MD/Baileys-tx"
  }
}
```

🔧 𝐈𝐧𝐬𝐭𝐚𝐥𝐥𝐚𝐭𝐢𝐨𝐧 • الـتـثـبـيـت

```bash
npm install @whiskeysockets/Baileys@github:TYSON-MD/Baileys-tx
```

```javascript
const { default: makeWASocket } = require("@whiskeysockets/Baileys")
```

🔗 𝐂𝐨𝐧𝐧𝐞𝐜𝐭𝐢𝐨𝐧 𝐌𝐞𝐭𝐡𝐨𝐝𝐬 • طـرق الاتـصـال

📱 𝐔𝐬𝐢𝐧𝐠 𝐐𝐑-𝐂𝐎𝐃𝐄 • بـاسـتـخـدام رمـز QR

```javascript
const { default: makeWASocket, Browsers } = require("@whiskeysockets/Baileys")

const sock = makeWASocket({
    browser: Browsers.ubuntu('𝐌𝐲 𝐀𝐩𝐩 • تـطـبـيـقـي'),
    printQRInTerminal: true
})
```

🔢 𝐔𝐬𝐢𝐧𝐠 𝐏𝐚𝐢𝐫𝐢𝐧𝐠 𝐂𝐨𝐝𝐞 • بـاسـتـخـدام رمـز الاقـتـران

```javascript
const sock = makeWASocket({
    printQRInTerminal: false
})

if (!sock.authState.creds.registered) {
    const number = 'XXXXXXXXXXX'
    const code = await sock.requestPairingCode(number)
    console.log('🔑 𝐏𝐚𝐢𝐫𝐢𝐧𝐠 𝐂𝐨𝐝𝐞 • كـود الاقـتـران:', code)
}
```

💾 𝐒𝐞𝐬𝐬𝐢𝐨𝐧 𝐒𝐭𝐨𝐫𝐚𝐠𝐞 • حـفـظ الجـلـسـات

```javascript
const { useMultiFileAuthState } = require("@whiskeysockets/Baileys")

const { state, saveCreds } = await useMultiFileAuthState('auth_info_baileys')
const sock = makeWASocket({ auth: state })

sock.ev.on('creds.update', saveCreds)
```

📨 𝐌𝐞𝐬𝐬𝐚𝐠𝐞 𝐇𝐚𝐧𝐝𝐥𝐢𝐧𝐠 • تـعـامـل مـع الـرسـائـل

```javascript
sock.ev.on('messages.upsert', async ({ messages }) => {
    for (const message of messages) {
        console.log('📩 𝐍𝐞𝐰 𝐌𝐞𝐬𝐬𝐚𝐠𝐞 • رسـالـة جـديـدة:', message)
        await sock.sendMessage(message.key.remoteJid, { 
            text: '🎯 𝐑𝐞𝐜𝐞𝐢𝐯𝐞𝐝! • تـم الاسـتـلام!' 
        })
    }
})
```

👑 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫 • الـمـطـور

```javascript
const 𝐓𝐘𝐒𝐎𝐍_𝐌𝐃 = {
  "👑 𝐂𝐫𝐞𝐚𝐭𝐨𝐫 • الـمـبـرـمـج": "𝐓𝐘𝐒𝐎𝐍 𝐌𝐃",
  "📱 𝐖𝐡𝐚𝐭𝐬𝐀𝐩𝐩 • واتـسـاب": "https://wa.me/201515378259",
  "💻 𝐆𝐢𝐭𝐇𝐮𝐛 • جـيـت هـب": "github.com/TYSON-MD/Baileys-tx",
  "🚀 𝐕𝐞𝐫𝐬𝐢𝐨𝐧 • الإصـدار": "𝐄𝐧𝐡𝐚𝐧𝐜𝐞𝐝 𝐄𝐝𝐢𝐭𝐢𝐨𝐧 • الـنسـخـة الـمـطـورة"
};
```

---

<div align="center">
<b>🎯 𝐓𝐘𝐒𝐎𝐍 𝐌𝐃 - 𝐏𝐨𝐰𝐞𝐫𝐟𝐮𝐥 𝐖𝐡𝐚𝐭𝐬𝐀𝐩𝐩 𝐁𝐨𝐭 𝐋𝐢𝐛𝐫𝐚𝐫𝐲 🚀</b>
<br>
<em>𝐓𝐘𝐒𝐎𝐍 𝐌𝐃 - مـكـتـبـة بـوتـات وتـسـاب 🎯</em>
</div>

🎯 الاستخدام المتقدم • Advanced Usage

🔄 إدارة الأحداث • Event Management

```javascript
const { default: makeWASocket, useMultiFileAuthState, DisconnectReason } = require("@whiskeysockets/Baileys")

async function startBot() {
    const { state, saveCreds } = await useMultiFileAuthState('session')
    
    const sock = makeWASocket({
        auth: state,
        printQRInTerminal: true,
        browser: ['TYSON-MD', 'Safari', '1.0.0']
    })

    // حفظ بيانات الجلسة
    sock.ev.on('creds.update', saveCreds)

    // إدارة الاتصال
    sock.ev.on('connection.update', (update) => {
        const { connection, lastDisconnect } = update
        
        if(connection === 'close') {
            const shouldReconnect = lastDisconnect?.error?.output?.statusCode !== DisconnectReason.loggedOut
            console.log('🔄 إعادة الاتصال...' , shouldReconnect)
            if(shouldReconnect) {
                startBot()
            }
        } else if(connection === 'open') {
            console.log('✅ تم الاتصال بنجاح!')
        }
    })

    // معالجة الرسائل
    sock.ev.on('messages.upsert', async ({ messages }) => {
        const msg = messages[0]
        
        if(!msg.message || msg.key.fromMe) return
        
        const jid = msg.key.remoteJid
        const text = msg.message.conversation || msg.message.extendedTextMessage?.text
        
        if(text) {
            await sock.sendMessage(jid, { 
                text: `🎯 *TYSON MD* \n\nتـم اسـتـلام رسـالـتـك: ${text}` 
            })
        }
    })
}

startBot()
```

📊 مثال متكامل • Complete Example

```javascript
const { 
    default: makeWASocket, 
    useMultiFileAuthState, 
    DisconnectReason,
    Browsers,
    fetchLatestBaileysVersion 
} = require("@whiskeysockets/Baileys")

class TYSONBot {
    constructor() {
        this.sock = null
        this.init()
    }

    async init() {
        try {
            // الحصول على أحدث إصدار
            const { version, isLatest } = await fetchLatestBaileysVersion()
            console.log(`🚀 استخدام Baileys الإصدار: ${version}`)

            // تحميل الجلسة
            const { state, saveCreds } = await useMultiFileAuthState('tyson_session')
            
            // إنشاء الاتصال
            this.sock = makeWASocket({
                auth: state,
                printQRInTerminal: true,
                browser: Browsers.ubuntu('TYSON-MD'),
                version: version
            })

            // إعداد المعالجات
            this.setupHandlers(saveCreds)
            
        } catch (error) {
            console.error('❌ خطأ في التهيئة:', error)
        }
    }

    setupHandlers(saveCreds) {
        // تحديث بيانات الاعتماد
        this.sock.ev.on('creds.update', saveCreds)

        // إدارة الاتصال
        this.sock.ev.on('connection.update', (update) => {
            this.handleConnectionUpdate(update)
        })

        // معالجة الرسائل
        this.sock.ev.on('messages.upsert', ({ messages }) => {
            this.handleMessages(messages)
        })
    }

    handleConnectionUpdate(update) {
        const { connection, lastDisconnect } = update
        
        if(connection === 'close') {
            const statusCode = lastDisconnect?.error?.output?.statusCode
            if(statusCode !== DisconnectReason.loggedOut) {
                console.log('🔄 إعادة المحاولة...')
                setTimeout(() => this.init(), 5000)
            } else {
                console.log('❌ تم تسجيل الخروج')
            }
        } else if(connection === 'open') {
            console.log('🎯 TYSON MD Bot متصل وجاهز!')
        }
    }

    async handleMessages(messages) {
        for (const msg of messages) {
            try {
                if(!msg.message || msg.key.fromMe) continue
                
                await this.processMessage(msg)
            } catch (error) {
                console.error('❌ خطأ في معالجة الرسالة:', error)
            }
        }
    }

    async processMessage(msg) {
        const jid = msg.key.remoteJid
        const text = this.extractText(msg.message)
        
        if(!text) return

        // الأوامر الأساسية
        const commands = {
            '!ping': '🏓 Pong! TYSON MD يعمل',
            '!info': '🎯 TYSON MD - Enhanced Baileys Library\nالمطور: https://wa.me/201515378259',
            '!الاوامر': '🎯 الأوامر المتاحة:\n!ping • !info • !الاوامر'
        }

        const response = commands[text.toLowerCase()]
        if(response) {
            await this.sock.sendMessage(jid, { text: response })
        }
    }

    extractText(message) {
        return message.conversation || 
               message.extendedTextMessage?.text || 
               message.imageMessage?.caption
    }
}

// تشغيل البوت
new TYSONBot()
```

🎨 ميزات إضافية • Additional Features

📁 إرسال الوسائط • Media Sending

```javascript
// إرسال صورة
await sock.sendMessage(jid, {
    image: { url: 'https://example.com/image.jpg' },
    caption: '📸 صورة من TYSON MD'
})

// إرسال فيديو
await sock.sendMessage(jid, {
    video: { url: 'https://example.com/video.mp4' },
    caption: '🎬 فيديو من TYSON MD'
})

// إرسال مستند
await sock.sendMessage(jid, {
    document: { url: 'https://example.com/file.pdf' },
    fileName: 'ملف.pdf',
    mimetype: 'application/pdf'
})
```

👥 إدارة المجموعات • Group Management

```javascript
// الحصول على معلومات المجموعة
const groupInfo = await sock.groupMetadata(jid)

// إضافة عضو
await sock.groupParticipantsUpdate(
    jid, 
    ['123456789@s.whatsapp.net'], 
    'add'
)

// تغيير إعدادات المجموعة
await sock.groupUpdateSubject(jid, 'اسم المجموعة الجديد')
```

🔧 استكشاف الأخطاء • Troubleshooting

❌ المشاكل الشائعة • Common Issues

```javascript
// 1. مشاكل الجلسة
if(!state.creds.registered) {
    console.log('📱 يلزم تسجيل الرقم')
}

// 2. مشاكل الاتصال
sock.ev.on('connection.update', ({ connection, lastDisconnect }) => {
    if(connection === 'close') {
        const error = lastDisconnect.error
        if(error?.output?.statusCode === 401) {
            console.log('❌ تم تسجيل الخروج، حذف الجلسة')
            // حذف مجلد الجلسة وإعادة المحاولة
        }
    }
})

// 3. مشاكل الذاكرة
process.on('uncaughtException', (error) => {
    console.error('❌ خطأ غير معالج:', error)
})

process.on('unhandledRejection', (reason, promise) => {
    console.error('❌ وعد مرفوض:', reason)
})
```

---

<div align="center">

⭐ دعم المطور • Support Developer

إذا أعجبك المشروع، لا تنسى ⭐ نجمة على الريبو!

https://img.shields.io/github/stars/TYSON-MD/Baileys-tx?style=social

📞 للدعم والاستفسارات:
واتساب المطور

🐛 الإبلاغ عن مشاكل:
GitHub Issues

</div>

---

<div align="center">
<b>🎯 تم التطوير بواسطة TYSON MD 🚀</b>
<br>
<em>مكتبة Baileys المحسنة للإصدارات المتقدمة</em>
</div>
