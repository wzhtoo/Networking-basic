# **Cisco CLI (Command-Line Interface)**

Cisco Network Devices (Router, Switch စသည်) တွေကို Configure လုပ်ဖို့၊ ထိန်းချုပ်ဖို့ နဲ့ ပြဿနာရှာဖွေဖို့အတွက် မရှိမဖြစ်လိုအပ်တဲ့ Tool တစ်ခုပဲ ဖြစ်ပါတယ်။

### **Cisco CLI ဆိုတာ ဘာလဲ။**

CLI ဆိုတာက Command-Line Interface ကို အတိုကောက်ခေါ်တာ ဖြစ်ပါတယ်။ Graphical User Interface (GUI) လိုမျိုး Mouse နဲ့ Click လုပ်ပြီး အလုပ်လုပ်တာမျိုးမဟုတ်ဘဲ **Keyboard ကနေ Command တွေကို စာသားနဲ့ ရိုက်ထည့်ပြီး အလုပ်လုပ်ရတဲ့ Interface** တစ်ခု ဖြစ်ပါတယ်။

Cisco CLI ကို အသုံးပြုပြီး Cisco IOS (Internetwork Operating System) ကို အဓိက အလုပ်လုပ်ကြပါတယ်။

### **Cisco CLI ကို ဘယ်လိုချိတ်ဆက်မလဲ။**

Cisco CLI ကို ချိတ်ဆက်ဖို့အတွက် နည်းလမ်းအမျိုးမျိုးရှိပါတယ်။

1.  **Console Connection:** Console Cable (RJ-45 to DB9) ကို အသုံးပြုပြီး ကွန်ပျူတာရဲ့ Console Port နဲ့ Router/Switch ရဲ့ Console Port ကို တိုက်ရိုက်ချိတ်ဆက်ခြင်း။ ဒါဟာ Device ကို စတင် Setup လုပ်တဲ့အခါ အသုံးအများဆုံး နည်းလမ်းပါ။
2.  **Telnet / SSH Connection:** Network နဲ့ ချိတ်ဆက်ပြီးသား Device တွေကို Remote ကနေ ချိတ်ဆက်ထိန်းချုပ်ခြင်း။ SSH (Secure Shell) က Telnet ထက်ပိုပြီး Secure ဖြစ်တဲ့အတွက် အခုခေတ်မှာ အများဆုံး အသုံးပြုကြပါတယ်။

### **Cisco CLI Modes (အခြေအနေများ)**

Cisco CLI မှာ Security နဲ့ Permissions (အခွင့်အရေး) ပေါ်မူတည်ပြီး အဓိက Modes ၄ ခု ရှိပါတယ်။

1.  **User EXEC Mode:**

    - **Prompt:** `Router>` သို့မဟုတ် `Switch>`
    - **Features:** Device ရဲ့ Basic Information (အခြေခံအချက်အလက်) တွေကို ကြည့်ရှုနိုင်ပါတယ်။ Configuration ကို ပြောင်းလဲခွင့် မရှိပါဘူး။
    - **Commands:** `enable`, `ping`, `show version`
    - **Exit Command:** `exit`

2.  **Privileged EXEC Mode:**

    - **Prompt:** `Router#` သို့မဟုတ် `Switch#`
    - **Features:** Device ရဲ့ Configuration ကို မပြောင်းလဲနိုင်ပေမယ့်၊ Debugging နဲ့ Troubleshooting အတွက် အသေးစိတ်အချက်အလက်တွေကို ကြည့်ရှုနိုင်ပါတယ်။
    - **Commands:** `configure terminal`, `show running-config`, `show ip interface brief`, `reload`
    - **Access Command:** `enable` command ကို User EXEC Mode ကနေ ရိုက်ပြီး ဝင်ရပါတယ်။
    - **Exit Command:** `exit` သို့မဟုတ် `disable`

3.  **Global Configuration Mode:**

    - **Prompt:** `Router(config)#` သို့မဟုတ် `Switch(config)#`
    - **Features:** Device တစ်ခုလုံးရဲ့ Global Configuration (ဥပမာ- Hostname ပြောင်းတာ၊ Interface တွေကို Enable လုပ်တာ) တွေကို ပြောင်းလဲနိုင်ပါတယ်။
    - **Access Command:** `configure terminal` command ကို Privileged EXEC Mode ကနေ ရိုက်ပြီး ဝင်ရပါတယ်။
    - **Exit Command:** `exit`

4.  **Interface Configuration Mode:**
    - **Prompt:** `Router(config-if)#` သို့မဟုတ် `Switch(config-if)#`
    - **Features:** Device ရဲ့ Interface (Port) တစ်ခုချင်းစီအတွက် Configuration (ဥပမာ- IP Address ပေးတာ၊ Speed ပြောင်းတာ) တွေကို ပြောင်းလဲနိုင်ပါတယ်။
    - **Access Command:** `interface gigabitethernet 0/0` စသဖြင့် Global Configuration Mode ကနေ ရိုက်ပြီး ဝင်ရပါတယ်။
    - **Exit Command:** `exit`

### **အသုံးများသော Commands များ**

- `show running-config`: လက်ရှိ Device မှာ အလုပ်လုပ်နေတဲ့ Configuration ကို ကြည့်ခြင်း။
- `show startup-config`: Reboot လုပ်ပြီးရင် ပြန်တက်လာမယ့် Configuration ကို ကြည့်ခြင်း။
- `copy running-config startup-config`: လက်ရှိ Configuration ကို Save လုပ်ခြင်း။
- `no shutdown`: Interface (Port) တစ်ခုကို On (အလုပ်လုပ်) စေခြင်း။
- `show ip interface brief`: Interface တွေရဲ့ Status နဲ့ IP Address တွေကို အကျဉ်းချုပ်ကြည့်ခြင်း။

### **အနှစ်ချုပ်**

**Cisco CLI** ဟာ Cisco Device တွေကို ထိန်းချုပ်တဲ့ **အဓိက ကိရိယာ** ဖြစ်ပါတယ်။ CLI ကို အသုံးပြုပြီး Devices တွေရဲ့ Configuration ကို စိတ်ကြိုက်ပြောင်းလဲနိုင်ခြင်း၊ Network ကို လိုအပ်သလို စီမံခန့်ခွဲနိုင်ခြင်းနဲ့ ပြဿနာတွေကို ထိရောက်စွာ ရှာဖွေဖြေရှင်းနိုင်ခြင်းစတဲ့ အကျိုးကျေးဇူးတွေ ရရှိနိုင်ပါတယ်ခင်ဗျာ။
