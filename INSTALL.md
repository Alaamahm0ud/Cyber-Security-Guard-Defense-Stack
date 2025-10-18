````markdown
# 🧰 دليل التثبيت — نظام Cyber Security Guard Defense Stack

يوضح هذا الدليل خطوات تثبيت وتكوين النظام الدفاعي الكامل، بما في ذلك الوحدات الأربع ونظام الأتمتة عبر N8N.

---

## 📦 المتطلبات المسبقة
- نظام التشغيل: Linux (يوصى باستخدام Ubuntu)، أو Windows Server، أو أي بيئة تدعم Docker  
- أدوات التطوير:
  - Python 3.10 أو أحدث (مطلوب لوحدتي CG و Link.CSG)
  - Rust (مطلوب للوحدة الأساسية CSG Core)
  - Node.js 18 أو أحدث (مطلوب لوحدتي N8N و VPN.CSG)
- Docker و Docker Compose (موصى بهما للنشر المعياري)
- GitHub CLI (اختياري لاستنساخ المستودعات)

---

## ⚙️ الخطوة 1: استنساخ المستودعات
افتح الطرفية ونفّذ الأوامر التالية لاستنساخ جميع المستودعات المطلوبة:

```bash
gh repo clone Alasarmamhd/Cyber-Security-Guard-Defense-Stack
gh repo clone Alasarmamhd/cyber-guard-pro
gh repo clone Alasarmamhd/cyber-security-guard-pro
gh repo clone Alasarmamhd/VPN-GUARD.-SCG-
gh repo clone Alasarmamhd/linkgarde.csg
````

---

## 🧩 الخطوة 2: تثبيت N8N (محرك الأتمتة)

يمكنك تثبيت N8N بطريقتين: عبر Docker (مستحسن) أو محليًا باستخدام Node.js.

### الخيار A — باستخدام Docker (موصى به)

```bash
docker run -it --rm \
  -p 5678:5678 \
  -v ~/.n8n:/home/node/.n8n \
  n8nio/n8n
```

### الخيار B — التثبيت المحلي

```bash
npm install n8n -g
n8n start
```

---

## 🔧 الخطوة 3: تهيئة كل وحدة

### 1. CSG (الوحدة الأساسية — Core AI-XDR)

```bash
cd cyber-security-guard-pro
# قم بالبناء باستخدام Rust أو شغّل الملف التنفيذي الجاهز مسبقًا
# تأكد من أن خدمة API تعمل على المنفذ 5050
```

### 2. CG (التحليل الذكي والذكاء التهديدي — AI-SOC & Threat Intelligence)

```bash
cd cyber-guard-pro
pip install -r requirements.txt
python main.py
```

### 3. VPN.CSG (شبكة VPN اللامركزية)

```bash
cd VPN-GUARD.-SCG-
npm install
node vpn.js
```

### 4. Link.CSG (التحقق قبل الدخول — Pre-entry Validation)

```bash
cd linkgarde.csg
pip install -r requirements.txt
python linkguard.py
```

---

## 🔗 الخطوة 4: ربط الوحدات عبر N8N

استخدم N8N لتنسيق العمليات بين جميع الوحدات. يمكن إعداد سير عمل (Workflows) للقيام بما يلي:

* تشغيل استجابة تلقائية للحوادث من وحدة CSG
* تحليل وربط التهديدات من وحدة CG
* فحص الروابط والتحقق منها عبر Link.CSG
* تحديث إعدادات VPN من خلال وحدة VPN.CSG

راجع الرسومات التوضيحية في المجلدين `docs/ar/` و `docs/en/` للاطلاع على أمثلة جاهزة لسير العمل.

---

## ✅ التحقق النهائي من التشغيل

تأكد من النقاط التالية بعد التثبيت:

* كل وحدة تُظهر واجهة API وتستجيب لاختبارات الصحة (Health Check).
* N8N قادر على تشغيل المشغلات والتنسيق بين الوحدات.
* السجلات (Logs) والتنبيهات تظهر في الطرفية أو في لوحة التحكم (Dashboard) إن وُجدت.

---

## 🛠️ إعدادات النشر المتقدم

للتشغيل في بيئة إنتاج أو بيئة متقدمة، يُوصى بما يلي:

* تفعيل بروتوكول HTTPS عبر شهادات TLS / SSL
* نشر النظام باستخدام Docker Compose أو Kubernetes
* مراقبة الأداء والسجلات باستخدام ELK أو Prometheus وGrafana
* تفعيل نظام الصلاحيات (RBAC) وسجلات التدقيق (Audit Logs)
* إنشاء نسخ احتياطية وخطط استعادة عند الكوارث

يمكن الاطلاع على إعدادات متقدمة إضافية (مثل ملفات `.env` و `docker-compose.yml`) من خلال Wiki المشروع أو صفحات GitHub الخاصة به.

---

## 📂 الهيكل المقترح للمجلدات

```
.
├── cyber-security-guard-pro/     # الوحدة الأساسية CSG
├── cyber-guard-pro/              # وحدة CG (ذكاء التهديدات)
├── linkgarde.csg/                # وحدة Link.CSG (التحقق من الروابط)
├── VPN-GUARD.-SCG-/              # وحدة VPN.CSG (الشبكة اللامركزية)
├── n8n-workflows/                # ملفات سير العمل الخاصة بـ N8N
├── docs/
│   ├── en/
│   └── ar/
└── README.md                     # ملف التثبيت هذا
```

---

```
```
