# TCP-IP_Suite

**TCP/IP Suite (or Protocol Stack)** အကြောင်းကို အသေးစိတ် ရှင်းပြပေးပါမယ်။ OSI Model က Concept အပိုင်းအတွက် အဓိကဖြစ်သလို၊ TCP/IP Suite ကတော့ လက်တွေ့ Internet နဲ့ Network တွေမှာ အသုံးပြုနေတဲ့ Model ဖြစ်လို့ ပိုမိုအရေးကြီးပါတယ်ခင်ဗျာ။

### **TCP/IP Suite ဆိုတာ ဘာလဲ။**

**TCP/IP** ဆိုတာ Network Protocols တွေရဲ့ စုစည်းမှုတစ်ခုဖြစ်ပါတယ်။ **TCP (Transmission Control Protocol)** နဲ့ **IP (Internet Protocol)** ဆိုတဲ့ Protocol နှစ်ခုဟာ ဒီစုစည်းမှုရဲ့ အဓိက Protocol တွေဖြစ်လို့ TCP/IP လို့ အလွယ်ခေါ်ဝေါ်ကြတာ ဖြစ်ပါတယ်။

### **TCP/IP Model ရဲ့ Layers ၄ ခု**

TCP/IP Model မှာ OSI Model ထက် Layers နည်းပြီး အလွှာ ၄ ခုသာ ပါဝင်ပါတယ်။

| TCP/IP Layer Name           | OSI Model Layers (Comparable) | Main Protocols & Functions                                                                                  |
| :-------------------------- | :---------------------------- | :---------------------------------------------------------------------------------------------------------- |
| **Layer 4: Application**    | Layer 7, 6, 5                 | အသုံးပြုသူနဲ့ အနီးဆုံးအလွှာဖြစ်ပြီး Network Application များအတွက် ဝန်ဆောင်မှုပေးသည်။                        |
|                             |                               | **Protocols:** **HTTP**, HTTPS, FTP, **DNS**, SMTP, POP3, SSH, Telnet                                       |
| **Layer 3: Transport**      | Layer 4                       | Data များကို Segments များအဖြစ် ခွဲခြမ်းပြီး Port Number ကို အသုံးပြု၍ Applications များကြား ဆက်သွယ်ပေးသည်။ |
|                             |                               | **Protocols:** **TCP**, **UDP**                                                                             |
| **Layer 2: Internet**       | Layer 3                       | Logical Addressing (IP Address) ကို အသုံးပြု၍ Networks များကြား လမ်းကြောင်းရှာပေးသည်။                       |
|                             |                               | **Protocols:** **IP**, ICMP, ARP, RARP                                                                      |
| **Layer 1: Network Access** | Layer 2, 1                    | Physical Addressing (MAC Address) နှင့် Physical Transmission (Network Medium) တို့ကို ကိုင်တွယ်သည်။        |
|                             |                               | **Protocols:** **Ethernet**, Wi-Fi, Frame Relay, ATM                                                        |

### **အဓိက TCP/IP Protocols များရဲ့ လုပ်ဆောင်ချက်**

#### **1. IP (Internet Protocol) - Internet Layer**

- TCP/IP Suite ရဲ့ အခြေခံအကျဆုံး Protocol ဖြစ်ပါတယ်။
- **Logical Addressing:** IP Address ကို အသုံးပြုပြီး ကွန်ရက်ထဲက Devices တွေကို လိပ်စာ သတ်မှတ်ပေးပါတယ်။ (ဥပမာ- `192.168.1.10`)
- **Routing:** IP Packet တွေကို Destination Address အလိုက် တစ်ခုနဲ့တစ်ခု လွှဲပြောင်းပေးပြီး အကောင်းဆုံး လမ်းကြောင်းကို ရွေးချယ်ပေးပါတယ်။
- **Connectionless:** IP ဟာ Data ကို ပို့ဆောင်တဲ့အခါ ရောက်မရောက်ကို ပြန်စစ်ဆေးမနေပါဘူး။ ဒါဟာ TCP လို Protocol တွေရဲ့ အလုပ်ဖြစ်ပါတယ်။

#### **2. TCP (Transmission Control Protocol) - Transport Layer**

- **Connection-oriented:** Data မပို့ခင် Source နဲ့ Destination ကြားမှာ Connection (Three-way Handshake) ကို တည်ဆောက်ပါတယ်။
- **Reliability (ယုံကြည်စိတ်ချရမှု):** Data Packet တွေ မပျက်စီးဘဲ မှန်ကန်စွာနဲ့ အစီအစဉ်အတိုင်း ရောက်မရောက်ကို စစ်ဆေးပေးပါတယ်။ အကယ်၍ ပျက်စီးသွားရင် ပြန်ပို့ပေးပါတယ်။
- **Flow Control:** Sender နဲ့ Receiver ကြားက Data ပို့ဆောင်တဲ့ အမြန်နှုန်းကို ထိန်းချုပ်ပေးပါတယ်။
- TCP ကို Web Browse (HTTP), Email (SMTP), File Transfer (FTP) တွေမှာ အသုံးပြုပါတယ်။

#### **3. UDP (User Datagram Protocol) - Transport Layer**

- **Connectionless:** Data မပို့ခင် Connection တည်ဆောက်စရာ မလိုပါဘူး။
- **Unreliable:** Data Packet တွေ ရောက်မရောက်ကို စစ်ဆေးမပေးပါဘူး။
- **Speed:** Connection မတည်ဆောက်ရတော့ TCP ထက် ပိုမြန်ပါတယ်။
- UDP ကို Real-time Communication (Live Video Streaming, Online Gaming, Voice calls) တွေမှာ အသုံးပြုပါတယ်။

### **TCP/IP Model ရဲ့ အရေးပါပုံ**

- **Practical Use:** လက်ရှိအသုံးပြုနေတဲ့ Internet ရဲ့ အဓိက Protocols တွေ ဖြစ်ပါတယ်။
- **Simpler than OSI:** Layers အရေအတွက် နည်းတဲ့အတွက် နားလည်ရပိုလွယ်ကူပါတယ်။
- **Interoperability:** TCP/IP ဟာ Open Standard ဖြစ်တဲ့အတွက် မည်သည့် Operating System (Windows, Linux, macOS) သို့မဟုတ် Hardware မျိုးမဆို အချင်းချင်း ချိတ်ဆက်ပြောဆိုနိုင်ပါတယ်။

**အနှစ်ချုပ်အနေနဲ့:** TCP/IP Suite ဟာ Internet ကို အလုပ်လုပ်စေတဲ့ အဓိက Protocols တွေရဲ့ စုစည်းမှုဖြစ်ပြီး၊ Layers 4 ခုကို အသုံးပြုကာ Devices တွေကြားမှာ Data တွေကို စနစ်တကျ ပို့ဆောင်ပေးတဲ့ Framework တစ်ခုပဲ ဖြစ်ပါတယ်ခင်ဗျာ။

Yes, I can convert the image you uploaded into a text-based table. Here is the information from the image, formatted as a table:

| OSI MODEL       | INTERNET              | TCP/IP Suite   |
| :-------------- | :-------------------- | :------------- |
| 7. Application  | H T F M G A B E T     | 4. Application |
| 6. Presentation | I R E R I M A B E E T |                |
| 5. Session      | H S H S F A B B E T   |                |
| 4. Transport    | E C N T 2 E E T       | 3. Transport   |
| 3. Network      | H C I N H 2 E E T     | 2. Internet    |
| 2. Data Link    | M A T H M A B E E T   | 1. Link        |
| 1. Physical     | I A E M G A A B E T   |                |

**Note:** The text in the "INTERNET" column appears to be garbled or a placeholder, as it doesn't correspond to any standard networking terms. The rest of the table accurately reflects the layers of the OSI Model and the TCP/IP Suite, and how they correspond to one another.

<hr>

# TCP/IP Suite နဲ့ OSI Model ကို နှိုင်းယှဉ်ထားတဲ့ Text-based ဇယား

### **TCP/IP Suite vs. OSI Model (Comparative Table)**

| OSI Model Layers          | **TCP/IP Suite Layers**           | RFC 1122    | Cisco Academy  | Forouzan    | ArpaNet Reference Model |
| :------------------------ | :-------------------------------- | :---------- | :------------- | :---------- | :---------------------- |
| **Layer 7: Application**  | **Application**                   | Application | Application    | Application | Application             |
| **Layer 6: Presentation** |                                   |             |                |             |                         |
| **Layer 5: Session**      |                                   |             |                |             |                         |
| **Layer 4: Transport**    | **Transport**                     | Transport   | Transport      | Transport   | Host-to-Host            |
| **Layer 3: Network**      | **Internet**                      | Internet    | Internet       | Network     | Internet                |
| **Layer 2: Data Link**    | **Network Access**\<br\>(or Link) | Link        | Network Access | Data Link   | Link                    |
| **Layer 1: Physical**     |                                   |             |                | Physical    |                         |

**ဇယား ရှင်းလင်းချက်:**

- **OSI Model:** Networking သဘောတရားကို သင်ကြားဖို့အတွက် အသုံးပြုတဲ့ ၇ လွှာပါတဲ့ Standard Model ဖြစ်ပါတယ်။
- **TCP/IP Suite:** လက်ရှိ Internet မှာ အမှန်တကယ် အသုံးပြုနေတဲ့ Model ဖြစ်ပြီး Layers တွေကို သဘောတရားအရ OSI နဲ့ နှိုင်းယှဉ်ပြထားတာ ဖြစ်ပါတယ်။

**Layers Mapping (Layers ကို ဘယ်လို ပေါင်းစည်းထားလဲ):**

- **Application Layer:** OSI ရဲ့ Layer 5, 6, 7 (Session, Presentation, Application) တွေကို TCP/IP ရဲ့ **Application Layer** တစ်ခုတည်းမှာ ပေါင်းစည်းထားပါတယ်။
- **Network Access Layer:** TCP/IP ရဲ့ **Network Access Layer** ဟာ OSI ရဲ့ Layer 1 (Physical) နဲ့ Layer 2 (Data Link) ကို ပေါင်းစည်းထားပါတယ်။

ဒီဇယားကို ကြည့်ခြင်းအားဖြင့် TCP/IP Model မှာ Layers အရေအတွက် နည်းပါးတာကြောင့် ပိုမိုရိုးရှင်းပြီး လက်တွေ့အသုံးဝင်ကြောင်း နားလည်နိုင်ပါတယ်ခင်ဗျာ။
