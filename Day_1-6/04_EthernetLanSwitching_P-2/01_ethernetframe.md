# EtherNet Frame

<img src="img/ethernet_frame.png">

ပုံမှာ **OSI Model** နဲ့ **TCP/IP Suite** ဆိုတဲ့ Network Framework နှစ်ခုကို နှိုင်းယှဉ်ပြသထားပါတယ်။

### **OSI Model**

OSI (Open Systems Interconnection) Model ဟာ Network Communication Process ကို အလွှာ (၇) ခု ခွဲပြီး Theory ပိုင်းဆိုင်ရာကို ရှင်းပြပေးတဲ့ Model တစ်ခု ဖြစ်ပါတယ်။

- **Layer 7 - Application:** User နဲ့ Applications တွေနဲ့ သက်ဆိုင်တဲ့ Protocols တွေ (ဥပမာ- HTTP, FTP)။
- **Layer 6 - Presentation:** Data ကို Formats (ဥပမာ- JPG, MP4) ပြောင်းလဲပေးတာ၊ Encryption လုပ်တာတွေလုပ်ဆောင်ပါတယ်။
- **Layer 5 - Session:** Applications နှစ်ခုကြားက Connection (Session) ကို ထိန်းချုပ်ပေးပါတယ်။
- **Layer 4 - Transport:** Data ကို Packet အသေးလေးတွေအဖြစ် ခွဲပြီး (Segmentation) စနစ်တကျ ပို့ဆောင်ပေးတဲ့ Protocols (TCP/UDP) တွေရှိပါတယ်။
- **Layer 3 - Network:** IP Address ကို အသုံးပြုပြီး Network အချင်းချင်း Data ကို လမ်းကြောင်းရှာ ပို့ဆောင်ပေးပါတယ်။
- **Layer 2 - Data Link:** MAC Address ကို အသုံးပြုပြီး LAN (Local Area Network) အတွင်းမှာ Data ကို ပို့ဆောင်ပေးပါတယ်။
- **Layer 1 - Physical:** Physical Medium (ဥပမာ- Cable, Wi-Fi) ပေါ်မှာ Data Bits (0s and 1s) တွေကို ပို့ဆောင်ပေးပါတယ်။

### **TCP/IP Suite**

TCP/IP (Transmission Control Protocol/Internet Protocol) Suite ဟာ လက်ရှိ Internet မှာ အမှန်တကယ် အသုံးပြုနေတဲ့ Model တစ်ခုဖြစ်ပါတယ်။ TCP/IP Model ဟာ OSI Model ကို အခြေခံထားပေမယ့် Layers အရေအတွက်နည်းပြီး ပိုမိုရိုးရှင်းပါတယ်။

- **Layer 4 - Application:** OSI ရဲ့ Layer 5, 6, 7 တို့ကို ပေါင်းစည်းထားပြီး User Applications နဲ့ သက်ဆိုင်တဲ့အရာအားလုံးကို ခြုံငုံထားပါတယ်။
- **Layer 3 - Transport:** OSI ရဲ့ Transport Layer အတိုင်းပဲ TCP နဲ့ UDP Protocols တွေ ပါဝင်ပါတယ်။
- **Layer 2 - Internet:** OSI ရဲ့ Network Layer ကို Internet Layer လို့ခေါ်ပြီး IP Address ကို အသုံးပြုကာ Routing လုပ်ဆောင်ပါတယ်။
- **Layer 1 - Link:** OSI ရဲ့ Data Link နဲ့ Physical Layer တို့ကို ပေါင်းစည်းထားပြီး MAC Address နဲ့ Cable လိုမျိုး Physical Medium တွေနဲ့ သက်ဆိုင်ပါတယ်။

### **ပုံရဲ့ အနှစ်ချုပ်**

ဒီပုံရဲ့ အဓိကအချက်ကတော့ **OSI Model** ဟာ **Theoretical Concept (သီအိုရီပိုင်းဆိုင်ရာ)** ဖြစ်ပြီး၊ **TCP/IP Suite** ကတော့ **Practical Implementation (လက်တွေ့အသုံးချမှု)** ဖြစ်တယ်ဆိုတာကို ရှင်းလင်းစွာ ပြသနေတာပဲ ဖြစ်ပါတယ်။
