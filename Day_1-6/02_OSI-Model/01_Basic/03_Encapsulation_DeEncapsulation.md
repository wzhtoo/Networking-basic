# Encapsulation_DeEncapsulation

Encapsulation နဲ့ De-Encapsulation ဆိုတာ Networking Model (OSI or TCP/IP) ရဲ့ အရေးကြီးဆုံး သဘောတရားနှစ်ခုပဲ ဖြစ်ပါတယ်။ သူတို့ကို အလွယ်တကူ နားလည်အောင် အဆင့်ဆင့် ရှင်းပြပေးပါမယ်ခင်ဗျာ။

### **၁။ Encapsulation (အချက်အလက်များကို ထုပ်ပိုးခြင်း)**

**Encapsulation** ဆိုတာဟာ ကွန်ပျူတာတစ်ခုကနေ အချက်အလက် (Data) တွေကို ပို့ဆောင်တဲ့အခါ OSI Model ရဲ့ အပေါ်ဆုံးအလွှာ (Layer 7) ကနေ အောက်ဆုံးအလွှာ (Layer 1) ကို ဆင်းသွားရင်း တစ်လွှာချင်းစီမှာ Protocol Header (အချက်အလက်ခေါင်းစီး) တွေ ထပ်ထည့်ပြီး ထုပ်ပိုးသွားတဲ့ လုပ်ငန်းစဉ် (Process) ကို ပြောတာ ဖြစ်ပါတယ်။

**အဆင့်ဆင့် လုပ်ဆောင်ပုံ (Sender ဘက်)**

- **Layer 7 (Application Layer):** မူလ Data (ဥပမာ- "Hello World") ကို Application (Web Browser, Email) ကနေ ထုတ်လုပ်ပါတယ်။
- **Layer 4 (Transport Layer):**
  - Data ကို Segment (အပိုင်း) တွေအဖြစ် ခွဲပါတယ်။
  - **TCP Header** သို့မဟုတ် **UDP Header** ကို ထပ်ထည့်ပြီး ထုပ်ပိုးပါတယ်။ ဒီ Header ထဲမှာ Source/Destination Port နံပါတ်တွေ ပါဝင်ပါတယ်။ ဒီအဆင့်ကို **Segmentation** လို့ ခေါ်ပါတယ်။
- **Layer 3 (Network Layer):**
  - Segment တစ်ခုချင်းစီကို **IP Header** ထပ်ထည့်ပြီး Packet အဖြစ် ထုပ်ပိုးပါတယ်။
  - ဒီ IP Header ထဲမှာ Source IP Address နဲ့ Destination IP Address တွေ ပါဝင်ပါတယ်။ ဒီအဆင့်ကို **Packetization** လို့ ခေါ်ပါတယ်။
- **Layer 2 (Data Link Layer):**
  - Packet ကို **Ethernet Header** နဲ့ **Trailer** ထပ်ထည့်ပြီး Frame အဖြစ် ထုပ်ပိုးပါတယ်။
  - ဒီ Header ထဲမှာ Source MAC Address နဲ့ Destination MAC Address တွေ ပါဝင်ပါတယ်။ ဒီအဆင့်ကို **Framing** လို့ ခေါ်ပါတယ်။
- **Layer 1 (Physical Layer):**
  - Frame ကို Bit (0s and 1s) တွေအဖြစ် ပြောင်းလဲပြီး Network Cable (ကေဘယ်) ပေါ်ကနေ လျှပ်စစ်လှိုင်း သို့မဟုတ် အလင်းလှိုင်းအဖြစ် ပို့ဆောင်ပါတယ်။

**ဥပမာ:**
Data -> Header ထပ်ထည့် -> New Data -> Header ထပ်ထည့် -> New Data...
(Hello World) -> (TCP Header + Hello World) -> (IP Header + TCP Header + Hello World) -> (Ethernet Header + IP Header + TCP Header + Hello World + Ethernet Trailer)

### **၂။ De-Encapsulation (အချက်အလက်များကို ဖြည်ချခြင်း)**

**De-Encapsulation** ဆိုတာဟာ Receiver ဘက်က ကွန်ပျူတာတစ်ခုမှာ Encapsulation လုပ်ပြီးသား Data တွေကို Layer 1 ကနေ အပေါ် Layer 7 ကို တက်သွားရင်း တစ်လွှာချင်းစီမှာ ပါလာတဲ့ Protocol Header တွေကို ပြန်လည်ဖြည်ချ (ဖယ်ထုတ်) တဲ့ လုပ်ငန်းစဉ် ဖြစ်ပါတယ်။

**အဆင့်ဆင့် လုပ်ဆောင်ပုံ (Receiver ဘက်)**

- **Layer 1 (Physical Layer):** Network Cable ပေါ်ကနေ ရောက်ရှိလာတဲ့ Bit (0s and 1s) တွေကို လက်ခံရယူပါတယ်။
- **Layer 2 (Data Link Layer):**
  - Bits တွေကို ပြန်လည်စုစည်းပြီး Frame အဖြစ် ပြောင်းလဲပါတယ်။
  - Frame ရဲ့ Header ကို စစ်ဆေးပါတယ်။ Destination MAC Address က သူ့ရဲ့ Address နဲ့ ကိုက်ညီရင် Frame Header နဲ့ Trailer ကို ဖြုတ်ပြီး Packet ကို Layer 3 ကို လွှဲပေးပါတယ်။
- **Layer 3 (Network Layer):**
  - Packet ရဲ့ IP Header ကို စစ်ဆေးပါတယ်။ Destination IP Address က သူ့ရဲ့ Address နဲ့ ကိုက်ညီရင် IP Header ကို ဖြုတ်ပြီး Segment ကို Layer 4 ကို လွှဲပေးပါတယ်။
- **Layer 4 (Transport Layer):**
  - Segment ရဲ့ TCP Header ဒါမှမဟုတ် UDP Header ကို စစ်ဆေးပြီး ဘယ် Application ကို ပေးရမလဲဆိုတာ ဆုံးဖြတ်ပါတယ်။
  - Header ကို ဖြုတ်ပြီး Data ကို Layer 7 ကို လွှဲပေးပါတယ်။
- **Layer 7 (Application Layer):**
  - မူလ Data (ဥပမာ- "Hello World") ကို လက်ခံရရှိပြီး Application ကနေ ဖတ်ရှုအသုံးပြုနိုင်ပါပြီ။

### **Encapsulation နဲ့ De-Encapsulation ရဲ့ အရေးပါပုံ**

- **Modular Design:** Networking Model ရဲ့ အလွှာလိုက်ခွဲခြားထားတဲ့ ပုံစံကြောင့် Protocol တွေဟာ တစ်လွှာချင်းစီမှာ သူ့တာဝန်နဲ့သူ လုပ်ဆောင်နိုင်ပါတယ်။ တစ်လွှာရဲ့ပြောင်းလဲမှုက တခြားအလွှာတွေကို ထိခိုက်မှု မရှိပါဘူး။
- **Protocol Independence:** IP Address တွေက MAC Address တွေနဲ့ သီးခြားစီ အလုပ်လုပ်ပါတယ်။ Layer 2 မှာ Ethernet ကိုသုံးသည်ဖြစ်စေ၊ Wi-Fi ကိုသုံးသည်ဖြစ်စေ၊ Layer 3 က IP ကို ဆက်လက်အသုံးပြုနိုင်ပါတယ်။
- **Error Checking:** Header တစ်ခုချင်းစီမှာ ပါဝင်တဲ့ Checksum လို အချက်အလက်တွေက Data corrupted ဖြစ်မဖြစ်ကို စစ်ဆေးနိုင်ပါတယ်။
- **Routing Decision:** Router တွေဟာ Packet ရဲ့ Layer 3 Header (IP) ကို ဖတ်ပြီး ဘယ်လမ်းကြောင်းကို သွားရမလဲဆိုတာ ဆုံးဖြတ်နိုင်ပါတယ်။ Switch တွေဟာ Layer 2 Header (MAC) ကို ဖတ်ပြီး ဘယ် Port ကို ပို့ရမလဲဆိုတာ ဆုံးဖြတ်နိုင်ပါတယ်။

ဒီ Process နှစ်ခုကြောင့် Network ထဲမှာရှိတဲ့ Devices တွေဟာ Data တွေကို စနစ်တကျနဲ့ အမှားအယွင်းမရှိ ပို့ဆောင်နိုင်တာ ဖြစ်ပါတယ်ခင်ဗျာ။
