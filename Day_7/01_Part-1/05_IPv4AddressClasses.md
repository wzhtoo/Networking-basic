# IPv4 address classes

IPv4 Address Classes အကြောင်းကို အသေးစိတ်ရှင်းပြပေးပါမယ်။ IPv4 Address တွေကို အစောပိုင်းကာလတွေမှာ Networks တွေကို အရွယ်အစားအလိုက် ခွဲခြားဖို့အတွက် Classify လုပ်ခဲ့တာ ဖြစ်ပါတယ်။ ဒီစနစ်ကို **Classful Addressing** လို့ခေါ်ပါတယ်ခင်ဗျာ။

အဓိကအားဖြင့် IP Address Classes (5) မျိုးရှိပါတယ်- Class A, Class B, Class C, Class D နဲ့ Class E တို့ပဲဖြစ်ပါတယ်။

### **၁။ Class A**

- **IP Address Range:** `1.0.0.0` မှ `126.255.255.255` အထိဖြစ်ပါတယ်။
- **Binary (ပထမ Octet):** ပထမဆုံး Octet ရဲ့ ပထမဆုံး Bit က **`0`** ဖြစ်ပါတယ်။
- **Network & Host Portion:** ပထမဆုံး Octet က Network Portion (Network ID) ဖြစ်ပြီး ကျန်တဲ့ Octet (3) ခုက Host Portion (Host ID) ဖြစ်ပါတယ်။ ဒါကြောင့် Host ပေါင်းများစွာ ပါဝင်တဲ့ Network ကြီးတွေအတွက် ရည်ရွယ်ပါတယ်။
- **Default Subnet Mask:** `255.0.0.0` သို့မဟုတ် `/8` ဖြစ်ပါတယ်။

### **၂။ Class B**

- **IP Address Range:** `128.0.0.0` မှ `191.255.255.255` အထိဖြစ်ပါတယ်။
- **Binary (ပထမ Octet):** ပထမဆုံး Octet ရဲ့ ပထမဆုံး Bit နှစ်ခုက **`10`** ဖြစ်ပါတယ်။
- **Network & Host Portion:** ပထမဆုံး Octet (2) ခုက Network Portion ဖြစ်ပြီး ကျန်တဲ့ Octet (2) ခုက Host Portion ဖြစ်ပါတယ်။ ဒါကြောင့် အလယ်အလတ်အရွယ်အစားရှိတဲ့ Networks တွေအတွက် ရည်ရွယ်ပါတယ်။
- **Default Subnet Mask:** `255.255.0.0` သို့မဟုတ် `/16` ဖြစ်ပါတယ်။

### **၃။ Class C**

- **IP Address Range:** `192.0.0.0` မှ `223.255.255.255` အထိဖြစ်ပါတယ်။
- **Binary (ပထမ Octet):** ပထမဆုံး Octet ရဲ့ ပထမဆုံး Bit သုံးခုက **`110`** ဖြစ်ပါတယ်။
- **Network & Host Portion:** ပထမဆုံး Octet (3) ခုက Network Portion ဖြစ်ပြီး နောက်ဆုံး Octet (1) ခုက Host Portion ဖြစ်ပါတယ်။ ဒါကြောင့် Host အရေအတွက်အနည်းငယ်ပါဝင်တဲ့ Networks တွေအတွက် ရည်ရွယ်ပါတယ်။
- **Default Subnet Mask:** `255.255.255.0` သို့မဟုတ် `/24` ဖြစ်ပါတယ်။

### **၄။ Class D နှင့် E**

- **Class D:** `224.0.0.0` မှ `239.255.255.255` အထိဖြစ်ပြီး Multicasting အတွက် အသုံးပြုပါတယ်။
- **Class E:** `240.0.0.0` မှ `255.255.255.255` အထိဖြစ်ပြီး Research နဲ့ Experimental purposes အတွက် Reserved (ကြိုတင်ထားရှိ) လုပ်ထားပါတယ်။

### **Classful Addressing ရဲ့ အားနည်းချက်**

Classful Addressing ဟာ IPv4 Address တွေကို ဖြုန်းတီးရာရောက်ပြီး အသုံးမဝင်တော့တဲ့အတွက် **Classless Inter-Domain Routing (CIDR)** လို့ခေါ်တဲ့ စနစ်သစ်နဲ့ အစားထိုးခဲ့ပါတယ်။ ယနေ့ခေတ်မှာ Network တွေကို Class အလိုက်ခွဲခြားတာမျိုးမရှိတော့ဘဲ `/24` လိုမျိုး CIDR Notation ကိုပဲ အသုံးပြုနေကြတာဖြစ်ပါတယ်။
