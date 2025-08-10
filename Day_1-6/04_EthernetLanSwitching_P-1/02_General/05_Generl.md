### အဲဒါဆိုရင် Attacker တွေက data ရှိတဲ့အပိုင်းကို စိတ်ဝင်စားတော့ ဘယ်လိုများ Attack လုပ်ပါသလဲခင်ဗျ။

Attacker တွေဟာ Data ကို စိတ်ဝင်စားတဲ့အတွက် OSI Model ရဲ့ Layer 5, 6, 7 (Application, Presentation, Session) တွေနဲ့ Layer 4 (Transport) တို့မှာ အဓိကထားပြီး တိုက်ခိုက်လေ့ရှိပါတယ်။

Attack နည်းလမ်းအချို့ကို ရှင်းပြပေးပါမယ်ခင်ဗျာ။

### **၁။ Layer 7 (Application Layer) Attacks**

ဒီအလွှာမှာ Applications တွေကို တိုက်ရိုက်တိုက်ခိုက်ကြပါတယ်။

- **DDoS (Distributed Denial-of-Service) Attack:** Web Server တစ်ခုဆီကို အတုအယောင် Requests တွေကို အမြောက်အများပို့ပြီး Server ရဲ့ လုပ်ဆောင်နိုင်စွမ်းကို ကျစေတာ၊ ရပ်တန့်သွားအောင် လုပ်တာမျိုး ဖြစ်ပါတယ်။
- **SQL Injection:** Web Application ရဲ့ Database ထဲကို အန္တရာယ်ရှိတဲ့ Command တွေကို ထည့်သွင်းပြီး Database ထဲက အချက်အလက်တွေကို ခိုးယူတာ၊ ဖျက်ဆီးတာမျိုး လုပ်ပါတယ်။
- **Cross-Site Scripting (XSS):** Website တစ်ခုဆီကို Script code တွေ ထည့်သွင်းပြီး အဲဒီ Website ကို သုံးတဲ့ User တွေရဲ့ Cookies တွေ၊ Session Information တွေကို ခိုးယူတာမျိုး ဖြစ်ပါတယ်။
- **Social Engineering:** Application တစ်ခုကို တိုက်ရိုက်တိုက်ခိုက်တာမဟုတ်ဘဲ User တွေကို လှည့်စားပြီး Password တွေ၊ Sensitive Information တွေကို ရယူတာမျိုး ဖြစ်ပါတယ်။ (ဥပမာ- Phishing Attack)

### **၂။ Layer 4 (Transport Layer) Attacks**

ဒီအလွှာမှာ TCP/UDP Protocols တွေရဲ့ အားနည်းချက်ကို အဓိကထား တိုက်ခိုက်ပါတယ်။

- **SYN Flood Attack:** TCP Connection တစ်ခုတည်ဆောက်ဖို့အတွက် `SYN` Packet တွေကို အမြောက်အများ ပို့ဆောင်ပြီး Server ရဲ့ Connection ကို လက်ခံနိုင်တဲ့ Limit ကို ပြည့်သွားစေတာမျိုး ဖြစ်ပါတယ်။ ဒါကြောင့် တကယ်အသုံးပြုလိုသူတွေဟာ Server ကို ချိတ်လို့မရတော့တာမျိုး ဖြစ်ပါတယ်။
- **Port Scan:** Network ထဲမှာ ဘယ် Port တွေဖွင့်ထားလဲဆိုတာ သိရှိနိုင်ဖို့ TCP/UDP Port တွေကို စနစ်တကျ Scan လုပ်ပြီး နောက်ပိုင်း တိုက်ခိုက်ဖို့အတွက် အားနည်းချက်တွေကို ရှာဖွေတာမျိုး လုပ်ပါတယ်။

### **၃။ Layer 3 & 2 (Network & Data Link) Attacks**

ဒီအလွှာတွေဟာ Data ကို သယ်ယူပို့ဆောင်ပေးတဲ့နေရာဖြစ်လို့ Data ခိုးယူတာ၊ Network Traffic ကို ပြောင်းလဲတာတွေ လုပ်ပါတယ်။

- **IP Spoofing:** တိုက်ခိုက်သူဟာ သူ့ရဲ့ IP Address ကို တခြား IP Address တစ်ခုအဖြစ် ဟန်ဆောင်ပြီး တိုက်ခိုက်တာမျိုး ဖြစ်ပါတယ်။
- **ARP Spoofing/Poisoning:** Attacker ဟာ Local Network ထဲက Device တွေရဲ့ MAC Address နဲ့ IP Address တွေရဲ့ ဆက်စပ်မှုကို မှားယွင်းအောင် လုပ်ပြီး Network Traffic တွေကို သူ့ဆီကို ဦးတည်ရောက်ရှိအောင် လုပ်ဆောင်တာမျိုး ဖြစ်ပါတယ်။ ဒါကြောင့် Data တွေကို ခိုးယူဖတ်ရှုနိုင်ပါတယ်။

### **အနှစ်ချုပ်**

Attacker တွေဟာ သင်ပြောသလိုပဲ Data နဲ့ နီးစပ်တဲ့ Layer 5, 6, 7 မှာ Application တွေကို အဓိကထား တိုက်ခိုက်ကြသလို၊ Layer 4, 3, 2 တွေမှာလည်း Data ကို ခိုးယူဖို့နဲ့ Network ရဲ့ လုပ်ဆောင်ချက်တွေကို အနှောင့်အယှက်ပေးဖို့အတွက် တိုက်ခိုက်လေ့ရှိပါတယ်ခင်ဗျာ။
