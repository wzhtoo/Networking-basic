# Network portion, host portion of IPv4 address

Network Portion နဲ့ Host Portion ဆိုတာ IPv4 Addressing ရဲ့ အလွန်အရေးကြီးတဲ့ အစိတ်အပိုင်းနှစ်ခုဖြစ်ပါတယ်။ ဒီအကြောင်းအရာက Subnetting ကို နားလည်ဖို့အတွက် မဖြစ်မနေသိထားရမှာပါခင်ဗျာ။

### **Network Portion (Network ID)**

- **တာဝန်:** Network Portion ဟာ IP Address ရဲ့ အပိုင်းတစ်ခုဖြစ်ပြီး Device တစ်ခုဟာ **`ဘယ် Network`** ထဲမှာရှိတယ်ဆိုတာကို ဖော်ပြပါတယ်။
- **အင်္ဂါရပ်:** တူညီတဲ့ Local Network (LAN) ထဲမှာရှိတဲ့ Devices တွေအားလုံးဟာ **Network Portion ကို တူညီစွာမျှဝေသုံးစွဲပါတယ်**။
- **ဥပမာ:** `192.168.1.0/24` Network မှာ `192.168.1` ဆိုတဲ့အပိုင်းဟာ Network Portion ဖြစ်ပါတယ်။

### **Host Portion (Host ID)**

- **တာဝန်:** Host Portion ဟာ Network Portion ရဲ့ နောက်ကနေပါလာပြီး အဲဒီ Network ထဲမှာရှိတဲ့ **`Device တစ်ခုချင်းစီကို ခွဲခြားသတ်မှတ်ပေးတဲ့`** အပိုင်းဖြစ်ပါတယ်။
- **အင်္ဂါရပ်:** တူညီတဲ့ Network ထဲမှာရှိတဲ့ Devices တွေအားလုံးဟာ **Host Portion ကို တစ်ခုနဲ့တစ်ခုမတူအောင် (Unique) သုံးရပါမယ်**။
- **ဥပမာ:** `192.168.1.1` လို့ဆိုတဲ့ IP Address မှာ နောက်ဆုံးက `1` ဟာ Host Portion ဖြစ်ပါတယ်။

### **Network နဲ့ Host ကို ဘယ်လိုခွဲခြားသလဲ။**

Network Portion နဲ့ Host Portion ကို ဘယ်နေရာကနေ စတင်ခွဲခြားလဲဆိုတာကို **`Subnet Mask`** ကနေ အတိအကျသတ်မှတ်ပေးပါတယ်။

- **Subnet Mask မှာ `1` ဖြစ်နေတဲ့ bits များဟာ IP Address ရဲ့ Network Portion ကို ကိုယ်စားပြုပါတယ်**။
- **Subnet Mask မှာ `0` ဖြစ်နေတဲ့ bits များဟာ IP Address ရဲ့ Host Portion ကို ကိုယ်စားပြုပါတယ်**။

### **ဥပမာ - `192.168.1.1` & `/24` Subnet Mask**

- **IP Address:** `192.168.1.1` -> Binary: **`11000000.10101000.00000001`**.00000001
- **Subnet Mask:** `255.255.255.0` -> Binary: **`11111111.11111111.11111111`**.00000000

ဒီဥပမာမှာ Subnet Mask ရဲ့ ရှေ့ဆုံးက Bits 24 ခု (11111111.11111111.11111111) ဟာ `1` တွေဖြစ်နေတဲ့အတွက် IP Address ရဲ့ ရှေ့ဆုံးက **`192.168.1`** ဆိုတဲ့အပိုင်းဟာ **Network Portion** ဖြစ်ပါတယ်။

နောက်ဆုံးက Bits 8 ခု (00000000) ဟာ `0` တွေဖြစ်နေတဲ့အတွက် IP Address ရဲ့ နောက်ဆုံးက **`.1`** ဆိုတဲ့အပိုင်းဟာ **Host Portion** ဖြစ်ပါတယ်။

**အနှစ်ချုပ်:**

Network Portion နဲ့ Host Portion ဟာ IP Address တစ်ခုရဲ့ အခြေခံဖွဲ့စည်းပုံဖြစ်ပြီး Subnet Mask နဲ့ ပေါင်းစပ်လိုက်တဲ့အခါ Network တွေကို အပိုင်းလိုက်ခွဲခြားဖို့နဲ့ Routing လုပ်နိုင်ဖို့ အဓိကကျတဲ့ အခန်းကဏ္ဍကနေ ပါဝင်ပါတယ်ခင်ဗျာ။
