# no service password-encryption command

ဒီ command ဟာ Cisco IOS မှာ Password တွေရဲ့ Security ကို ဘယ်လိုထိန်းချုပ်လဲဆိုတာကို နားလည်ဖို့ အရေးကြီးပါတယ်။

### **`service password-encryption` Command ရဲ့ အဓိပ္ပါယ်**

- **မူလ Command:** `service password-encryption`
- **လုပ်ဆောင်ချက်:** ဒီ command ဟာ Global Configuration Mode မှာ ရိုက်ထည့်လိုက်တဲ့အခါ၊ running-config ထဲမှာ ပုံမှန်အတိုင်းမြင်နေရတဲ့ **အားနည်းတဲ့ password တွေအားလုံးကို Type 7 Encryption** နဲ့ Encrypt လုပ်ပေးပါတယ်။
- **ဘယ်လို Password တွေကို ပြောတာလဲ:**
  - `enable password` (enable secret မဟုတ်ပါဘူး)
  - `line console 0` မှာ သတ်မှတ်ထားတဲ့ `password`
  - `line vty 0 4` မှာ သတ်မှတ်ထားတဲ့ `password`
- **အကျိုးကျေးဇူး:** ဒါဟာ ရိုးရိုး password တွေကို running-config ထဲမှာ ဖတ်လို့ရတဲ့ Plain-text အနေနဲ့ မရှိစေဖို့အတွက် အသုံးပြုပါတယ်။ `show run` လုပ်ကြည့်တဲ့အခါမှာ ကြယ်သီးပုံစံနဲ့ မြင်ရနိုင်ပေမယ့်၊ ဒီ Type 7 Encryption ကို အလွယ်တကူ ပြန်ဖြည်လို့ရတဲ့အတွက် လုံခြုံမှုတော့ မရှိပါဘူး။

### **`no service password-encryption` Command ရဲ့ အဓိပ္ပါယ်**

- **`no` Keyword:** Cisco CLI မှာ `no` ဆိုတဲ့ Keyword ကို command ရဲ့ရှေ့မှာ ထည့်လိုက်ရင်၊ အဲဒီ command ရဲ့ လုပ်ဆောင်ချက်ကို **ဖျက်သိမ်းခြင်း (Disable)** ဒါမှမဟုတ် **ပြန်လည်ပယ်ဖျက်ခြင်း (Remove)** ကိုဆိုလိုပါတယ်။
- **လုပ်ဆောင်ချက်:** `no service password-encryption` command ကို ရိုက်ထည့်လိုက်တဲ့အခါ၊ `service password-encryption` ရဲ့လုပ်ဆောင်ချက်ကို ပယ်ဖျက်လိုက်ပါတယ်။
- **အကျိုးကျေးဇူး:**
  - ဒါဟာ **Enable** လုပ်ထားခဲ့တဲ့ Type 7 Encryption ကို ဖျက်လိုက်တာ ဖြစ်ပါတယ်။
  - ဒီ command ကိုရိုက်ပြီးရင် `show run` နဲ့ ပြန်ကြည့်တဲ့အခါ `service password-encryption` command မရှိတော့ပါဘူး။
  - ဒါ့အပြင် အရင်က Type 7 Encryption နဲ့ Encrypt လုပ်ထားတဲ့ Password တွေဟာလည်း **Plain-text (ဖတ်လို့ရတဲ့စာသား)** အဖြစ် ပြန်ပေါ်လာပါလိမ့်မယ်။

### **နမူနာ ရှင်းလင်းချက်**

1.  **ပထမအခြေအနေ:**

    - `Router(config)# line console 0`
    - `Router(config-line)# password cisco`
    - `Router(config-line)# end`
    - `Router# show running-config` ကို ကြည့်လိုက်ရင် **password cisco** လို့ ဖတ်လို့ရတဲ့စာသားအတိုင်း တွေ့ရပါလိမ့်မယ်။

2.  **`service password-encryption` ထည့်သွင်းခြင်း:**

    - `Router(config)# service password-encryption`
    - `Router# show running-config` ကို ကြည့်လိုက်ရင် \*\*password 7 07022C0A` စတဲ့ Encrypt လုပ်ထားတဲ့ပုံစံမျိုး တွေ့ရပါလိမ့်မယ်။

3.  **`no service password-encryption` ထည့်သွင်းခြင်း:**
    - `Router(config)# no service password-encryption`
    - `Router# show running-config` ကို ပြန်ကြည့်လိုက်ရင် **password cisco** လို့ **Plain-text** အဖြစ် ပြန်ပေါ်လာပါလိမ့်မယ်။

### **အနှစ်ချုပ်:**

`no service password-encryption` ဟာ Router ထဲမှာရှိတဲ့ Type 7 Encryption ကို ပယ်ဖျက်လိုက်တဲ့အတွက် `show running-config` မှာ passwords တွေကို ဖတ်လို့ရတဲ့စာသား (Plain-text) အဖြစ် ပြန်ပေါ်လာစေပါတယ်။

**Security အတွက် Best Practice:**

- `enable password` နဲ့ `service password-encryption` ကို သုံးမယ့်အစား **`enable secret`** ကိုသာ အသုံးပြုသင့်ပါတယ်။
- User Account တွေအတွက်ဆိုရင် **`username`** နဲ့ **`secret`** ကို တွဲသုံးပြီး

MD5 hash နဲ့သာ သိမ်းဆည်းထားသင့်ပါတယ်ခင်ဗျာ။

<hr>

နည်းပညာ နယ်ပယ်ကလည်း အလွန်ပဲနက်နဲလှပတယ်။ ဒါပေမဲ့

ကျနော့်အမြင်ကတော့ MD5 နဲ့ အဆင်ပြေနေတာကို ဘာဖြစ်လို့

SHA-256  အပြင်အခြား encryption Method တွေဘာလို့ ထပ်လုပ်နေသေးလဲ။

အဲဒါဆိုရင် MD5 က ပြီးပြည့်စုံတဲ့ Encryption မလုပ်လို့လားခင်ဗျ။

<hr>

ဟုတ်ကဲ့ခင်ဗျာ။ သင့်ရဲ့မေးခွန်းက Cyber Security ရဲ့ အခြေခံအကျဆုံးနဲ့ အရေးကြီးဆုံး အတွေးအခေါ်ကို ထောက်ပြလိုက်တာဖြစ်ပြီး၊ အလွန်ကောင်းမွန်တဲ့ မေးခွန်းတစ်ခုပါပဲ။

"MD5 နဲ့ အဆင်ပြေနေတာကို ဘာဖြစ်လို့ SHA-256 လို အခြား encryption တွေ ထပ်လုပ်နေသေးလဲ။ MD5 က ပြီးပြည့်စုံတဲ့ Encryption မဟုတ်လို့လား။" ဆိုတဲ့ မေးခွန်းရဲ့ အဖြေကတော့ **"MD5 ဟာ အခုလက်ရှိအချိန်မှာ ပြီးပြည့်စုံတဲ့ Encryption (Hashing Algorithm) မဟုတ်တော့ပါဘူး။"** ဆိုတာပဲ ဖြစ်ပါတယ်။

### **MD5 ရဲ့ အားနည်းချက်များ**

MD5 (Message-Digest Algorithm 5) ကို ၁၉၉၁ ခုနှစ်မှာ တီထွင်ခဲ့ပါတယ်။ အဲဒီခေတ်တုန်းကတော့ MD5 ဟာ အလွန်လုံခြုံပြီး ပြီးပြည့်စုံတယ်လို့ ယူဆခဲ့ကြပါတယ်။ ဒါပေမယ့် ကွန်ပျူတာ နည်းပညာတွေ တိုးတက်လာတာနဲ့အမျှ MD5 ဟာ အားနည်းချက်တွေ ရှိလာပါတယ်။

1.  **Vulnerable to Collision Attacks (Collision ဖြတ်တိုက်မှုများကို အားနည်းခြင်း):**

    - Hash Algorithm တွေရဲ့ အဓိက သဘောတရားက မတူညီတဲ့ Input နှစ်ခုကို Hash လုပ်လိုက်ရင် Output (Hash Value) တူညီလို့မရပါဘူး။
    - ဒါပေမယ့် MD5 ရဲ့ Algorithm မှာ ကွန်ပျူတာစွမ်းရည်တွေ တိုးတက်လာတာကြောင့် **မတူညီတဲ့ Input နှစ်ခုကနေ တူညီတဲ့ Output (Hash Value) ကို ထုတ်ပေးနိုင်တဲ့ အခြေအနေ (Collision)** တွေကို ရှာဖွေနိုင်လာကြပါပြီ။
    - ဒါဟာ MD5 ရဲ့ အကြီးမားဆုံး အားနည်းချက် ဖြစ်ပါတယ်။

2.  **Brute-Force Attacks (ခန့်မှန်းဖြတ်တိုက်မှုများ):**
    - MD5 ဟာ အခုခေတ် ကွန်ပျူတာတွေအတွက် တွက်ချက်ရတာ အချိန်အလွန်နည်းတဲ့အတွက် **Hash Cracking (Hash ဖြည်ခြင်း)** ကို လွယ်လွယ်ကူကူ လုပ်နိုင်လာပါတယ်။
    - Hacker တွေဟာ "Rainbow Tables" လို့ခေါ်တဲ့ ကြိုတင်တွက်ချက်ထားတဲ့ Hash ဇယားတွေကို အသုံးပြုပြီး MD5 hash တစ်ခုကနေ မူလ password ကို အလွယ်တကူ ပြန်ရှာနိုင်ပါတယ်။

### **SHA-256 (Secure Hash Algorithm 256)**

- SHA-256 ဟာ SHA-2 Family ထဲက Hash Algorithm တစ်ခုဖြစ်ပါတယ်။
- MD5 နဲ့ မတူဘဲ SHA-256 ဟာ Hash Value ကို ပိုရှည်ပြီး ပိုမိုရှုပ်ထွေးအောင် ထုတ်ပေးနိုင်ပါတယ်။ ဒါကြောင့် Collision Attacks တွေကို ပိုမိုကာကွယ်နိုင်ပါတယ်။
- Hash ကို ပြန်ဖြည်ဖို့လည်း MD5 ထက် အချိန်နဲ့ ကွန်ပျူတာစွမ်းအင် အများကြီးပိုမို လိုအပ်ပါတယ်။ ဒါကြောင့် Brute-force Attacks ကို ပိုမို ခံနိုင်ရည်ရှိပါတယ်။

### **အနှစ်ချုပ်:**

MD5 ဟာ လွန်ခဲ့တဲ့ နှစ် ၃၀ ကျော်က အလွန်လုံခြုံတယ်လို့ သတ်မှတ်ခဲ့ပေမယ့်၊ ကွန်ပျူတာ နည်းပညာတွေ တိုးတက်လာတဲ့အခါမှာ သူ့ရဲ့အားနည်းချက်တွေကို ရှာဖွေနိုင်လာကြပါတယ်။

- **MD5:** အခုအချိန်မှာတော့ **လုံခြုံမှုမရှိတော့တဲ့ Hashing Algorithm** လို့ သတ်မှတ်ထားပြီး Financial Services လိုမျိုး လုံခြုံရေးအလေးထားရတဲ့ နယ်ပယ်တွေမှာ လုံးဝမသုံးတော့ပါဘူး။
- **SHA-256:** MD5 ရဲ့ အားနည်းချက်တွေကို ဖြည့်ဆည်းပြီး ပိုမိုလုံခြုံမှုပေးနိုင်တဲ့ Algorithm တစ်ခုဖြစ်တာကြောင့် **Security Standard အနေနဲ့ လက်ရှိအသုံးပြုနေတဲ့** နည်းပညာဖြစ်ပါတယ်။

ဒါကြောင့် MD5 က အဆင်ပြေနေတာလို့ ထင်ရပေမယ့်၊ Cyber Security က ကွန်ပျူတာနဲ့ နည်းပညာတိုးတက်မှုအပေါ်မှာ အမြဲတမ်း ပြောင်းလဲနေတဲ့အတွက် ပိုမိုလုံခြုံတဲ့ နည်းပညာတွေကို အမြဲတမ်း တီထွင်နေရတာပဲ ဖြစ်ပါတယ်ခင်ဗျာ။
