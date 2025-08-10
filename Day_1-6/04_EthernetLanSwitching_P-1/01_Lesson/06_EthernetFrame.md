## Ethernet Header, Packet, Ethernet Trailer

ဒီအကြောင်းအရာတွေဟာ OSI Model ရဲ့ **Layer 2 (Data Link Layer)** မှာရှိတဲ့ Encapsulation Process ကို အဓိကထား ရှင်းပြတာပဲ ဖြစ်ပါတယ်ခင်ဗျာ။

### **၁။ Ethernet Header (Eth Header)**

Ethernet Header ဟာ Frame ရဲ့ **ရှေ့ဆုံး (အစ)** မှာရှိပြီး၊ Frame ကို Local Network (LAN) အတွင်းမှာ ဘယ်လို ပို့ဆောင်ရမလဲဆိုတာကို သတ်မှတ်ပေးတဲ့ အချက်အလက်တွေ ပါဝင်ပါတယ်။

- **Preamble & Start of Frame Delimiter (SFD):** ဒါတွေကတော့ Data ကို အမှန်တကယ် မစတင်ခင် ရောက်လာမယ့် Data ရဲ့ အစကို Network Device တွေကို အသိပေးတဲ့ Signaling Bits တွေ ဖြစ်ပါတယ်။
- **Destination MAC Address:** Frame ကို လက်ခံမယ့် Device ရဲ့ **MAC Address (Physical Address)** ကို ထည့်သွင်းထားပါတယ်။ Switch ဟာ ဒီ MAC Address ကို အသုံးပြုပြီး Frame ကို သက်ဆိုင်ရာ Port ဆီကို တိုက်ရိုက်ပို့ဆောင်ပေးပါတယ်။
- **Source MAC Address:** Frame ကို ပို့ဆောင်လိုက်တဲ့ Device ရဲ့ **MAC Address** ကို ထည့်သွင်းထားပါတယ်။ Switch ဟာ ဒီ Address ကို အသုံးပြုပြီး ဘယ် MAC Address ဟာ ဘယ် Port မှာ ချိတ်ထားလဲဆိုတာကို လေ့လာမှတ်သား (Learning) ပါတယ်။
- **Type/Length:** ဒီ Field မှာ Frame အတွင်းမှာ ဘယ်လိုမျိုး Packet ပါလာတယ်ဆိုတာကို သတ်မှတ်ပေးပါတယ်။ ဥပမာ- `0x0800` ဆိုရင် IPv4 Packet ပါလာတယ်လို့ ဆိုလိုပြီး၊ `0x0806` ဆိုရင် ARP Packet ပါလာတယ်လို့ ဆိုလိုပါတယ်။ ဒါမှ Receiver က Packet ကို သက်ဆိုင်ရာ Upper Layer (ဥပမာ- Network Layer) ကို မှန်မှန်ကန်ကန် လွှဲပေးနိုင်မှာ ဖြစ်ပါတယ်။

### **၂။ Packet (Payload or Data)**

Packet ဟာ Ethernet Frame ရဲ့ **အလယ် (Payload)** အပိုင်းဖြစ်ပါတယ်။ ဒီနေရာမှာ Layer 3 (Network Layer) ကနေ Encapsulate လုပ်ပြီးသား Data တွေ ပါဝင်ပါတယ်။

- Ethernet Header ရဲ့ `Type/Length` Field မှာ ဖော်ပြထားတဲ့ Protocol အမျိုးအစား (ဥပမာ- IPv4) ပေါ်မူတည်ပြီး၊ Frame ဟာ ဒီ Packet ကို သက်ဆိုင်ရာ Upper Layer ကို ပို့ပေးမှာ ဖြစ်ပါတယ်။
- Packet ထဲမှာ Layer 3 Header (IP Header) နဲ့ Layer 4 Header (TCP Header) တွေလည်း ပါဝင်ပြီးသား ဖြစ်ပါတယ်။
- **Payload** အနေနဲ့ အနည်းဆုံး 46 Bytes ကနေ အများဆုံး 1500 Bytes အထိ ရှိနိုင်ပါတယ်။

### **၃။ Ethernet Trailer (Eth Trailer)**

Ethernet Trailer ဟာ Frame ရဲ့ **နောက်ဆုံး (အဆုံး)** မှာရှိပြီး၊ Data ကို ပို့ဆောင်နေစဉ်အတွင်း အမှားအယွင်းရှိ မရှိ စစ်ဆေးဖို့အတွက် အဓိက အသုံးပြုပါတယ်။

- **Frame Check Sequence (FCS):** Trailer ထဲမှာ အဓိကပါဝင်တဲ့ Field ဖြစ်ပါတယ်။
- `FCS` ဟာ Sender (ပို့သူ) က Frame ထဲက Data တွေကို **Cyclic Redundancy Check (CRC)** လိုမျိုး Algorithm တစ်ခုကို အသုံးပြုပြီး Hash (checksum) တစ်ခု တွက်ချက်လိုက်ပါတယ်။
- Receiver (လက်ခံသူ) ကလည်း ဒီ Frame ကို လက်ခံရရှိတဲ့အခါ CRC ကို ပြန်တွက်ချက်ပါတယ်။
- Sender နဲ့ Receiver က တွက်ထားတဲ့ တန်ဖိုးနှစ်ခု **တူညီတယ်ဆိုရင်** Frame ကို လက်ခံပြီး၊ **မတူညီဘူးဆိုရင်** Frame ဟာ ပျက်စီးသွားပြီလို့ ယူဆကာ ပယ်ချ (Discard) လိုက်ပါတယ်။

### **အနှစ်ချုပ်**

- **Ethernet Header:** Frame ရဲ့ အစမှာရှိပြီး **Source/Destination MAC Address** တို့လို လိပ်စာအချက်အလက်တွေ ပါဝင်ပါတယ်။
- **Packet (Payload):** Header နဲ့ Trailer ကြားမှာရှိပြီး Layer 3 နဲ့ Upper Layer Data တွေကို သယ်ဆောင်လာတဲ့နေရာ ဖြစ်ပါတယ်။
- **Ethernet Trailer:** Frame ရဲ့ အဆုံးမှာရှိပြီး **FCS** ကို အသုံးပြုကာ **Data Error (အမှားအယွင်း) ရှိ/မရှိ** စစ်ဆေးပေးပါတယ်။
