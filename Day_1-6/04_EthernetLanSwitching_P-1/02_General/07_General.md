- အဲဒါဆိုရင် attacker က victims တွေဆီကို milicious file တစ်ခုပို့လိုက်တယ်ဆိုပါတော့။ အဲဒီဖိုင်အမျိုးအစားကို SOC အင်ဂျင်နီယာက ခုနက ဖော်ပြတဲ့ 1536 တို့ဖြစ်တဲ့ type နဲ့ length တွေကို ဆုံးဖြတ်ပြီး ဘယ်လိုအမျိုးအစား file လဲ ဘယ်ကပို့တာလဲ ဆိုတာကို ဆုံးဖြတ်တာလားခင်ဗျ။

ဟုတ်ကဲ့ခင်ဗျာ။ သင့်ရဲ့မေးခွန်းက အလွန်ကောင်းမွန်ပြီး Network Layer တွေရဲ့ အလုပ်လုပ်ပုံကို Security Engineers တွေ ဘယ်လိုအသုံးချလဲဆိုတာကို တွေးခေါ်လိုက်တာ ဖြစ်ပါတယ်။ ဒါပေမယ့် သင့်ရဲ့ အယူအဆတစ်ခုကို ပြန်လည်ရှင်းလင်းပေးပါမယ်။

**"SOC အင်ဂျင်နီယာက Type or Length field (ဥပမာ- `0x0800`) ကို ကြည့်ပြီး ဖိုင်အမျိုးအစားနဲ့ ပို့တဲ့သူကို ဆုံးဖြတ်တာလား"** ဆိုတဲ့ မေးခွန်းရဲ့ အဖြေကတော့ **"မဟုတ်ပါဘူး"** ခင်ဗျာ။

`Type or Length` field ရဲ့ လုပ်ဆောင်ချက်ဟာ သင်ပြောတဲ့ ဖိုင်အမျိုးအစား၊ ဒါမှမဟုတ် ပို့တဲ့သူကို ဆုံးဖြတ်တာမျိုးမဟုတ်ပါဘူး။

### **Type or Length Field ရဲ့ အမှန်တကယ် အခန်းကဏ္ဍ**

- `Type or Length` field ဟာ **Layer 2 (Data Link Layer)** မှာပဲ အဓိက သက်ဆိုင်ပြီး၊ သူ့ရဲ့တန်ဖိုး (ဥပမာ- `0x0800` or `0x0806`) က Frame ရဲ့ Payload ထဲမှာ ဘယ်လို **`Network Layer Protocol`** ပါလာလဲဆိုတာကိုပဲ ပြောပြပေးတာ ဖြစ်ပါတယ်။
- ဥပမာ- `Type` field က `0x0800` ဆိုရင် Network Card (NIC) က Frame ရဲ့ Payload ကို **IPv4 Packet** ဖြစ်ကြောင်းသိရှိပြီး Layer 3 မှာရှိတဲ့ IP Protocol Stack ဆီကို လွှဲပေးလိုက်ပါတယ်။

### **SOC အင်ဂျင်နီယာတစ်ယောက်ရဲ့ လုပ်ဆောင်ပုံ**

SOC (Security Operations Center) အင်ဂျင်နီယာတစ်ယောက်ဟာ Malicious file တစ်ခုကို ခွဲခြမ်းစိတ်ဖြာတဲ့အခါ `Type or Length` field ကို ကြည့်မနေပါဘူး။ သူတို့ဟာ ပိုပြီး အသေးစိတ်တဲ့ အချက်အလက်တွေကို အောက်ပါအတိုင်း ရှာဖွေပါတယ်။

#### **1. ဖိုင်အမျိုးအစား (File Type) ကို ဘယ်လိုဆုံးဖြတ်လဲ။**

ဖိုင်အမျိုးအစားကို ဆုံးဖြတ်ဖို့အတွက် SOC အင်ဂျင်နီယာက OSI Model ရဲ့ **Layer 7 (Application Layer)** နဲ့ **ဖိုင်ရဲ့အတွင်းပိုင်းဖွဲ့စည်းပုံ** ကို ကြည့်ပါတယ်။

- **Application Layer Protocols:** ဖိုင်ကို HTTP, HTTPS, FTP, or SMTP စတဲ့ Protocols တွေနဲ့ပို့တာဖြစ်တဲ့အတွက် SOC Engineer ဟာ အဲဒီ Protocol Headers တွေကို ကြည့်ပြီး ဖိုင်ကို ဘယ်လိုပို့လိုက်လဲဆိုတာကို သိနိုင်ပါတယ်။
- **File Header & Magic Number:** ကွန်ပျူတာမှာရှိတဲ့ ဖိုင်တိုင်းမှာ သူ့ရဲ့ ဖိုင်အမျိုးအစားကို ဖော်ပြတဲ့ Code (Magic Number) တွေရှိပါတယ်။ ဥပမာ- `PDF` ဖိုင်တွေဆိုရင် `%PDF-` နဲ့ စပြီး `JPEG` ဖိုင်ဆိုရင် `FF D8` နဲ့ စပါတယ်။ SOC Engineer ဟာ ဒီ Magic Number တွေကို ဖတ်ပြီး ဖိုင်အမျိုးအစားကို အတိအကျသိနိုင်ပါတယ်။
- **File Extension:** ဖိုင်ရဲ့ နာမည်နောက်က `.exe`, `.pdf`, `.zip` စတဲ့ Extension တွေကိုလည်း စစ်ဆေးပါတယ်။

#### **2. ဘယ်ကပို့တာလဲ (Origin) ကို ဘယ်လိုဆုံးဖြတ်လဲ။**

မူလအစကို ဆုံးဖြတ်ဖို့အတွက် SOC Engineer ဟာ OSI Model ရဲ့ **Layer 3 (Network Layer)** နဲ့ **Layer 7 (Application Layer)** တို့ကို ကြည့်ပါတယ်။

- **Layer 3: IP Address:** Network Traffic ကို စောင့်ကြည့်တဲ့အခါ **`Source IP Address`** ကို သိရှိနိုင်ပါတယ်။ အဲဒီ IP Address ဟာ Attack ကို စတင်ခဲ့တဲ့ Computer ရဲ့ IP ဖြစ်ပါတယ်။ ဒါကို Whois Database လိုမျိုး Tools တွေနဲ့ အသုံးပြုပြီး ဘယ်နိုင်ငံ၊ ဘယ် Service Provider ကလဲဆိုတာကို ရှာဖွေနိုင်ပါတယ်။
- **Layer 7: Email Headers:** Email ကနေပို့တဲ့ Malicious file ဆိုရင် Email Header ထဲမှာပါတဲ့ `Sender's Address`, `Received From` စတဲ့အချက်အလက်တွေကိုကြည့်ပြီး ပို့တဲ့သူရဲ့ Origin ကို ခြေရာခံနိုင်ပါတယ်။

### **အနှစ်ချုပ်:**

- **`Type or Length` field (Layer 2):** Network Card အတွက် **Network Protocol** ကို ခွဲခြားပေးဖို့ပဲ ဖြစ်ပါတယ်။
- **SOC Engineer:** ဖိုင်ရဲ့ **`အမျိုးအစား (File Type)`** ကို သိရှိဖို့ **Application Layer Protocols** နဲ့ **ဖိုင်ရဲ့ Magic Number** တွေကို ကြည့်ပြီး၊ **`ဘယ်ကပို့တာလဲ (Origin)`** ဆိုတာကို သိရှိဖို့ **Layer 3 IP Address** နဲ့ **Application Headers** တွေကို ကြည့်ပြီး စစ်ဆေးပါတယ်ခင်ဗျာ။
