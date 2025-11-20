<div align="center">TYSON MD</div>

https://files.catbox.moe/2gzoau.jpg

<div align="center">تم تطوير Bayles Library Enhanced بواسطة TYSON-MD</div>

المشاكل التي تم إصلاحها

· lid - إصلاحات الاتصال الأساسية
· الجلسات - دعم المصادقة المزدوجة:
  · تسجيل الدخول برمز QR
  · تسجيل الدخول برمز 8 أرقام

الميزات المحسنة

· أداء محسن للمجموعات
· دعم كامل للوسائط
· إدارة متقدمة للجلسات

كيفية التحديث إلى هذه النسخة؟

· في ملف package.json

```json
{
  "dependencies": {
    "@whiskeysockets/Baileys": "github:TYSON-MD/Baileys-tx"
  }
}
```

مثال

هذا مثال يمكنك استخدامه: example.ts أو هذا البرنامج التعليمي لتشغيل كود Baileys WhatsApp API

1.  cd path/to/Baileys 
2.  npm install
3.  node example.js

التثبيت

استخدم النسخة المستقرة:

```bash
npm install @whiskeysockets/Baileys@github:TYSON-MD/Baileys-tx
```

ثم استورد الكود الخاص بك باستخدام:

```javascript
const { default: makeWASocket } = require("@whiskeysockets/Baileys")
```

توصيل الحساب

يوفر WhatsApp واجهة برمجة تطبيقات متعددة الأجهزة تسمح لمصادقة Baileys كعميل WhatsApp ثان عن طريق مسح رمز QR أو رمز الاقتران باستخدام WhatsApp على هاتفك.

بدء الاتصال باستخدام QR-CODE

[!TIP]
يمكنك تخصيص اسم المتصفح إذا اتصلت باستخدام QR-CODE، باستخدام ثابت Browser، لدينا بعض إعدادات المتصفح، انظر هنا

```javascript
const { default: makeWASocket, Browsers } = require("@whiskeysockets/Baileys")

const sock = makeWASocket({
    // يمكنك تقديم إعدادات إضافية هنا
    browser: Browsers.ubuntu('My App'),
    printQRInTerminal: true
})
```

إذا نجح الاتصال، سترى رمز QR مطبوع على شاشة طرفيتك، قم بمسحه باستخدام WhatsApp على هاتفك وسيتم تسجيل دخولك!

بدء الاتصال باستخدام رمز الاقتران

[!IMPORTANT]
رمز الاقتران ليس واجهة برمجة تطبيقات الهاتف، إنها طريقة للاتصال بـ Whatsapp Web بدون QR-CODE، يمكنك الاتصال بجهاز واحد فقط، انظر هنا

رقم الهاتف لا يمكن أن يحتوي على + أو () أو -، أرقام فقط، يجب تقديم رمز الدولة

```javascript
const { default: makeWASocket } = require("@whiskeysockets/Baileys")

const sock = makeWASocket({
    // يمكنك تقديم إعدادات إضافية هنا
    printQRInTerminal: false //يجب أن يكون false
})

// الاقتران العادي
if (!sock.authState.creds.registered) {
    const number = 'XXXXXXXXXXX'
    const code = await sock.requestPairingCode(number)
    console.log(code)
}

// الاقتران المخصص
if (!sock.authState.creds.registered) {
    const pair = "12345678" // فقط 8 أحرف أبجدية رقمية (لا أكثر ولا أقل)
    const number = 'XXXXXXXXXXX'
    const code = await sock.requestPairingCode(number, pair)
    console.log(code)
}
```

استقبال السجل الكامل

1. عيّن syncFullHistory كـ true
2. يستخدم Baileys افتراضيًا إعدادات متصفح Chrome
   · إذا كنت ترغب في محاكاة اتصال سطح المكتب (واستقبال المزيد من سجل الرسائل)، أضف هذا الإعداد للمتصفح في إعدادات السوكيت:

```javascript
const sock = makeWASocket({
    ...otherOpts,
    // يمكن استخدام Windows, Ubuntu هنا أيضًا
    browser: Browsers.macOS('Desktop'),
    syncFullHistory: true
})
```

ملاحظات مهمة حول إعدادات السوكيت

تخزين بيانات المجموعة مؤقتًا (مُوصى به)

· إذا كنت تستخدم baileys للمجموعات، نوصي بتعيين cachedGroupMetadata في إعدادات السوكيت، تحتاج إلى تنفيذ ذاكرة تخزين مؤقت مثل هذا:

```javascript
const NodeCache = require('node-cache')
const groupCache = new NodeCache({stdTTL: 5 * 60, useClones: false})

const sock = makeWASocket({
    cachedGroupMetadata: async (jid) => groupCache.get(jid)
})

sock.ev.on('groups.update', async ([event]) => {
    const metadata = await sock.groupMetadata(event.id)
    groupCache.set(event.id, metadata)
})

sock.ev.on('group-participants.update', async (event) => {
    const metadata = await sock.groupMetadata(event.id)
    groupCache.set(event.id, metadata)
})
```

تحسين نظام إعادة المحاولة وفك تشفير أصوات الاستطلاع

· إذا كنت تريد تحسين إرسال الرسائل، وإعادة المحاولة عند حدوث خطأ وفك تشفير أصوات الاستطلاع، تحتاج إلى وجود مخزن وتعيين getMessage في إعدادات السوكيت مثل هذا:

```javascript
const sock = makeWASocket({
    getMessage: async (key) => await getMessageFromStore(key)
})
```

استقبال الإشعارات في تطبيق WhatsApp

· إذا كنت تريد استقبال الإشعارات في تطبيق WhatsApp، عيّن markOnlineOnConnect إلى false

```javascript
const sock = makeWASocket({
    markOnlineOnConnect: false
})
```

حفظ واستعادة الجلسات

من الواضح أنك لا تريد الاستمرار في مسح رمز QR في كل مرة تريد الاتصال.

لذلك، يمكنك تحميل بيانات الاعتماد لتسجيل الدخول مرة أخرى:

```javascript
const makeWASocket = require("@whiskeysockets/Baileys").default;
const { useMultiFileAuthState } = require("@whiskeysockets/Baileys");

const { state, saveCreds } = await useMultiFileAuthState('auth_info_baileys')

// سيستخدم الحالة المعطاة للاتصال
// لذا إذا كانت بيانات الاعتماد صالحة متاحة -- سيتصل بدون QR
const sock = makeWASocket({ auth: state })

// سيتم استدعاء هذا بمجرد تحديث بيانات الاعتماد
sock.ev.on('creds.update', saveCreds)
```

[!IMPORTANT]
useMultiFileAuthState هي وظيفة مساعدة لحفظ حالة المصادقة في مجلد واحد، تخدم هذه الوظيفة كدليل جيد للمساعدة في كتابة حالات المصادقة والمفاتيح لقواعد بيانات SQL/no-SQL، والتي أوصي بها في أي نظام إنتاجي.

[!NOTE]
عند استلام/إرسال رسالة، بسبب حاجة جلسات signal للتحديث، سيتم تحديث مفاتيح المصادقة (authState.keys). عندما يحدث ذلك، يجب عليك حفظ المفاتيح المحدثة (يتم استدعاء authState.keys.set()). عدم القيام بذلك سيمنع وصول رسائلك إلى المستلم ويتسبب في عواقب غير متوقعة أخرى. تقوم وظيفة useMultiFileAuthState تلقائيًا بالعناية بذلك، ولكن لأي تنفيذ جاد آخر -- ستحتاج إلى أن تكون حريصًا جدًا على إدارة حالة المفتاح.

التعامل مع الأحداث

· يستخدم Baileys بناء جملة EventEmitter للأحداث.
  جميعها مدعومة بأنواع،لذا لا يجب أن تواجه أي مشاكل مع محرر ذكي مثل VS Code.

[!IMPORTANT]
الأحداث هي هذه، من المهم أن ترى جميع الأحداث

يمكنك الاستماع إلى هذه الأحداث مثل هذا:

```javascript
const sock = makeWASocket()
sock.ev.on('messages.upsert', ({ messages }) => {
    console.log('تم استقبال الرسائل', messages)
})
```

مثال للبدء

[!NOTE]
هذا المثال يتضمن أيضًا تخزين أساسي للمصادقة

```javascript
const makeWASocket = require("@whiskeysockets/Baileys").default;
const { DisconnectReason, useMultiFileAuthState } = require("@whiskeysockets/Baileys");
const Boom = require('@hapi/boom');

async function connectToWhatsApp() {
    const { state, saveCreds } = await useMultiFileAuthState('auth_info_baileys')
    const sock = makeWASocket({
        // يمكنك تقديم إعدادات إضافية هنا
        auth: state,
        printQRInTerminal: true
    })
    sock.ev.on('connection.update', (update) => {
        const { connection, lastDisconnect } = update
        if(connection === 'close') {
            const shouldReconnect = lastDisconnect.error?.output?.statusCode !== DisconnectReason.loggedOut
            console.log('تم إغلاق الاتصال بسبب ', lastDisconnect.error, ', إعادة الاتصال ', shouldReconnect)
            // إعادة الاتصال إذا لم يتم تسجيل الخروج
            if(shouldReconnect) {
                connectToWhatsApp()
            }
        } else if(connection === 'open') {
            console.log('تم فتح الاتصال')
        }
    })
    sock.ev.on('messages.upsert', async event => {
        for (const m of event.messages) {
            console.log(JSON.stringify(m, undefined, 2))

            console.log('الرد على', m.key.remoteJid)
            await sock.sendMessage(m.key.remoteJid, { text: 'Hello World' })
        }
    })

    // لتخزين بيانات الاعتماد (معلومات الجلسة) عند تحديثها
    sock.ev.on('creds.update', saveCreds)
}
// تشغيل في الملف الرئيسي
connectToWhatsApp()
```

[!IMPORTANT]
في messages.upsert يُوصى باستخدام حلقة مثل for (const message of event.messages) للتعامل مع جميع الرسائل في المصفوفة

TYSON-MD

```JavaScript
const owner = {
  "𝗧𝗬𝗦𝗢𝗡 𝗘𝗟𝗬𝗢𝗨𝗧𝗨𝗢𝗕𝗘𝗥": {
    "whatsapp": "https://wa.me/201207762702"
  }
};
```