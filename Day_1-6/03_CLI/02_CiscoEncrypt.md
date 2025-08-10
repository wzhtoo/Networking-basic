# Cisco Encryption Methods

လုပ်ဆောင်ခဲ့တဲ့ အဆင့်တွေက ဒီလိုပါ:

1.  `password ccna` (or similar) နဲ့ Console Password တစ်ခုထားခဲ့တယ်။
2.  `enable secret Cisco` နဲ့ Privileged EXEC mode အတွက် Password တစ်ခုထားခဲ့တယ်။
3.  `show run` နဲ့ကြည့်တော့ `enable secret` က **MD5 hash** နဲ့ Encrypt လုပ်ထားတာကို တွေ့ခဲ့တယ်။

သင့်ရဲ့ မေးခွန်းက "ဒီအခြေအနေမှာ MD5 Encryption မဟုတ်ဘဲ တခြား Encryption နည်းလမ်းကို ဘယ်လိုသုံးမလဲ" ဆိုတာ ဖြစ်ပါတယ်။

ဒီမေးခွန်းရဲ့ အဖြေကတော့ **`enable secret` command ကိုယ်တိုင်က MD5 Hash ကိုပဲ အသုံးပြုဖို့ သီးသန့်ဒီဇိုင်းလုပ်ထားတာဖြစ်တဲ့အတွက်၊ တခြား Encryption နည်းလမ်းကို တိုက်ရိုက်ပြောင်းလို့မရပါဘူး** ခင်ဗျာ။

### **ရှင်းလင်းချက် အဆင့်ဆင့်**

#### **1. `enable secret` နဲ့ `enable password` ရဲ့ ကွာခြားချက်**

Cisco မှာ Password သတ်မှတ်တဲ့ Command ၂ ခု ရှိပါတယ်။

- **`enable secret`**:

  - `enable secret` command ဟာ **Security ကို အဓိကထားပြီး MD5 hashing Algorithm** ကို အသုံးပြုပါတယ်။
  - MD5 ဟာ **One-way Hash** ဖြစ်လို့ သူ့ကို Original Password ကို ပြန်ပြောင်းယူလို့ မရပါဘူး။ ဒါကြောင့် အလွန်လုံခြုံပါတယ်။ `show run` မှာဆိုရင် MD5 Hash ကိုပဲ တွေ့ရမှာပါ။
  - ဒါဟာ Cisco ရဲ့ **Recommended (အကြံပြုထားတဲ့) Password Method** ဖြစ်ပါတယ်။

- **`enable password`**:
  - `enable password` command ဟာ Security ကို အဓိကမထားဘဲ၊ **Type 7 Encryption** လို့ခေါ်တဲ့ အားနည်းတဲ့ Encryption နည်းလမ်းကိုပဲ သုံးပါတယ်။
  - ဒီ Type 7 Encryption ဟာ လွယ်ကူစွာ Decoding ပြန်လုပ်နိုင်တဲ့အတွက် လုံးဝ မလုံခြုံပါဘူး။ `show run` မှာ Encrypt လုပ်ထားတဲ့ Password ကို တွေ့ရပေမယ့် အလွယ်တကူ ပြန်ဖတ်လို့ရပါတယ်။

#### **2. `service password-encryption` command ရဲ့ အခန်းကဏ္ဍ**

- `service password-encryption` command ကို သုံးလိုက်ရင် `enable password` လိုမျိုး Plain-text (ဖတ်လို့ရတဲ့စာသား) နဲ့ ရိုက်ထည့်ထားတဲ့ Password တွေကို **Type 7 Encryption** နဲ့ Encrypt လုပ်ပေးပါတယ်။
- ဒါဟာ Console Password လိုမျိုး `line vty` တွေမှာ သုံးထားတဲ့ Password တွေကို ဖတ်လို့ရတဲ့စာသားအဖြစ် မပြစေဖို့ပဲ ဖြစ်ပါတယ်။
- ဒီ Command ဟာ `enable secret` နဲ့တော့ မသက်ဆိုင်ပါဘူး။

#### **3. သင့်ရဲ့ အခြေအနေအတွက် အဖြေ**

- `enable secret Cisco` လို့ သတ်မှတ်လိုက်တဲ့အချိန်မှာ Cisco IOS က Automatic အနေနဲ့ **MD5 hash** ကို တွက်ချက်လိုက်ပြီး Running-config ထဲမှာ သိမ်းလိုက်ပါတယ်။
- သင်ဟာ **MD5 hash မဟုတ်တဲ့ တခြား Encryption နည်းလမ်းတစ်ခုကို `enable secret` နဲ့ တွဲပြီး သုံးဖို့ တိုက်ရိုက် command မရှိပါဘူး**။ `enable secret` ဟာ MD5 အတွက်ပဲ ဖြစ်ပါတယ်။

### **ဘယ်လိုလုပ်သင့်လဲ**

- သင်ဟာ `enable secret` ကို အသုံးပြုထားတာဟာ လုံခြုံမှုအရှိဆုံးဖြစ်တဲ့အတွက် ဒါကိုပဲ ဆက်လက် အသုံးပြုသင့်ပါတယ်။
- MD5 ဟာ Hash Algorithm ဖြစ်လို့ **Encryption လို့ ခေါ်ဆိုပေမယ့် One-way Hash** ဖြစ်တာကြောင့် Password ကို ပြန်ပြောင်းလို့မရနိုင်ပါဘူး။
- တကယ်လို့ သင်ဟာ MD5 ထက် ပိုပြီးလုံခြုံတဲ့ Hashing Algorithms (ဥပမာ- SHA-256) ကို သုံးချင်တယ်ဆိုရင် Cisco IOS Versions အသစ်တွေနဲ့ `username` command ကိုသုံးပြီး Local User Account တွေအတွက် **SHA-256** ကို သုံးနိုင်ပါတယ်။ ဒါပေမယ့် `enable secret` command မှာတော့ MD5 ကိုပဲ သုံးနိုင်ပါသေးတယ်။

ဒါကြောင့် သင့်ရဲ့ မေးခွန်းအတွက် အနှစ်ချုပ်ကတော့ `enable secret` ဟာ လုံခြုံတဲ့ MD5 ကိုပဲသုံးဖို့ ရည်ရွယ်ထားတဲ့ Command ဖြစ်ပြီး၊ တခြား Encryption နည်းလမ်းတစ်ခုကို တိုက်ရိုက်ပြောင်းလို့မရပါဘူးခင်ဗျာ။
