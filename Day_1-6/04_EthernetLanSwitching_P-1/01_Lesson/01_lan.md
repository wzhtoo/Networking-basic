# Ethernet LAN Switching

ယနေ့ခေတ် Network တွေရဲ့ အခြေခံအုတ်မြစ်တစ်ခုပဲ ဖြစ်ပါတယ်။

### **Ethernet LAN Switching ဆိုတာ ဘာလဲ။**

**Ethernet LAN Switching** ဆိုတာ Local Area Network (LAN) တစ်ခုအတွင်းမှာ Devices (Computer, Server, Printer စသည်) အချင်းချင်း အချက်အလက် (Data) တွေကို လျင်မြန်စွာနဲ့ ထိရောက်စွာ ပို့ဆောင်ပေးတဲ့ လုပ်ငန်းစဉ် (Process) ကို ပြောတာ ဖြစ်ပါတယ်။ ဒီလုပ်ငန်းစဉ်ရဲ့ အဓိက Device ကတော့ **Switch** ပဲ ဖြစ်ပါတယ်။

### **Switch တစ်ခုရဲ့ အဓိက လုပ်ဆောင်ချက်များ**

Switch တစ်ခုဟာ OSI Model ရဲ့ **Layer 2 (Data Link Layer)** မှာ အလုပ်လုပ်ပါတယ်။ သူဟာ **MAC Address** ကို အခြေခံပြီး Data Packet (Frame) တွေကို သက်ဆိုင်ရာ Destination ကို တိုက်ရိုက် ပို့ဆောင်ပေးပါတယ်။

Switch ရဲ့ အဓိက လုပ်ဆောင်ချက် ၃ ခု ရှိပါတယ်။

1.  **Learning (လေ့လာမှတ်သားခြင်း)**
2.  **Flooding (ဖြန့်ဝေခြင်း)**
3.  **Forwarding (ပို့ဆောင်ခြင်း)**

#### **1. Learning (လေ့လာမှတ်သားခြင်း)**

- Switch တစ်လုံး စတင်အလုပ်လုပ်တဲ့အခါ သူ့ရဲ့ **MAC Address Table (CAM Table)** ဟာ လုံးဝ ဗလာဖြစ်နေပါတယ်။
- Switch ရဲ့ Port တစ်ခုခုကို Device တစ်ခုကနေ Frame တစ်ခု ပို့လိုက်တဲ့အခါ၊ Switch ဟာ Frame ရဲ့ Source MAC Address ကို ဖတ်ပြီး ဘယ် MAC Address ဟာ ဘယ် Port မှာ ချိတ်ထားလဲဆိုတာကို မှတ်သားပါတယ်။
- ဥပမာ- Computer A က Frame ပို့လိုက်ရင် Switch က **"Computer A ရဲ့ MAC Address က Port 1 မှာ ရှိတယ်"** ဆိုပြီး သူ့ရဲ့ Table ထဲမှာ မှတ်ထားလိုက်ပါတယ်။

#### **2. Flooding (ဖြန့်ဝေခြင်း)**

- Switch ကနေ Frame တစ်ခု လက်ခံရရှိတဲ့အခါ Frame ရဲ့ **Destination MAC Address** ကို စစ်ဆေးပါတယ်။
- အကယ်၍ အဲဒီ Destination MAC Address ကို Switch ရဲ့ MAC Address Table ထဲမှာ **ရှာမတွေ့သေးဘူးဆိုရင်**၊ Switch ဟာ **Frame ကို Port အားလုံး (Source Port မှလွဲ၍)** ကို ဖြန့်ဝေ (Flood) လိုက်ပါတယ်။
- ဒါမှ Destination ရဲ့ MAC Address ကို နောက်တစ်ကြိမ် ပြန်လည် Learning လုပ်နိုင်ဖို့အတွက် အခွင့်အရေး ရစေပါတယ်။

#### **3. Forwarding (ပို့ဆောင်ခြင်း)**

- Switch ကနေ Frame တစ်ခု လက်ခံရရှိတဲ့အခါ Frame ရဲ့ **Destination MAC Address** ကို စစ်ဆေးပါတယ်။
- အကယ်၍ အဲဒီ Destination MAC Address ကို Switch ရဲ့ MAC Address Table ထဲမှာ **ရှာတွေ့ပြီဆိုရင်**၊ Switch ဟာ Frame ကို သက်ဆိုင်ရာ **Destination Port တစ်ခုတည်းကိုသာ** တိုက်ရိုက် ပို့ဆောင်ပေးပါတယ်။
- ဒါဟာ Ethernet Switching ရဲ့ အဓိကအားသာချက်ဖြစ်ပါတယ်။ Hub လိုမျိုး Port အားလုံးကို မပို့တော့ဘဲ၊ သက်ဆိုင်ရာ Port ကိုပဲ တိုက်ရိုက်ပို့တာကြောင့် **Network Traffic ကို လျှော့ချနိုင်ပြီး Security ကိုလည်း ပိုမိုကောင်းမွန်စေပါတယ်**။

### **Ethernet LAN Switching ရဲ့ အကျိုးကျေးဇူးများ**

1.  **Increased Bandwidth & Performance:** Switch ဟာ Traffic တွေကို သက်ဆိုင်ရာနေရာကိုပဲ ပို့ဆောင်ပေးတာကြောင့် **Collision Domain** ကို သေးငယ်စေပြီး Network Performance ကို မြင့်တက်စေပါတယ်။
2.  **Security:** မလိုအပ်တဲ့ Traffic တွေကို တခြား Ports တွေဆီ မပို့ဆောင်တော့တဲ့အတွက် Network Traffic ကို အလွယ်တကူ Sniffing (ခိုးနားထောင်) လုပ်ဖို့ ခက်ခဲစေပါတယ်။
3.  **Scalability:** Network ကို ချဲ့ထွင်တဲ့အခါ Switches တွေ အသုံးပြုပြီး Devices ပိုမိုထည့်သွင်းနိုင်ပါတယ်။

### **အနှစ်ချုပ်:**

**Ethernet LAN Switching** ဆိုတာ Switch တွေက **MAC Address** ကို အခြေခံပြီး Network Devices တွေကြားမှာ Data Frame တွေကို စနစ်တကျ၊ ထိရောက်စွာနဲ့ လုံခြုံမှုရှိရှိ ပို့ဆောင်ပေးတဲ့ လုပ်ငန်းစဉ်တစ်ခု ဖြစ်ပါတယ်။ ဒါကြောင့် Switch တွေဟာ ယနေ့ခေတ် LAN Network တွေအတွက် မရှိမဖြစ်လိုအပ်တဲ့ စက်ပစ္စည်းတစ်ခုအဖြစ် ရပ်တည်နေတာ ဖြစ်ပါတယ်ခင်ဗျာ။
