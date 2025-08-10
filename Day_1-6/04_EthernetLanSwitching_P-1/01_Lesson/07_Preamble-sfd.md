## Premeable and Sfd

Ethernet Frame ရဲ့ Preamble နဲ့ SFD (Start of Frame Delimiter) အကြောင်းကို ရှင်းပြပေးပါမယ်။ ဒီနှစ်ခုလုံးဟာ Data Frame ကို အမှန်တကယ် မပို့ခင် Network Devices တွေကြားမှာ Synchronization (အချိန်ကိုက်ညီမှု) ရရှိစေဖို့အတွက် အသုံးပြုတဲ့ အရေးကြီးတဲ့ အစိတ်အပိုင်းတွေ ဖြစ်ပါတယ်။

### **1. Preamble (56 bits)**

- **Preamble ဆိုတာ ဘာလဲ:** Preamble ဟာ **Alternating Pattern (တစ်လှည့်စီပြောင်းလဲနေတဲ့ ပုံစံ)** ဖြစ်တဲ့ `10101010...` ဆိုတဲ့ Digital Bits (0s and 1s) ပေါင်း 56 ခု ပါဝင်ပါတယ်။
- **လုပ်ဆောင်ချက်:** Preamble ရဲ့ အဓိက လုပ်ဆောင်ချက်ကတော့ **Receiver (data လက်ခံမယ့်သူ) ကို Ready ဖြစ်စေဖို့** ဖြစ်ပါတယ်။ Network Cable ကြိုးပေါ်မှာ Data (လျှပ်စစ်လှိုင်း) တွေ ပို့တဲ့အခါ Clock Signal (အချိန်နာရီ) မပါဝင်ပါဘူး။ ဒါကြောင့် Receiver ဘက်က Data ရဲ့အစကို သိရှိပြီး Synchronize လုပ်နိုင်ဖို့အတွက် Preamble ကို အရင်ဆုံး ပို့ပေးတာဖြစ်ပါတယ်။
- **Preamble ကို ဘာလို့ 56 bits တောင် သုံးရတာလဲ:**
  - Network ကြိုးတွေမှာ Latency (နှောင့်နှေးမှု) တွေရှိနိုင်ပါတယ်။ Sender က ပို့တဲ့ Signal ဟာ Receiver ကိုရောက်ဖို့ အချိန်အနည်းငယ် ကြာပါတယ်။
  - ဒီ 56 bits ဟာ Latency ကိုကျော်လွှားပြီး Receiver ရဲ့ Clock ကို Sender ရဲ့ Clock နဲ့ အချိန်ကိုက်ညီသွားစေဖို့ (synchronize) အတွက် အချိန်ပေးလိုက်တာ ဖြစ်ပါတယ်။
  - ဒါမှ Receiver ဟာ နောက်ဆက်တွဲလာမယ့် Data Bits တွေကို အမှန်အကန် ဖတ်နိုင်မှာ ဖြစ်ပါတယ်။

### **2. SFD (Start of Frame Delimiter) (8 bits)**

- **SFD ဆိုတာ ဘာလဲ:** SFD ဟာ Preamble ပြီးတာနဲ့ ချက်ချင်းလိုက်ပါလာပြီး `10101011` ဆိုတဲ့ **8 bits** Pattern တစ်ခု ဖြစ်ပါတယ်။
- **လုပ်ဆောင်ချက်:**
  - Preamble က Synchronization အတွက်ပဲ ဖြစ်ပြီး၊ SFD ကတော့ **Data Frame ရဲ့ အစကို အတိအကျ သတ်မှတ်ပေးတဲ့အမှတ်အသား** ဖြစ်ပါတယ်။
  - Preamble က `101010...` နဲ့ ပြီးပြီးချင်း SFD ရဲ့ နောက်ဆုံး `11` ပုံစံကို တွေ့လိုက်တာနဲ့ Receiver ဟာ **"အခုမှသာ Data Frame အမှန်တကယ် စပြီ"** ဆိုတာကို သိရှိသွားပါတယ်။
  - ဒါကြောင့် Receiver ဟာ SFD ပြီးတာနဲ့ ချက်ချင်းလိုက်ပါလာမယ့် Destination MAC Address ကို ဖတ်ဖို့ အသင့်ဖြစ်သွားပါတယ်။

### **အနှစ်ချုပ်:**

- **Preamble (56 bits):** **`Synchronization`** အတွက်ဖြစ်ပြီး၊ Receiver ကို Data လက်ခံဖို့ အဆင်သင့်ဖြစ်အောင် ပြင်ဆင်ပေးပါတယ်။
- **SFD (8 bits):** **`Start of Frame`** အတွက်ဖြစ်ပြီး၊ Preamble ပြီးဆုံးကာ Frame ရဲ့အစကို အတိအကျ သတ်မှတ်ပေးပါတယ်။

ဒီနှစ်ခုပေါင်းပြီးတော့ **8 Bytes (64 bits)** ဟာ Data Frame ရဲ့ရှေ့ဆုံးမှာ အမြဲတမ်း ပါဝင်ပြီး Network Devices တွေကြားမှာ ယုံကြည်စိတ်ချရတဲ့ ဆက်သွယ်မှုကို ထိန်းသိမ်းပေးပါတယ်ခင်ဗျာ။

## Desinitation & Source

ဟုတ်ကဲ့ခင်ဗျာ။ Network ပညာရပ်မှာ အခြေခံအကျဆုံး အရေးကြီးတဲ့ Concepts နှစ်ခုဖြစ်တဲ့ **Destination** နဲ့ **Source** တို့အကြောင်းကို ရှင်းပြပေးပါမယ်။

### **Source (မူလအစ)**

- **Source** ဆိုတာကတော့ **အချက်အလက် (Data) တွေကို စတင်ပို့ဆောင်လိုက်တဲ့ နေရာ၊ ဒါမှမဟုတ် စက်ပစ္စည်း** ကို ပြောတာဖြစ်ပါတယ်။
- Network မှာဆိုရင် Data ကို စတင်ထုတ်လွှတ်လိုက်တဲ့ Computer၊ Server၊ ဒါမှမဟုတ် Mobile Device စတာတွေဟာ **Source** ဖြစ်ပါတယ်။
- **Source Address:** Data Packet တွေမှာ **`Source IP Address`** နဲ့ **`Source MAC Address`** ဆိုပြီး မူလအစရဲ့ လိပ်စာတွေ ပါဝင်ပါတယ်။ ဒီလိပ်စာတွေဟာ Data ကို လက်ခံရရှိတဲ့ Receiver ဘက်ကနေ Sender ကို ပြန်လည် ဆက်သွယ်နိုင်ဖို့အတွက် အလွန်အရေးကြီးပါတယ်။

### **Destination (ဦးတည်ရာ)**

- **Destination** ဆိုတာကတော့ **အချက်အလက် (Data) တွေ သွားရောက်ရမယ့် နေရာ၊ ဒါမှမဟုတ် လက်ခံမယ့် စက်ပစ္စည်း** ကို ပြောတာဖြစ်ပါတယ်။
- Network မှာဆိုရင် Data ကို လက်ခံမယ့် Computer၊ Server၊ ဒါမှမဟုတ် Mobile Device စတာတွေဟာ **Destination** ဖြစ်ပါတယ်။
- **Destination Address:** Data Packet တွေမှာ **`Destination IP Address`** နဲ့ **`Destination MAC Address`** ဆိုပြီး ဦးတည်ရာရဲ့ လိပ်စာတွေ ပါဝင်ပါတယ်။ ဒီလိပ်စာတွေပေါ်မူတည်ပြီး Router နဲ့ Switch တွေက Data တွေကို လမ်းကြောင်းရှာ ပို့ဆောင်ပေးတာ ဖြစ်ပါတယ်။

### **ဥပမာ ရှင်းလင်းချက်**

အင်တာနက်ပေါ်မှာ Email တစ်စောင် ပို့တယ်ဆိုပါစို့။

- **Source:** Email ကို စတင်ရေးသားပြီး ပို့လိုက်တဲ့ **သင့်ရဲ့ကွန်ပျူတာ** ဟာ **Source** ဖြစ်ပါတယ်။ သင့်ရဲ့ PC မှာ `Source IP` နဲ့ `Source MAC` တွေ ပါရှိပါတယ်။
- **Destination:** Email ကို လက်ခံရရှိမယ့် **သင့်သူငယ်ချင်းရဲ့ ကွန်ပျူတာ** ဟာ **Destination** ဖြစ်ပါတယ်။ သင့်သူငယ်ချင်းရဲ့ PC မှာ `Destination IP` နဲ့ `Destination MAC` တွေ ပါရှိပါတယ်။

Switch နဲ့ Router တွေဟာ ဒီ `Source` နဲ့ `Destination` လိပ်စာတွေကို အသုံးပြုပြီး Data ကို မှန်ကန်စွာ ပို့ဆောင်ပေးတာ ဖြစ်ပါတယ်။

- **Switch:** Ethernet Frame ရဲ့ `Destination MAC Address` ကို ကြည့်ပြီး LAN အတွင်းမှာ Data ကို ပို့ဆောင်ပေးပါတယ်။
- **Router:** IP Packet ရဲ့ `Destination IP Address` ကို ကြည့်ပြီး Networks တွေကြားမှာ Data ကို လမ်းကြောင်းရှာ ပို့ဆောင်ပေးပါတယ်။

ဒါကြောင့် `Source` နဲ့ `Destination` ဟာ Data Transfer Process အတွက် မရှိမဖြစ်လိုအပ်တဲ့ အခြေခံသဘောတရားတွေပဲ ဖြစ်ပါတယ်ခင်ဗျာ။

## Type or Length

Ethernet Frame ရဲ့ **Type or Length** field အကြောင်းကို ရှင်းပြပေးပါမယ်။ ဒီ field ဟာ Layer 2 နဲ့ Layer 3 ကြားမှာ Data တွေကို စနစ်တကျ လွှဲပြောင်းပေးဖို့အတွက် အလွန်အရေးကြီးတဲ့ အခန်းကဏ္ဍကနေ ပါဝင်ပါတယ်။

### **Type or Length Field ဆိုတာ ဘာလဲ။**

`Type` or `Length` field ဟာ Ethernet Header ရဲ့ တစ်စိတ်တစ်ပိုင်းဖြစ်ပြီး **2 Bytes (16 bits)** ရှိပါတယ်။ ဒီ field ရဲ့ အဓိပ္ပါယ်ဟာ ဘယ်လို Ethernet Standard ကိုသုံးလဲဆိုတဲ့အပေါ်မှာ မူတည်ပြီး ကွဲပြားပါတယ်။

- **Ethernet II (Diablo) Standard မှာ Type Field:**

  - လက်ရှိအသုံးအများဆုံး Standard ဖြစ်တဲ့ Ethernet II မှာ ဒီ field ကို `Type` field အဖြစ် အသုံးပြုပါတယ်။
  - `Type` field ရဲ့ တန်ဖိုးဟာ **`0x0600` (1536) ထက် ကြီးတယ်**ဆိုရင် ဒါဟာ `Type` field ဖြစ်တယ်လို့ သတ်မှတ်ပါတယ်။
  - **လုပ်ဆောင်ချက်:** ဒီ `Type` field ထဲမှာ Frame ရဲ့ Payload (Data) အပိုင်းမှာ ဘယ်လို Protocol အမျိုးအစား ပါလာလဲဆိုတာကို သတ်မှတ်ပေးပါတယ်။
  - ဥပမာ-
    - `0x0800` ဆိုရင် Payload ထဲမှာ **IPv4 Packet** ပါလာတယ်လို့ ဆိုလိုပါတယ်။
    - `0x0806` ဆိုရင် Payload ထဲမှာ **ARP Packet** ပါလာတယ်လို့ ဆိုလိုပါတယ်။
    - `0x86DD` ဆိုရင် Payload ထဲမှာ **IPv6 Packet** ပါလာတယ်လို့ ဆိုလိုပါတယ်။
  - **အရေးပါပုံ:** Receiver (လက်ခံသူ) ဘက်က Data Frame တစ်ခုကို လက်ခံရရှိတဲ့အခါ `Type` field ကိုဖတ်လိုက်တာနဲ့ Payload ထဲက Packet ကို ဘယ် Upper Layer Protocol ကို လွှဲပေးရမလဲဆိုတာကို သိရှိနိုင်ပါတယ်။ (ဥပမာ- `0x0800` ဆိုရင် Network Layer မှာရှိတဲ့ IP Process ကို လွှဲပေးတာမျိုး ဖြစ်ပါတယ်။)

- **IEEE 802.3 Standard မှာ Length Field:**
  - အစောပိုင်း Standard ဖြစ်တဲ့ IEEE 802.3 မှာ ဒီ field ကို `Length` field အဖြစ် အသုံးပြုပါတယ်။
  - `Length` field ရဲ့ တန်ဖိုးဟာ **`0x0600` (1536) ထက် ငယ်တယ်**ဆိုရင် ဒါဟာ `Length` field ဖြစ်တယ်လို့ သတ်မှတ်ပါတယ်။
  - **လုပ်ဆောင်ချက်:** ဒီ field ထဲမှာ Payload ရဲ့ Size ကို Bytes နဲ့ ဖော်ပြပါတယ်။

### **အနှစ်ချုပ်**

`Type or Length` field ရဲ့ အဓိကတာဝန်ကတော့ Ethernet Frame တစ်ခုရဲ့ **`Payload` (Data)** အပိုင်းမှာ ဘယ်လို Protocol အမျိုးအစား ပါဝင်လဲဆိုတာကို သတ်မှတ်ပေးဖို့ပဲ ဖြစ်ပါတယ်။

- **Type Field (Ethernet II):** Payload ထဲက **Protocol အမျိုးအစား (ဥပမာ- IPv4, IPv6, ARP)** ကို ပြောပြပါတယ်။ ဒီကနေ့ခေတ် Network တွေမှာ အများဆုံးသုံးပါတယ်။
- **Length Field (IEEE 802.3):** Payload ရဲ့ **အရွယ်အစား (Size)** ကို ပြောပြပါတယ်။

ဒီ field ကြောင့်သာ Data Link Layer ဟာ သူ့ရဲ့အလုပ်ပြီးဆုံးတဲ့အခါ Data Packet ကို သက်ဆိုင်ရာ Network Layer Protocol ဆီကို မှန်မှန်ကန်ကန် လွှဲပေးနိုင်တာ ဖြစ်ပါတယ်ခင်ဗျာ။

<img src="ethernet_frame.png" width="350">

```
Preamble = 7
SFD = 1
Sestination = 6
Source = 6
Type = 2
```

Ethernet Frame ရဲ့ အစိတ်အပိုင်းတွေကို သင်ပြောပြတဲ့ Bytes အရေအတွက် (7, 1, 6, 6, 2) အတိုင်း အသေးစိတ် ရှင်းပြပေးပါမယ်။

ဒီဂဏန်းတွေဟာ Frame တစ်ခုချင်းစီရဲ့ Field အရွယ်အစား (Byte size) ကို ကိုယ်စားပြုတာ ဖြစ်ပါတယ်ခင်ဗျာ။

### **၁။ Preamble (7 Bytes)**

- **Bytes အရေအတွက်:** 7 Bytes = 56 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** Preamble ဟာ Frame တစ်ခုရဲ့ အစမှာရှိပြီး `10101010...` ဆိုတဲ့ Bit Pattern တွေနဲ့ ဖွဲ့စည်းထားပါတယ်။ ဒါဟာ Data အမှန်တကယ်မရောက်ခင်မှာ **လက်ခံသူ (Receiver)** ရဲ့ Clock (အချိန်နာရီ) နဲ့ **ပို့သူ (Sender)** ရဲ့ Clock တို့ကို **အချိန်ကိုက်ညီစေဖို့ (Synchronization)** အတွက် အသုံးပြုပါတယ်။ ဒီလို Synchronization လုပ်ပြီးမှ Data Bits တွေကို မှန်မှန်ကန်ကန် စတင်ဖတ်ရှုနိုင်မှာ ဖြစ်ပါတယ်။

### **၂။ SFD (Start of Frame Delimiter) (1 Byte)**

- **Bytes အရေအတွက်:** 1 Byte = 8 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** Preamble ပြီးတာနဲ့ ချက်ချင်းလိုက်ပါလာပြီး `10101011` ဆိုတဲ့ Bit Pattern နဲ့ ဖွဲ့စည်းထားပါတယ်။ SFD ဟာ **Frame ရဲ့အစကို အတိအကျ သတ်မှတ်ပေးတဲ့အမှတ်အသား** ဖြစ်ပါတယ်။ Receiver ဟာ SFD ရဲ့ ဒီ Pattern ကိုတွေ့လိုက်တာနဲ့ Preamble ပြီးဆုံးပြီး Data Frame စတင်ပြီဆိုတာကို သိရှိနိုင်ပါတယ်။

### **၃။ Destination (6 Bytes)**

- **Bytes အရေအတွက်:** 6 Bytes = 48 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** ဒီ Field ထဲမှာ Frame ကိုလက်ခံမယ့် **Destination Device ရဲ့ MAC Address** ကို ထည့်သွင်းထားပါတယ်။ Switch က ဒီ MAC Address ကိုကြည့်ပြီး Frame ကို သက်ဆိုင်ရာ Device ဆီကို တိုက်ရိုက်ပို့ဆောင်ပေးပါတယ်။

### **၄။ Source (6 Bytes)**

- **Bytes အရေအတွက်:** 6 Bytes = 48 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** ဒီ Field ထဲမှာ Frame ကိုပို့လိုက်တဲ့ **Source Device ရဲ့ MAC Address** ကို ထည့်သွင်းထားပါတယ်။ Switch က ဒီ Address ကို အသုံးပြုပြီး ဘယ် Device ဟာ ဘယ် Port မှာ ချိတ်ထားလဲဆိုတာကို လေ့လာမှတ်သားပါတယ်။

### **၅။ Type (or Length) (2 Bytes)**

- **Bytes အရေအတွက်:** 2 Bytes = 16 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** ဒီ Field က Frame ရဲ့ Payload (Packet) ထဲမှာ ဘယ်လို **Protocol အမျိုးအစား** ပါလာလဲဆိုတာကို ဖော်ပြပေးပါတယ်။ ဥပမာ- `0x0800` ဆိုရင် IPv4 Packet လို့ဆိုလိုပြီး `0x0806` ဆိုရင် ARP Packet လို့ဆိုလိုပါတယ်။

### **Frame Check Sequence (FCS) (4 Bytes)**

- **Bytes အရေအတွက်:** 4 Bytes = 32 bits ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** ပုံမှာ Eth Trailer အောက်မှာပါတဲ့ FCS ဟာ Data ကို ပို့ဆောင်နေစဉ်အတွင်း အမှားအယွင်းရှိ မရှိ စစ်ဆေးဖို့အတွက် အသုံးပြုပါတယ်။ Sender နဲ့ Receiver က ဒီတန်ဖိုးကို တွက်ချက်ပြီး တူညီမှသာ Frame ကို လက်ခံပါတယ်။

Ethernet Frame ရဲ့ Trailer မှာပါတဲ့ **FCS (Frame Check Sequence)** နဲ့ **CRC (Cyclic Redundancy Check)** တို့ရဲ့ ဆက်စပ်မှုကို ရှင်းပြပေးပါမယ်။

### **FCS နဲ့ CRC ရဲ့ ဆက်စပ်မှု**

- **FCS ဆိုတာ:** FCS ဆိုတာကတော့ **Frame Check Sequence** ရဲ့ အတိုကောက်ဖြစ်ပြီး Ethernet Trailer မှာပါဝင်တဲ့ **4 Bytes (32 bits)** အရွယ်အစားရှိတဲ့ Field တစ်ခုဖြစ်ပါတယ်။
- **CRC ဆိုတာ:** CRC ဆိုတာကတော့ **Cyclic Redundancy Check** ရဲ့ အတိုကောက်ဖြစ်ပြီး၊ ဒါဟာ Data ထဲမှာ **Error (အမှားအယွင်း)** ရှိ/မရှိ စစ်ဆေးဖို့အတွက် အသုံးပြုတဲ့ **Algorithm (တွက်ချက်နည်း)** တစ်ခု ဖြစ်ပါတယ်။

ဆိုလိုတာက **CRC** ဟာ **တွက်ချက်နည်း** ဖြစ်ပြီး၊ **FCS** ဟာ အဲဒီ **တွက်ချက်နည်းကနေ ထွက်လာတဲ့ ရလဒ်** ကို သိမ်းဆည်းထားတဲ့နေရာ (Field) ဖြစ်ပါတယ်ခင်ဗျာ။

### **အလုပ်လုပ်ပုံ ရှင်းလင်းချက်**

Ethernet Frame တစ်ခုကို Sender ကနေ Receiver ကိုပို့တဲ့အခါ ဒီ Process အတိုင်း အလုပ်လုပ်ပါတယ်။

1.  **Sender ဘက်မှ လုပ်ဆောင်ပုံ:**

    - Sender (ပို့သူ) က Frame ထဲမှာပါတဲ့ Data (Ethernet Header, Payload) တွေကို **CRC Algorithm** နဲ့ တွက်ချက်လိုက်ပါတယ်။
    - ဒီလိုတွက်ချက်လိုက်တဲ့အခါ 32 bits ရှိတဲ့ **Checksum** တစ်ခု ထွက်ပေါ်လာပါတယ်။
    - ဒီ Checksum ကို **FCS Field** ထဲမှာ ထည့်သွင်းလိုက်ပြီး Frame ရဲ့ နောက်ဆုံးမှာ ပို့ဆောင်လိုက်ပါတယ်။

2.  **Receiver ဘက်မှ လုပ်ဆောင်ပုံ:**
    - Receiver (လက်ခံသူ) က Frame တစ်ခုလုံးကို လက်ခံရရှိတဲ့အခါ **FCS Field မှလွဲပြီး** ကျန်တဲ့ Data အားလုံးကို **CRC Algorithm** နဲ့ ပြန်တွက်ချက်လိုက်ပါတယ်။
    - ပြီးရင် သူတွက်ချက်လို့ရတဲ့ ရလဒ် (Calculated CRC) ကို **Frame ရဲ့ FCS Field မှာ ပါလာတဲ့ Original CRC တန်ဖိုးနဲ့ တိုက်ဆိုင်စစ်ဆေး** လိုက်ပါတယ်။
    - **အကယ်၍ တန်ဖိုးနှစ်ခုဟာ တူညီတယ်ဆိုရင်** Frame ဟာ လမ်းခရီးမှာ ပျက်စီးမှုမရှိဘဲ မှန်ကန်စွာ ရောက်ရှိလာတယ်လို့ ယူဆပြီး Data ကို လက်ခံလိုက်ပါတယ်။
    - **အကယ်၍ တန်ဖိုးနှစ်ခုဟာ မတူညီဘူးဆိုရင်** Frame ဟာ လမ်းခရီးမှာ ပျက်စီးသွားပြီလို့ ယူဆပြီး **Frame ကို ချက်ချင်း ပယ်ချ (Discard)** လိုက်ပါတယ်။

### **အနှစ်ချုပ်**

**FCS** ဟာ **CRC Algorithm** ကနေ ထွက်လာတဲ့ Error-checking **တန်ဖိုး** ကို သယ်ဆောင်လာတဲ့ Field ဖြစ်ပါတယ်ခင်ဗျာ။ CRC Algorithm ဟာလည်း Ethernet Switching မှာ Data Integrity (Data ရဲ့ မှန်ကန်မှု) ကို ထိန်းသိမ်းပေးတဲ့ အဓိကနည်းပညာတစ်ခုပဲ ဖြစ်ပါတယ်ခင်ဗျာ။

## Destination & Source

Destination နဲ့ Source fields အကြောင်းကို Ethernet Frame ရဲ့ ဖွဲ့စည်းပုံနဲ့ ဆက်စပ်ပြီး ရှင်းပြပေးပါမယ်။ ဒီ fields တွေဟာ OSI Model ရဲ့ Layer 2 (Data Link Layer) မှာပါဝင်ပြီး Frame တွေဟာ Local Network (LAN) အတွင်းမှာ ဘယ်လိုခရီးသွားတယ်ဆိုတာကို သတ်မှတ်ပေးပါတယ်။

### **Source MAC Address Field**

- **အဓိပ္ပါယ်:** Source MAC Address Field ဟာ Frame ကို စတင်ပို့လွှတ်လိုက်တဲ့ Device ရဲ့ **MAC Address** ကို သယ်ဆောင်ထားတဲ့ Field ဖြစ်ပါတယ်။
- **အရွယ်အစား:** 6 Bytes (48 bits) ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** Switch လိုမျိုး Network Device တွေဟာ ဒီ Source MAC Address ကို ကြည့်ပြီး ဘယ် MAC Address က ဘယ် Port မှာ ချိတ်ဆက်ထားတယ်ဆိုတာကို မှတ်သားလေ့လာပါတယ်။ ဒီလိုမှတ်သားထားတဲ့အချက်အလက်တွေကို အသုံးပြုပြီး နောက်ပိုင်းမှာ Destination ကို ပိုမိုမြန်ဆန်စွာ Data ပို့ဆောင်နိုင်ဖို့အတွက် အထောက်အကူပြုပါတယ်။

### **Destination MAC Address Field**

- **အဓိပ္ပါယ်:** Destination MAC Address Field ဟာ Frame ကို လက်ခံရရှိမယ့် Device ရဲ့ **MAC Address** ကို သယ်ဆောင်ထားတဲ့ Field ဖြစ်ပါတယ်။
- **အရွယ်အစား:** 6 Bytes (48 bits) ရှိပါတယ်။
- **လုပ်ဆောင်ချက်:** Switch ဟာ ဒီ Destination MAC Address ကို ကြည့်ပြီး Frame ကို သက်ဆိုင်ရာ Port ဆီကို တိုက်ရိုက်ပို့ဆောင်ပေးပါတယ်။ ဒီလိုမလုပ်နိုင်ရင်တော့ Frame ကို Network မှာရှိတဲ့ Port အားလုံးဆီကို Broadcast ပို့ဆောင်ပါလိမ့်မယ်။

### **နိဂုံးချုပ်**

- **Source MAC Address** က **"ဘယ်ကနေလာတာလဲ"** ဆိုတာကို ပြောပြပါတယ်။
- **Destination MAC Address** ကတော့ **"ဘယ်ကိုသွားရမှာလဲ"** ဆိုတာကို ပြောပြပါတယ်။

ဒီ Fields နှစ်ခုကြောင့်ပဲ Data Frames တွေဟာ Local Network အတွင်းမှာ စနစ်တကျနဲ့ ထိရောက်စွာ အလုပ်လုပ်နိုင်တာ ဖြစ်ပါတယ်ခင်ဗျာ။

## Type or Length

Ethernet Frame မှာပါတဲ့ **Type or Length** Field အကြောင်းကို ရှင်းပြပေးပါမယ်။ ဒီ Field ဟာ Ethernet Header ရဲ့ အစိတ်အပိုင်းတစ်ခုဖြစ်ပြီး **2 Bytes (16 bits)** အရွယ်အစား ရှိပါတယ်။

ဒီ Field ရဲ့ အဓိပ္ပါယ်ဟာ ဘယ်လို Ethernet Standard ကိုသုံးလဲဆိုတဲ့အပေါ်မှာ မူတည်ပြီး ကွဲပြားပါတယ်။

### **1. Type Field (Ethernet II)**

- လက်ရှိအသုံးအများဆုံးဖြစ်တဲ့ Ethernet II Standard မှာ ဒီ Field ကို **`Type`** Field အဖြစ် အသုံးပြုပါတယ်။
- ဒီ Field ရဲ့ တန်ဖိုးဟာ `0x0600` (ဒဿမကိန်းနဲ့ဆိုရင် 1536) ထက် ကြီးတယ်ဆိုရင် ဒါဟာ `Type` Field ဖြစ်တယ်လို့ သတ်မှတ်ပါတယ်။
- `Type` Field ထဲမှာ Frame ရဲ့ Payload (Packet) အပိုင်းမှာ ဘယ်လို Network Layer Protocol ပါလာလဲဆိုတာကို သတ်မှတ်ပေးပါတယ်။
- ဥပမာ-
  - `0x0800` ဆိုရင် Payload ထဲမှာ **IPv4 Packet** ပါလာတယ်လို့ ဆိုလိုပါတယ်။
  - `0x0806` ဆိုရင် Payload ထဲမှာ **ARP Packet** ပါလာတယ်လို့ ဆိုလိုပါတယ်။
- ဒီ Field ကြောင့် Receiver ဘက်က Frame ကို လက်ခံရရှိတဲ့အခါ Payload ထဲက Packet ကို သက်ဆိုင်ရာ Upper Layer Protocol (ဥပမာ- Network Layer မှာရှိတဲ့ IP Process) ဆီကို မှန်မှန်ကန်ကန် လွှဲပေးနိုင်တာ ဖြစ်ပါတယ်။

### **2. Length Field (IEEE 802.3)**

- အစောပိုင်း Standard ဖြစ်တဲ့ IEEE 802.3 မှာတော့ ဒီ Field ကို **`Length`** Field အဖြစ် အသုံးပြုပါတယ်။
- ဒီ Field ရဲ့ တန်ဖိုးဟာ `0x0600` ထက် ငယ်တယ်ဆိုရင် ဒါဟာ `Length` Field ဖြစ်တယ်လို့ သတ်မှတ်ပါတယ်။
- `Length` Field ထဲမှာ Payload ရဲ့ အရွယ်အစား (Byte Size) ကို ဖော်ပြပေးပါတယ်။

### **အနှစ်ချုပ်**

`Type or Length` Field ရဲ့ အဓိကတာဝန်ကတော့ Ethernet Frame ရဲ့ Payload (Data) အပိုင်းမှာ ဘယ်လို Protocol အမျိုးအစား ပါဝင်လဲဆိုတာကို သတ်မှတ်ပေးဖို့ပဲ ဖြစ်ပါတယ်။
