# Networking Model

Networking Model ဆိုတာ ကွန်ရက်တစ်ခုမှာ ကွန်ပျူတာတွေကြား အချက်အလက် (Data) တွေ ဘယ်လိုပို့ဆောင်လဲဆိုတာကို နားလည်လွယ်အောင် အလွှာလိုက် အပိုင်းလိုက် ခွဲခြားပြထားတဲ့ သဘောတရားတစ်ခု (conceptual framework) ဖြစ်ပါတယ်။ ဒါဟာ Network Engineers တွေ၊ Software Developers တွေနဲ့ IT ပညာရှင်တွေအတွက် ဆက်သွယ်ရေးစနစ်တစ်ခုရဲ့ရှုပ်ထွေးမှုကို စနစ်တကျလေ့လာဖို့နဲ့ ပြဿနာရှာဖွေဖြေရှင်းဖို့ အလွန်အသုံးဝင်တဲ့ ကိရိယာတစ်ခုပါပဲ။

အဓိက Networking Model နှစ်မျိုး ရှိပါတယ်။

1.  **OSI (Open Systems Interconnection) Model**
2.  **TCP/IP (Transmission Control Protocol/Internet Protocol) Model**

### **1. OSI Model (အလွှာ ၇ လွှာပါတဲ့ Model)**

OSI Model ကို 1980 ခုနှစ်များအလယ်ပိုင်းမှာ ISO (International Organization for Standardization) ကနေ Network protocols တွေအတွက် universal standard တစ်ခုအဖြစ် သတ်မှတ်ခဲ့တာ ဖြစ်ပါတယ်။ ဒါဟာ လက်တွေ့မှာ အသုံးနည်းပေမယ့် Network သင်ကြားရေးအတွက် အဓိက Model တစ်ခုပါပဲ။

**OSI Model ရဲ့ အလွှာ ၇ လွှာ:**

| Layer No.   | Layer Name       | Functions (လုပ်ဆောင်ချက်များ)                                                           | Devices (အသုံးပြုစက်ပစ္စည်းများ) |
| :---------- | :--------------- | :-------------------------------------------------------------------------------------- | :------------------------------- |
| **Layer 7** | **Application**  | အသုံးပြုသူအတွက် ကွန်ရက်ဝန်ဆောင်မှုများ (Web Browser, Email Client, File Transfer)       | PC, Web Server                   |
| **Layer 6** | **Presentation** | Data Format ပြောင်းလဲခြင်း၊ Compression, Encryption (ဒေတာတွေကို စနစ်တကျ ပြောင်းလဲခြင်း) | PC                               |
| **Layer 5** | **Session**      | ကွန်ရက်ချိတ်ဆက်မှုများ စတင်၊ ထိန်းချုပ်၊ ပြီးဆုံးစေခြင်း (Login / Logout)               | PC                               |
| **Layer 4** | **Transport**    | Data ကို Segments များအဖြစ် ခွဲခြင်း၊ Flow Control၊ Error Handling (TCP, UDP)           | Router, Firewall                 |
| **Layer 3** | **Network**      | Logical Addressing (IP Address) နဲ့ Routing (လမ်းကြောင်းရှာခြင်း)                       | Router                           |
| **Layer 2** | **Data Link**    | Physical Addressing (MAC Address) နဲ့ Frame Creation (ဒေတာလင့်ခ်ဖရိမ်များ ဖန်တီးခြင်း)  | Switch                           |
| **Layer 1** | **Physical**     | Physical Transmission (ကေဘယ်၊ ရေဒီယိုလှိုင်းများမှ ဒေတာပို့ခြင်း)                       | Hub, Repeater, Cables            |

### **2. TCP/IP Model (အလွှာ ၄ လွှာပါတဲ့ Model)**

TCP/IP Model ဟာ OSI Model ကို အခြေခံထားပေမယ့် လက်တွေ့ Internet နဲ့ Networking မှာ အဓိက အသုံးပြုနေတဲ့ Model ဖြစ်ပါတယ်။ ဒါကြောင့် Practical (လက်တွေ့) အပိုင်းအတွက် ပိုအရေးကြီးပါတယ်။

**TCP/IP Model ရဲ့ အလွှာ ၄ လွှာ:**

| Layer No.   | Layer Name         | OSI Layers (နှိုင်းယှဉ်ချက်)       | Protocols (ဥပမာ)     |
| :---------- | :----------------- | :--------------------------------- | :------------------- |
| **Layer 4** | **Application**    | Application, Presentation, Session | HTTP, FTP, SMTP, DNS |
| **Layer 3** | **Transport**      | Transport                          | TCP, UDP             |
| **Layer 2** | **Internet**       | Network                            | IP, ICMP             |
| **Layer 1** | **Network Access** | Data Link, Physical                | Ethernet, Wi-Fi      |

### **Networking Model ရဲ့ အဓိကရည်ရွယ်ချက်များ**

- **ရှုပ်ထွေးမှုကို ဖြေရှင်းရန်:** Network စနစ်တစ်ခုရဲ့ ရှုပ်ထွေးတဲ့လုပ်ဆောင်ချက်တွေကို သေးငယ်တဲ့ အလွှာငယ်လေးတွေအဖြစ် ခွဲခြမ်းစိတ်ဖြာနိုင်ခြင်း။
- **စံနှုန်းသတ်မှတ်ရန်:** မတူညီတဲ့ Vendors (Cisco, Juniper, HP) တွေရဲ့ စက်ပစ္စည်းတွေဟာ Protocol Standard (ဥပမာ- Ethernet, TCP/IP) တွေကို လိုက်နာပြီး အချင်းချင်း ချိတ်ဆက်ပြောဆိုနိုင်ရန် စံနှုန်းသတ်မှတ်ပေးခြင်း။
- **ပြဿနာရှာဖွေရန်:** Network မှာ ပြဿနာတစ်ခုဖြစ်တဲ့အခါ (ဥပမာ- အင်တာနက်မရတာ)၊ ဘယ်အလွှာမှာ ပြဿနာဖြစ်နေလဲဆိုတာကို စနစ်တကျ လိုက်လံစစ်ဆေးနိုင်ခြင်း (ဥပမာ- Layer 1 (Cable) အလုပ်လုပ်ရဲ့လား၊ Layer 3 (IP) ရောက်ရဲ့လား စသဖြင့်)။

ဒါကြောင့် Networking Model ဟာ Network စနစ်ရဲ့ လုပ်ဆောင်ပုံကို စနစ်တကျနဲ့ နားလည်လွယ်အောင် ပြသပေးတဲ့ Framework တစ်ခု ဖြစ်ပါတယ်ခင်ဗျာ။
