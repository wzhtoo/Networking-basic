# Network Devices Data Transfer

Network Devices တွေ Data Transfer လုပ်တဲ့အခါမှာ သက်ဆိုင်ရာ Characteristics (ဝိသေသလက္ခဏာများ) တွေအကြောင်းကို အသေးစိတ် ရှင်းပြပေးပါမယ်။

ဒီ Characteristics တွေဟာ Physical Layer (Layer 1) ရဲ့ အဓိက အစိတ်အပိုင်းတွေဖြစ်ပြီး၊ Network ရဲ့ မြန်နှုန်း၊ အကွာအဝေးနဲ့ ယုံကြည်စိတ်ချရမှုတို့ကို သတ်မှတ်ပေးပါတယ်။ အများဆုံးအသုံးပြုတဲ့ Ethernet Standard တွေကို ဥပမာပေးပြီး ရှင်းပြပေးပါမယ်။

### **1. 10BASE-T Ethernet (10 Mbps)**

ဒါဟာ အစောဆုံး Ethernet Standard တွေထဲက တစ်ခုဖြစ်ပြီး အခုခေတ်မှာတော့ အသုံးပြုမှု နည်းပါးသွားပါပြီ။

- **Voltage Levels:** Manchester Encoding ကိုအသုံးပြုပါတယ်။ Bit 0 နဲ့ 1 ကို Voltage Level တွေအပြောင်းအလဲနဲ့ ဖော်ပြပါတယ်။ (ဥပမာ- 0 ကို အမြင့်ကနေ အနိမ့်၊ 1 ကို အနိမ့်ကနေ အမြင့်ပြောင်းခြင်း)။
- **Maximum Transmission Distance:** အများဆုံး **100 မီတာ (328 ပေ)** အထိ အလုပ်လုပ်နိုင်ပါတယ်။
- **Physical Connectors:** RJ-45 Connector ကို အသုံးပြုပါတယ်။
- **Cable Specifications:** Category 3 (Cat3) သို့မဟုတ် ပိုကောင်းတဲ့ UTP (Unshielded Twisted-Pair) Cable ကို အသုံးပြုပါတယ်။
- **Other Characteristics:**
  - **Wires Used:** Data ပို့ဆောင်ဖို့အတွက် ကြိုးအတွဲ ၂ ခု (Pin 1, 2 for Transmit / Pin 3, 6 for Receive) ကိုပဲ အသုံးပြုပါတယ်။
  - **Duplex Mode:** Half-duplex နဲ့ Full-duplex နှစ်မျိုးလုံးကို အထောက်အပံ့ပေးပါတယ်။

### **2. 100BASE-TX Ethernet (100 Mbps)**

ဒါကို **Fast Ethernet** လို့လည်း ခေါ်ပြီး ယနေ့အသုံးပြုနေတဲ့ Network များစွာရဲ့ အခြေခံဖြစ်ပါတယ်။

- **Voltage Levels:** MLT-3 (Multi-Level Transmit 3) Encoding ကို အသုံးပြုပါတယ်။ ဒီနည်းလမ်းက Voltage Level ၃ ခု (+1, 0, -1) ကို အသုံးပြုပြီး Data ပိုမြန်မြန်ပို့နိုင်အောင် လုပ်ဆောင်ပေးပါတယ်။
- **Maximum Transmission Distance:** အများဆုံး **100 မီတာ (328 ပေ)** အထိသာ အလုပ်လုပ်နိုင်ပါတယ်။
- **Physical Connectors:** RJ-45 Connector ကို အသုံးပြုပါတယ်။
- **Cable Specifications:** Category 5 (Cat5) သို့မဟုတ် ပိုကောင်းတဲ့ UTP Cable ကို အသုံးပြုရပါမယ်။
- **Other Characteristics:**
  - **Wires Used:** Data ပို့ဆောင်ဖို့အတွက် ကြိုးအတွဲ ၂ ခု (Pin 1, 2 for Transmit / Pin 3, 6 for Receive) ကိုပဲ အသုံးပြုပါတယ်။
  - **Duplex Mode:** Full-duplex ကို အဓိက အထောက်အပံ့ပေးပါတယ်။

### **3. 1000BASE-T Ethernet (1 Gbps)**

ဒါကို **Gigabit Ethernet** လို့လည်း ခေါ်ပြီး ယနေ့ခေတ် Networks တွေရဲ့ Standard Speed ဖြစ်ပါတယ်။

- **Voltage Levels:** PAM-5 (Pulse Amplitude Modulation 5-level) Encoding ကို အသုံးပြုပါတယ်။ ဒီနည်းလမ်းက Voltage Level ၅ ခုကို အသုံးပြုပြီး တစ်ချိန်တည်းမှာ Data ကို အမြောက်အများ ပို့ဆောင်နိုင်ပါတယ်။
- **Maximum Transmission Distance:** အများဆုံး **100 မီတာ (328 ပေ)** အထိသာ အလုပ်လုပ်နိုင်ပါတယ်။
- **Physical Connectors:** RJ-45 Connector ကို အသုံးပြုပါတယ်။
- **Cable Specifications:** Category 5e (Cat5e) သို့မဟုတ် ပိုကောင်းတဲ့ UTP Cable ကို အသုံးပြုရပါမယ်။ Cat5e က Cat5 ထက် crosstalk (အချက်ပြမှုနှောင့်ယှက်မှု) ကို ပိုမိုကာကွယ်ပေးနိုင်ပါတယ်။
- **Other Characteristics:**
  - **Wires Used:** Data ပို့ဆောင်ဖို့အတွက် **ကြိုး ၄ တွဲလုံး (Pin 8 ပင်လုံး)** ကို တစ်ချိန်တည်း Transmit နဲ့ Receive လုပ်ဖို့ အသုံးပြုပါတယ်။
  - **Duplex Mode:** အမြဲတမ်း **Full-duplex** Mode နဲ့ပဲ အလုပ်လုပ်ပါတယ်။

### **4. Fiber Optic Cable (Optical Signals)**

Fiber Cable တွေကတော့ Electrical Signal (လျှပ်စစ်) နဲ့မပို့ဘဲ Optical Signal (အလင်း) နဲ့ ပို့ဆောင်တာဖြစ်ပါတယ်။

- **Voltage Levels:** အသုံးပြုခြင်းမရှိပါဘူး။ **အလင်းထုတ်လွှတ်တဲ့ Laser or LED** နဲ့ **အလင်းရောင်လက်ခံတဲ့ Photodiode** ကို အသုံးပြုပါတယ်။
- **Maximum Transmission Distance:**
  - **Multi-mode Fiber:** Short-distance အတွက်သုံးပြီး **300m - 550m** အထိ အလုပ်လုပ်နိုင်ပါတယ်။
  - **Single-mode Fiber:** Long-distance အတွက်သုံးပြီး **10 km, 40 km** သို့မဟုတ် ပိုဝေးတဲ့ အကွာအဝေးကို ပို့ဆောင်နိုင်ပါတယ်။
- **Physical Connectors:** LC, SC, ST Connector အမျိုးအစားများကို အသုံးပြုပါတယ်။
- **Cable Specifications:** အလင်းဖြတ်သန်းတဲ့ Core ရဲ့ အရွယ်အစားပေါ်မူတည်ပြီး Single-mode (9 microns) နဲ့ Multi-mode (50/62.5 microns) အဖြစ် ခွဲခြားပါတယ်။

**အနှစ်ချုပ်အနေဖြင့်:**

Device တွေရဲ့ Data Transfer Characteristics တွေဟာ Network Standards ပေါ်မူတည်ပြီး **Voltage Levels (လျှပ်စစ်လှိုင်း)၊ Maximum Distances (အကွာအဝေး) နဲ့ Cable Specifications (ကြိုးအမျိုးအစား)** တို့ ကွဲပြားပါတယ်။ ဒီလို သတ်မှတ်ချက်တွေဟာ Network ရဲ့ Performance ကို တိုက်ရိုက်သက်ရောက်မှုရှိတာကြောင့် နည်းပညာတွေတိုးတက်လာတာနဲ့အမျှ ပိုမိုကောင်းမွန်တဲ့ Standards တွေ ပေါ်ပေါက်လာတာ ဖြစ်ပါတယ်ခင်ဗျာ။
