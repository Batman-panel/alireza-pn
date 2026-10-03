# 🦇 AlirezaPanel — KataBump Edition

<p align="center">
  <b>🚀 A KataBump-ready version of AlirezaPanel / VPN-UI</b>
</p>

<p align="center">
  <b>نسخه آماده AlirezaPanel برای اجرا روی KataBump</b>
</p>

<p align="center">

![Node.js](https://img.shields.io/badge/Node.js-Ready-339933?style=for-the-badge\&logo=node.js)

![KataBump](https://img.shields.io/badge/KataBump-Ready-orange?style=for-the-badge)

![Linux](https://img.shields.io/badge/Linux-amd64-blue?style=for-the-badge\&logo=linux)

</p>

---

# 🌐 About | درباره پروژه

## 🇬🇧 English

**AlirezaPanel — KataBump Edition** is a modified and adapted version of AlirezaPanel / VPN-UI designed to run inside a **KataBump Node.js server**.

The original VPN-UI installation process normally expects a traditional Linux server environment with root access, system services and system-level interfaces.

This edition provides a dedicated **KataBump entry point** that adapts the panel for the KataBump environment.

The project is built around:

```text
index.js
package.json
```

The included `index.js` starts the application, manages the internal panel process, handles the public port, prepares the required directories and provides the KataBump-compatible runtime layer.

The project also downloads and verifies the required `vpn-ui` binary automatically.

---

## 🇮🇷 فارسی

**AlirezaPanel — KataBump Edition** نسخه‌ای تغییر داده‌شده و آماده از AlirezaPanel / VPN-UI است که برای اجرای آسان‌تر داخل **KataBump** آماده شده است.

نسخه اصلی VPN-UI برای نصب معمولاً به محیط لینوکس سنتی، دسترسی Root و سرویس‌های سیستمی نیاز دارد.

این نسخه یک لایه مخصوص KataBump دارد تا برنامه بتواند داخل محیط Node.js این سرویس اجرا شود.

ساختار اصلی پروژه:

```text
index.js
package.json
```

است.

`index.js` وظیفه اجرای پنل، مدیریت پورت عمومی، ایجاد پوشه‌های موردنیاز، اجرای سرویس داخلی و آماده‌سازی محیط KataBump را برعهده دارد.

همچنین فایل موردنیاز `vpn-ui` را دانلود کرده و قبل از استفاده، صحت آن را بررسی می‌کند.

---

# ✨ Features | امکانات

* 🚀 KataBump Ready
* 🦇 AlirezaPanel branding
* ⚡ Node.js based startup
* 📦 Automatic VPN-UI binary setup
* 🔐 SHA-256 binary verification
* 🌐 Public port support
* 🔄 Internal panel proxy
* 💾 Persistent application data
* 📁 Automatic directory creation
* 🧪 Built-in self-test functionality
* 🌍 Multiple protocol endpoints
* 🖥️ Linux amd64 support

The project exposes multiple protocol-related ports and WebSocket paths through its internal runtime.

---

# 📡 Supported Protocol Endpoints

The current project defines support for several protocol endpoints, including:

```text
VLESS
VMess
Trojan
Shadowsocks
gRPC
WebSocket
HTTP Upgrade
```

The configured internal ports include:

```text
VLESS        → 21001
Trojan       → 21002
Shadowsocks  → 21003

VLESS WS     → 21011
VMess WS     → 21012
Trojan WS    → 21013
gRPC         → 21014
Upgrade      → 21015
```

WebSocket paths include:

```text
/bp-vless
/bp-vmess
/bp-trojan
/bp-up
```

These values are defined directly in the project's runtime configuration.

---

# ☁️ Why KataBump?

## 🇬🇧 English

KataBump provides Node.js and Python hosting with a free tier, making it possible to experiment with Node.js applications without managing a traditional VPS.

KataBump automatically installs Node.js project dependencies when a valid `package.json` is present.

## 🇮🇷 فارسی

KataBump امکان اجرای پروژه‌های Node.js و Python را فراهم می‌کند و یک پلن رایگان نیز دارد.

در پروژه‌های Node.js، وجود `package.json` باعث می‌شود KataBump بتواند وابستگی‌های پروژه را به‌صورت خودکار نصب کند.

---

# 🆓 Free Hosting | اجرای رایگان

KataBump دارای پلن رایگان است.

در حال حاضر پلن Free شامل:

```text
RAM:     308 MB
Storage: 716 MB
CPU:     25%
Price:   0€
```

است.

سرورهای رایگان باید هر **4 روز** تمدید شوند؛ در صورت تمدید نکردن، سرور متوقف و بعد از مهلت حذف می‌شود.

> ⚠️ منابع پلن رایگان محدود هستند و مناسب پروژه‌های سبک و تستی‌اند. برای استفاده سنگین باید محدودیت‌های سرویس را در نظر بگیرید.

---

# 🚀 Installation | نصب

## 1️⃣ Create a KataBump Server

وارد KataBump شوید و یک Server جدید ایجاد کنید.

برای این پروژه:

```text
Runtime → Node.js
```

را انتخاب کنید.

KataBump از Node.js و Python پشتیبانی می‌کند.

---

# 2️⃣ Upload the Project

فایل‌های زیر را داخل سرور قرار دهید:

```text
index.js
package.json
```

ساختار باید به شکل زیر باشد:

```text
/home/container/
│
├── index.js
└── package.json
```

KataBump برای فایل‌های پروژه مسیر `/home/container` را به‌عنوان working directory استفاده می‌کند.

---

# 3️⃣ Install Dependencies

این پروژه وابستگی npm خارجی در `package.json` ندارد.

فایل `package.json` فقط اسکریپت اصلی را مشخص می‌کند:

```json
{
  "name": "alirezapanel-katabump",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "start": "node index.js"
  }
}
```

بنابراین اجرای اصلی پروژه با:

```bash
node index.js
```

انجام می‌شود.

---

# 4️⃣ Start the Server

در پنل KataBump وارد:

```text
Console
```

شوید و سرور را:

```text
Start
```

کنید.

KataBump هنگام اولین اجرا وابستگی‌های Node.js را در صورت نیاز نصب می‌کند و سپس اسکریپت Start پروژه را اجرا می‌کند.

---

# 5️⃣ Wait for Initialization

در اولین اجرا، پروژه محیط موردنیاز خود را ایجاد می‌کند.

پوشه‌هایی مانند:

```text
vpn/
├── data/
├── bin/
└── log/
```

به‌صورت خودکار ساخته می‌شوند.

فایل VPN-UI نیز در محیط پروژه قرار می‌گیرد و قبل از استفاده SHA-256 آن بررسی می‌شود.

---

# 6️⃣ Open the Panel

پروژه پورت عمومی را از:

```text
SERVER_PORT
```

یا:

```text
PORT
```

می‌خواند و در صورت نبودن این متغیرها از پورت پیش‌فرض استفاده می‌کند.

بعد از Online شدن سرور، آدرس عمومی ارائه‌شده توسط KataBump را باز کنید.

---

# 🛠️ Environment Variables

The project supports environment variables such as:

```text
PORT
SERVER_PORT
PANEL_HOST
SERVER_IP
KATABUMP_ROOT
```

The KataBump environment normally provides the public port through its runtime configuration.

The project also detects `/home/container` automatically when available.

---

# 🧠 How It Works

```text
                 KataBump Server
                       │
                       ▼
                 Node.js Runtime
                       │
                       ▼
                    index.js
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
    Public HTTP Port          Internal Panel
          │                         │
          └────────────┬────────────┘
                       │
                       ▼
                  VPN-UI Engine
                       │
          ┌────────────┼────────────┐
          ▼            ▼            ▼
       VLESS         Trojan       Other
```

The project uses Node.js as the outer runtime and manages the internal VPN-UI process from `index.js`.

---

# 🔒 Verification & Safety

The project contains a SHA-256 checksum for the downloaded VPN-UI binary.

During initialization, the downloaded file is checked against the expected hash before it is used.

This helps prevent an unexpected or corrupted binary from being used by the startup process.

---

# 🧪 Self Test

The project includes a built-in self-test mode.

You can run:

```bash
SELFTEST=1 node index.js
```

to execute the available startup and branding tests.

The project tests several internal components, including the panel proxy and branding layer.

---

# 🎨 AlirezaPanel Branding

The KataBump edition includes custom branding for:

```text
alirezapanel
```

The runtime can rewrite the visible panel branding and provide the custom logo and branding assets.

The project keeps the underlying runtime compatible with the adapted VPN-UI environment.

---

# 📁 Project Structure

```text
alireza-pn/
│
├── index.js
│
└── package.json
```

After the first launch, runtime data is created automatically:

```text
vpn/
├── data/
├── bin/
├── log/
├── PANEL.txt
└── state.json
```

---

# 🔄 Updating

To update the project:

1. Stop the KataBump server.
2. Replace `index.js`.
3. Replace `package.json` if required.
4. Start the server again.
5. Wait for the initialization process.

Do **not** delete the `vpn/data` directory if you want to preserve the existing application data.

---

# ⚠️ Important Notes

### Linux amd64 Required

The current implementation checks for:

```text
Linux
x64 / amd64
```

and exits if the runtime does not match.

### Free KataBump Resources

The free KataBump plan currently provides limited resources and requires renewal every 4 days.

### Service Rules

Use the hosting service according to KataBump's current terms and resource policies. Free services are subject to their usage restrictions.

---

# 🦇 Quick Start

For experienced users:

```bash
git clone https://github.com/Batman-panel/alireza-pn.git
cd alireza-pn
npm start
```

Or upload:

```text
index.js
package.json
```

to your KataBump server and start it from the panel.

---

# 📌 Repository

**GitHub:**

https://github.com/Batman-panel/alireza-pn

**KataBump:**

https://katabump.com/

---

# ⭐ Support the Project

If this project helped you, consider giving the repository a ⭐ on GitHub.

Every star helps the project get more visibility and motivates further development.

---

# 🦇 AlirezaPanel × KataBump

<p align="center">
  <b>Simple Deployment • Free Hosting • Node.js • KataBump</b>
</p>

<p align="center">
  <b>راه‌اندازی ساده • میزبانی رایگان • Node.js • KataBump</b>
</p>

<p align="center">
  🦇 <b>Batman Panel</b> × <b>AlirezaPanel</b> × <b>KataBump</b>
</p>
