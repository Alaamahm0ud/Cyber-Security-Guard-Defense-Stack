# 🛡️ Cyber Security Guard Defense Stack

منصة دفاع سيبراني متعددة الطبقات، تعتمد على الذكاء الاصطناعي للكشف اللحظي عن التهديدات، إخفاء الهوية عبر VPN، والتحقق الذكي من الروابط قبل الوصول. مصممة لأغراض دفاعية وأبحاث سيبرانية أخلاقية، وتدعم أتمتة العمليات وفقًا لمنهجية SOAR.

---

## نظرة عامة

المنظومة تتكون من أربع وحدات مترابطة:

- CSG: نواة AI-XDR الداخلية — مسؤولة عن المراقبة التكيفية والاستجابة للحوادث  
- CG: وحدة AI-SOC واستخبارات التهديدات — تحليل الترابطات ودعم القرار  
- VPN.CSG: شبكة افتراضية لا مركزية — لإخفاء الهوية وتأمين الاتصال  
- Link.CSG: بوابة تحقق ذكية — لفحص الروابط والملفات قبل الوصول

تعمل هذه المكونات بتناغم عبر واجهات API مؤمنة، وتتكامل مع أدوات الأتمتة مثل [N8N](https://n8n.io) لتوفير استجابة ديناميكية وسريعة.

---

## الهيكل المعماري

| المكون     | الوظيفة التقنية                 | الموضع في المنظومة         |
|------------|----------------------------------|-----------------------------|
| CSG        | نواة AI-XDR                     | داخلي / مركزي              |
| CG         | استخبارات التهديدات             | تحليلي / داعم              |
| VPN.CSG    | إخفاء الهوية اللامركزي          | حدودي / شبكة خارجية        |
| Link.CSG   | تحقق ذكي من الروابط             | حدودي / بوابة التفتيش      |

---

## متطلبات التشغيل

- نظام تشغيل: Linux أو Windows Server أو Docker  
- تثبيت أداة N8N للأتمتة  
- تحميل أو بناء الوحدات الأربع: CSG، CG، VPN.CSG، Link.CSG  
- بيئات تطوير: Python / Rust / Node.js حسب كل وحدة

---

## سيناريوهات الأتمتة باستخدام N8N

### 1. الاستجابة للحوادث الداخلية  
عند اكتشاف سلوك شاذ من CSG، يتم عزل الجهاز وتشغيل تحليل عبر CG.

### 2. فحص الروابط قبل الوصول  
أي رابط وارد يتم تمريره إلى Link.CSG للفحص، وإذا كان خبيثًا يتم حظره وإرسال تقرير إلى CSG.

### 3. تحديثات أمنية استباقية  
عند اكتشاف ثغرة جديدة من CG، يصدر N8N تعليمات إلى CSG لتطبيق التصحيحات على الأجهزة المستهدفة.

---

## الصور التوضيحية

### النسخة العربية  
- [مخطط سير العمل 1](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/ar/n8n.0.png)  
- [مخطط سير العمل 2](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/ar/n8n.1.png)  
- [الهيكل المعماري](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/ar/architecture.png)

### النسخة الإنجليزية  
- [Workflow Diagram](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/en/n8n.0.png)  
- [Workflow Overview](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/en/n8n.jpg)  
- [Architecture Diagram](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack/blob/main/docs/en/architecture.png)

---

## الرخصة والاستخدام الأخلاقي

تم تطوير المنصة لأغراض دفاعية فقط، ويُحظر استخدامها في أي أنشطة غير مصرح بها.  
الرخصة المعتمدة: [Apache-2.0 License](https://www.apache.org/licenses/LICENSE-2.0)

---

## التطويرات المستقبلية

- لوحة تحكم لحظية للمراقبة  
- نشر مؤمن عبر Docker  
- تدوير تلقائي لمفاتيح TLS  
- وحدة AI للكشف التلقائي عن التهديدات

---

## المطوّر

Alaa Mahmoud Mohamed  
مطور أدوات أمن سيبراني مستقل  
الجيزة، مصر  
📧 alaat9080@gmail.com  
📞 +20 22595905  
🔗 [LinkedIn](https://www.linkedin.com/in/alaa-mahmoudmohamed)

---

## روابط المشاريع

- [الصفحة الشخصية](https://github.com/Alaamahm0ud/Alaamahm0ud.git)  
- [Cyber Guard Pro](https://github.com/Alaamahm0ud/cyber-guard-pro.git)  
- [Cyber Security Guard Pro](https://github.com/Alaamahm0ud/cyber-security-guard-pro.git)  
- [VPN-GUARD SCG](https://github.com/Alaamahm0ud/VPN-GUARD.-SCG-.git)  
- [Linkgarde CSG](https://github.com/Alaamahm0ud/linkgarde.csg.git)  
- [Cyber Security Guard Defense Stack](https://github.com/Alaamahm0ud/Cyber-Security-Guard-Defense-Stack.git)

---

تم بناء هذه المنصة لتكون حجر أساس في الدفاع السيبراني الأخلاقي، وتوفر بيئة متكاملة للباحثين والمطورين والمختصين في أمن المعلومات.
