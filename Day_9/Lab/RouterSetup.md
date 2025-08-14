## Command Line

### ၁။ Mode အဆင့်ဆင့်သို့ ဝင်ရောက်ခြင်း

ဒီအပိုင်းကတော့ router ရဲ့ configuration တွေပြင်ဆင်နိုင်တဲ့ mode တွေထဲကို အဆင့်ဆင့်ဝင်ရောက်သွားတာဖြစ်ပါတယ်။

- `Router>en`
- `Router#en`
- `Router#enable`

  - **ရှင်းလင်းချက်**: ဒီသုံးခုစလုံးဟာ **`enable`** command ရဲ့ ပုံစံကွဲတွေဖြစ်ပါတယ်။ User EXEC Mode (`>`) ကနေ Privileged EXEC Mode (`#`) ကိုပြောင်းဖို့အတွက် သုံးပါတယ်။ `en` ဆိုတာက `enable` ရဲ့ အတိုကောက်ဖြစ်ပါတယ်။ `Router#` မှာ `en` ဒါမှမဟုတ် `enable` ကို ထပ်ရိုက်ရင်တော့ ဘာမှမဖြစ်တော့ပါဘူး၊ ဘာဖြစ်လို့လဲဆိုတော့ Privileged Mode ထဲကို ရောက်နှင့်နေလို့ဖြစ်ပါတယ်။

- `Router#conf`
- `Router(config)#conf`
- `Router(config)#conf t`

  - **ရှင်းလင်းချက်**: ဒီ command တွေက **`configure terminal`** ရဲ့ အတိုကောက်တွေပါ။ Privileged Mode (`#`) ကနေ Global Configuration Mode (`(config)#`) ထဲကိုဝင်ဖို့ သုံးပါတယ်။ ဒီ mode ထဲမှာ router တစ်ခုလုံးနဲ့ သက်ဆိုင်တဲ့ ပြင်ဆင်မှုတွေ ပြုလုပ်နိုင်ပါတယ်။ `conf` သို့မဟုတ် `conf t` က အသုံးအများဆုံး အတိုကောက်ပါ။

- `Configuring from terminal, memory, or network [terminal]?`
  - **ရှင်းလင်းချက်**: `conf` ဒါမှမဟုတ် `configure` လို့ပဲရိုက်ပြီး `terminal` လို့မထည့်ခဲ့ရင် router က ဒီမေးခွန်းကိုမေးပါတယ်။ "Configuration တွေကို ဘယ်ကနေစပြီး ပြင်ချင်တာလဲ" လို့မေးတာပါ။ Default အနေနဲ့က `terminal` (keyboard ကနေ ကိုယ်တိုင်ရိုက်ထည့်တာ) ဖြစ်တဲ့အတွက် **Enter** ခေါက်လိုက်ရုံပါပဲ။

---

### ၂။ Router Hostname ပြောင်းလဲခြင်း

- `Router(config)#host R1`
  - **ရှင်းလင်းချက်**: **`hostname`** command ရဲ့ အတိုကောက်ပါ။ Router ရဲ့ လက်ရှိနာမည်ဖြစ်တဲ့ "Router" ကို "R1" ဆိုပြီး ပြောင်းလိုက်တာဖြစ်ပါတယ်။ command ရိုက်ပြီးတာနဲ့ prompt က `Router(config)#` ကနေ **`R1(config)#`** ဆိုပြီး ချက်ချင်းပြောင်းသွားတာကို တွေ့ရပါမယ်။

---

### ၃။ Interface Configuration Mode သို့ ဝင်ရောက်ခြင်း

- `R1(config)#int`
- `R1(config)#interface g0/0`
  - **ရှင်းလင်းချက်**: **`interface`** command ရဲ့ အတိုကောက်က `int` ပါ။ `g0/0` ဆိုတာ `GigabitEthernet0/0` ကို အတိုကောက်ရေးထားတာပါ။ ဒီ command က router မှာရှိတဲ့ network port တွေထဲက **`GigabitEthernet0/0` ဆိုတဲ့ port တစ်ခုတည်းကို သီးသန့်**ပြင်ဆင်ဖို့အတွက် သူ့ရဲ့ configuration mode (`config-if`) ထဲကို ဝင်လိုက်တာဖြစ်ပါတယ်။

---

### ၄။ Interface Configuration များ ပြုလုပ်ခြင်း

ဒီအပိုင်းကတော့ `g0/0` interface ထဲမှာ လိုအပ်တဲ့ setting တွေကိုထည့်သွင်းတာဖြစ်ပါတယ်။

- `R1(config-if)#do show ip int brief`

  - **ရှင်းလင်းချက်**: ဒါက အလွန်အရေးကြီးတဲ့ command ပါ။ ပုံမှန်အားဖြင့် `show` command တွေကို Privileged Mode (`#`) မှာပဲသုံးလို့ရပါတယ်။ Config Mode (`config-if`) ထဲမှာ `show` command ကိုသုံးချင်ရင် ရှေ့မှာ **`do`** ဆိုတဲ့စကားလုံးကို ခံပြီးသုံးရပါတယ်။ ဒီ command က interface တွေရဲ့ IP address နဲ့ အခြေအနေကို အကျဉ်းချုံးကြည့်တာပါ။
  - **Output မှာ:** `administratively down` လို့ပြနေတာက အဲဒီ port ကို ပိတ်ထားတယ် (Default အနေနဲ့ ပိတ်ထားပါတယ်) လို့ပြတာပါ။

- `R1(config-if)#ip add`
- `R1(config-if)#ip address 172.16.255.254 255.255.0.0`

  - **ရှင်းလင်းချက်**: `ip address` command (`ip add` က အတိုကောက်) ကိုသုံးပြီး လက်ရှိရောက်နေတဲ့ `g0/0` interface ကို **IP Address (172.16.255.254)** နဲ့ **Subnet Mask (255.255.0.0)** သတ်မှတ်ပေးလိုက်တာပါ။

- `R1(config-if)#speed 1000`

  - **ရှင်းလင်းချက်**: Interface ရဲ့ data ပို့လွှတ်နှုန်းကို **1000 Mbps** (1 Gbps) ဖြစ်အောင် သတ်မှတ်လိုက်တာပါ။

- `R1(config-if)#duplex full`

  - **ရှင်းလင်းချက်**: Data ကို တစ်ပြိုင်တည်း ပို့နိုင်၊ လက်ခံနိုင်တဲ့ **Full-duplex** mode ကို သတ်မှတ်လိုက်တာပါ။

- `R1(config-if)#desc`
- `R1(config-if)#description ## to SW1 ##`

  - **ရှင်းလင်းချက်**: `description` (`desc` က အတိုကောက်) command က ဒီ interface ဘာအတွက်သုံးတယ်၊ ဘယ်ကိုချိတ်ထားတယ်ဆိုတာ မှတ်သားဖို့ စာတိုလေးရေးထားတာပါ။ Router ရဲ့အလုပ်လုပ်ပုံကို ဘာမှမသက်ရောက်ပေမယ့်၊ network administrator တွေအတွက် အလွန်အသုံးဝင်ပါတယ်။

- `R1(config-if)#no shut`
- `R1(config-if)#no shutdown`
  - **ရှင်းလင်းချက်**: ဒါက အရေးကြီးဆုံး command တစ်ခုပါ။ `no shutdown` (`no shut` က အတိုကောက်) ဆိုတာက အစောက `administratively down` ဖြစ်နေတဲ့ interface ကို **"ဖွင့်လိုက်တာ"** ဖြစ်ပါတယ်။ ဒီ command ရိုက်ပြီးမှ interface က အလုပ်လုပ်ပါတယ်။

---

### ၅။ Interface အခြေအနေပြောင်းလဲမှုကို စစ်ဆေးခြင်း

- `%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up`

  - **ရှင်းလင်းချက်**: ဒါက ကိုယ်ရိုက်လိုက်တဲ့ command မဟုတ်ပါဘူး။ Router ရဲ့ system ကနေ အလိုအလျောက် ပေါ်လာတဲ့ log message ပါ။ `no shutdown` command ကြောင့် `GigabitEthernet0/0` interface ရဲ့ အခြေအနေက **`up` (ပွင့်သွားပြီ)** ဆိုပြီး အသိပေးတာပါ။

- `R1(config-if)#do sh ip int br`
  - **ရှင်းလင်းချက်**: အပေါ်က `do show ip interface brief` command ကိုပဲ အတိုကောက် (`sh ip int br`) နဲ့ ပြန်စစ်ဆေးတာပါ။
  - **Output မှာ:** `GigabitEthernet0/0` မှာ IP address ဝင်သွားပြီး၊ **Status** က **`up`** ဖြစ်သွားတာကိုတွေ့ရပါမယ်။ ဒါပေမဲ့ **Protocol** က `down` ဖြစ်နေတုန်းပါပဲ။ ဒါက port ကတော့ ပွင့်သွားပြီ၊ ဒါပေမဲ့ network ကြိုးမထိုးရသေးလို့ (သို့) တစ်ဖက်က device က အလုပ်မလုပ်သေးလို့ data link အဆင့်မှာ ချိတ်ဆက်မှုမရသေးဘူးလို့ ဆိုလိုပါတယ်။

---

### ၆။ Interface Range ကို အသုံးပြုခြင်း

- `R1(config-if)#int rang g0/1 - 2`

  - **ရှင်းလင်းချက်**: ဒါက အချိန်ကုန်သက်သာစေတဲ့ command ပါ။ **`interface range`** (`int rang` က အတိုကောက်) ကိုသုံးပြီး interface တွေကို တစ်ခုချင်းစီဝင်ပြင်စရာမလိုဘဲ **အများကြီးကို တစ်ပြိုင်တည်း** ပြင်ဆင်နိုင်ပါတယ်။ ဒီ command က `GigabitEthernet0/1` နဲ့ `GigabitEthernet0/2` နှစ်ခုလုံးကို တစ်ခါတည်းရွေးပြီး config mode (`config-if-range`) ထဲဝင်လိုက်တာပါ။

- `R1(config-if-range)#des`
- `R1(config-if-range)#description ## not in use ##`
  - **ရှင်းလင်းချက်**: အခုရေးလိုက်တဲ့ `description` က `g0/1` ရော `g0/2` ရော **နှစ်ခုလုံးမှာ** တစ်ပြိုင်တည်း သွားပြီး သက်ရောက်မှာဖြစ်ပါတယ်။

## Lab

[Day_9_lab](https://drive.google.com/drive/folders/1scDYToyvKLsXuA-rXdOMhPHrLNQbG9z4?usp=drive_link)
