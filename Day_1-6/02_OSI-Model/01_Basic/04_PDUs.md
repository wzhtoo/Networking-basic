# PDU (Protocol Data Unit)

OSI Model မှာရှိတဲ့ **PDU (Protocol Data Unit)** တွေအကြောင်းကို ရှင်းပြပေးပါမယ်ခင်ဗျာ။ PDU ဆိုတာ OSI Model ရဲ့ အလွှာတစ်ခုချင်းစီမှာ Data တွေကို ပုံစံချပြီး ခေါ်ဝေါ်တဲ့ နာမည်ပဲ ဖြစ်ပါတယ်။

### **PDU ရဲ့ အရေးပါပုံ**

PDU တွေက Data Encapsulation Process ကို ပိုမိုနားလည်လွယ်စေပါတယ်။ တစ်လွှာချင်းစီမှာ Data က ဘယ်လိုပုံစံနဲ့ ဘယ်လိုခေါ်လဲဆိုတာကို သိရှိနိုင်ပါတယ်။

**OSI Model ရဲ့ အလွှာတစ်ခုချင်းစီက PDU များ**

| OSI Layer                                                   | PDU Name       | Process                                                                                                                                                                                       |
| :---------------------------------------------------------- | :------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Layer 7, 6, 5**\<br\>(Application, Presentation, Session) | **Data**\<br\> | ဒီအလွှာတွေမှာ Data ကို မူရင်းပုံစံအတိုင်းပဲ သုံးပါတယ်။\<br\>Protocol Headers တွေ အပြောင်းအလဲ မရှိသေးတဲ့အတွက် Data လို့ပဲ ခေါ်ပါတယ်။                                                           |
| **Layer 4**\<br\>(Transport)                                | **Segment**    | Layer 7, 6, 5 ကနေ ရောက်လာတဲ့ Data ကို Port Number ပါတဲ့ **TCP Header** ထည့်ပြီး **Segment** အဖြစ် ပုံစံချပါတယ်။\<br\>TCP သုံးရင် Segment လို့ခေါ်ပြီး UDP သုံးရင်တော့ Datagram လို့ခေါ်ပါတယ်။ |
| **Layer 3**\<br\>(Network)                                  | **Packet**     | Layer 4 ကနေ ရောက်လာတဲ့ Segment ကို Source IP နဲ့ Destination IP ပါတဲ့ **IP Header** ထည့်ပြီး **Packet** အဖြစ် ပုံစံချပါတယ်။                                                                   |
| **Layer 2**\<br\>(Data Link)                                | **Frame**      | Layer 3 ကနေ ရောက်လာတဲ့ Packet ကို Source MAC နဲ့ Destination MAC ပါတဲ့ **Frame Header** နဲ့ **Trailer (FCS)** ထည့်ပြီး **Frame** အဖြစ် ပုံစံချပါတယ်။                                          |
| **Layer 1**\<br\>(Physical)                                 | **Bits**       | Layer 2 ကနေ ရောက်လာတဲ့ Frame ကို **Digital Bits (0s and 1s)** တွေအဖြစ် ပြောင်းလဲပြီး Physical Medium (Cable/Wireless) ပေါ်ကနေ ပို့ဆောင်ပါတယ်။                                                 |

### **PDU တွေရဲ့ စီးဆင်းပုံ (Encapsulation Process)**

Sender ကနေ Receiver ကို Data ပို့တဲ့အခါ PDU တွေဟာ အောက်ပါအတိုင်း အဆင့်ဆင့် ပြောင်းလဲသွားပါတယ်ခင်ဗျာ။

1.  **Application Layer (Layer 7)** မှာ **Data** ရှိပါတယ်။
2.  Data ကို **Transport Layer (Layer 4)** ကို ပို့လိုက်တဲ့အခါ TCP Header ထည့်ပြီး **Segment** ဖြစ်သွားပါတယ်။
3.  Segment ကို **Network Layer (Layer 3)** ကို ပို့လိုက်တဲ့အခါ IP Header ထည့်ပြီး **Packet** ဖြစ်သွားပါတယ်။
4.  Packet ကို **Data Link Layer (Layer 2)** ကို ပို့လိုက်တဲ့အခါ MAC Header နဲ့ Trailer ထည့်ပြီး **Frame** ဖြစ်သွားပါတယ်။
5.  Frame ကို **Physical Layer (Layer 1)** ကို ပို့လိုက်တဲ့အခါ 0s and 1s တွေအဖြစ် ပြောင်းလဲပြီး **Bits** ဖြစ်သွားပါတယ်။

ဒီ PDU တွေရဲ့ သဘောတရားကို နားလည်ထားခြင်းအားဖြင့် Network Troubleshooting လုပ်တဲ့အခါမှာ ဘယ် Layer မှာ ပြဿနာဖြစ်နေလဲဆိုတာကို ပိုမိုလွယ်ကူစွာ သိရှိနိုင်ပါတယ်ခင်ဗျာ။
