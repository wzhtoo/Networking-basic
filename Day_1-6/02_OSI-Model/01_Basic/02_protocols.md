# Protocols

Protocols ဆိုတာ Network ထဲမှာ Devices တွေ (ကွန်ပျူတာ၊ Router, Switch စသည်) အချင်းချင်း ဆက်သွယ်ပြောဆိုကြဖို့အတွက် သတ်မှတ်ထားတဲ့ စည်းမျဉ်းစည်းကမ်းများ (Rules and Procedures) ကို ပြောတာ ဖြစ်ပါတယ်။ ဒါဟာ လူတွေ စကားပြောကြတဲ့အခါ ဘာသာစကား (Language) နဲ့ အပြန်အလှန်နားလည်နိုင်သလိုပဲ၊ Network Devices တွေအတွက် ဘာသာစကားတစ်ခုလိုပဲလို့ တင်စားနိုင်ပါတယ်ခင်ဗျာ။

Protocols တွေမရှိရင် ကွန်ပျူတာတွေကြားမှာ အချက်အလက် (Data) တွေကို စနစ်တကျ ပို့ဆောင်နိုင်မှာ မဟုတ်ပါဘူး။

### **Protocols တွေရဲ့ အဓိက လုပ်ဆောင်ချက်များ**

1.  **Standardization (စံသတ်မှတ်ခြင်း):**

    - Protocols တွေက မတူညီတဲ့ Vendors (ဥပမာ- Cisco, Juniper, TP-Link) တွေက ထုတ်လုပ်တဲ့ စက်ပစ္စည်းတွေဟာ Protocol တစ်ခုတည်းကို လိုက်နာခြင်းအားဖြင့် အချင်းချင်း ချိတ်ဆက်ပြောဆိုနိုင်ဖို့ စံတစ်ခုကို သတ်မှတ်ပေးပါတယ်။
    - ဥပမာ- TCP/IP Protocol ဟာ Internet မှာရှိတဲ့ Devices အားလုံးအတွက် Universal Standard တစ်ခု ဖြစ်ပါတယ်။

2.  **Data Formatting (ဒေတာပုံစံချခြင်း):**

    - ကွန်ပျူတာတစ်လုံးက Data တွေကို ပို့တဲ့အခါ၊ အဲဒီ Data ကို Protocol က သတ်မှတ်ထားတဲ့ ပုံစံအတိုင်း Packet, Frame, ဒါမှမဟုတ် Segment တွေအဖြစ် ခွဲခြမ်းစိတ်ဖြာပြီး ပုံစံချပေးပါတယ်။
    - လက်ခံမယ့် ကွန်ပျူတာကလည်း အဲဒီပုံစံအတိုင်းပဲ ပြန်လည်စုစည်းပြီး ဖတ်နိုင်ပါတယ်။

3.  **Error Handling (အမှားပြင်ဆင်ခြင်း):**

    - Network ပေါ်မှာ Data တွေပို့နေရင်း အလယ်မှာ ပျောက်သွားတာ ဒါမှမဟုတ် မှားယွင်းသွားတာမျိုးတွေ ဖြစ်နိုင်ပါတယ်။ Protocols တွေက အဲဒီအမှားတွေကို ရှာဖွေပြီး ပြန်ပို့ဖို့၊ ပြင်ဆင်ဖို့ စတဲ့ အစီအစဉ်တွေကို လုပ်ဆောင်ပေးပါတယ်။
    - ဥပမာ- TCP Protocol မှာ Data Packet တွေ မူရင်းနေရာကို ရောက်မရောက်ဆိုတာ အမြဲတမ်း စစ်ဆေးပေးပါတယ်။

4.  **Addressing (လိပ်စာသတ်မှတ်ခြင်း):**
    - ကွန်ရက်တစ်ခုအတွင်းက Devices တွေကို တစ်ခုနဲ့တစ်ခု ခွဲခြားသိမြင်နိုင်ဖို့အတွက် IP Address, MAC Address စတဲ့ လိပ်စာတွေကို Protocols တွေကနေ သတ်မှတ်ပေးပါတယ်။
    - ဥပမာ- IP (Internet Protocol) က IP Address ကို အသုံးပြုပြီး၊ Ethernet က MAC Address ကို အသုံးပြုပါတယ်။

### **Protocols အမျိုးအစားများ (Examples)**

Protocols တွေဟာ OSI Model ဒါမှမဟုတ် TCP/IP Model ရဲ့ အလွှာတစ်ခုချင်းစီမှာ သီးသန့်တည်ရှိပြီး အလုပ်လုပ်ကြပါတယ်။

- **Layer 4 (Transport Layer):**

  - **TCP (Transmission Control Protocol):** Reliability (ယုံကြည်စိတ်ချရမှု) ကို အဓိကထားတဲ့ Protocol ဖြစ်ပါတယ်။ Data ကို စနစ်တကျနဲ့ အမှားအယွင်းမရှိ ပို့ဆောင်ပေးပါတယ်။ Web Browse, Email, File Transfer တွေမှာ အသုံးပြုပါတယ်။
  - **UDP (User Datagram Protocol):** Speed ကို အဓိကထားတဲ့ Protocol ဖြစ်ပါတယ်။ Real-time Communication (Voice, Video Streaming) တွေမှာ အသုံးပြုပြီး Data လေးနည်းနည်းလောက် ပျောက်သွားရင်တောင် ကိစ္စမရှိပါဘူး။

- **Layer 3 (Internet Layer):**

  - **IP (Internet Protocol):** Network ပေါ်မှာ Devices တွေကို IP Address နဲ့ လိပ်စာပေးပြီး Routing လုပ်ပေးတဲ့ အဓိက Protocol ဖြစ်ပါတယ်။
  - **ICMP (Internet Control Message Protocol):** Network Error တွေကို Report လုပ်ဖို့နဲ့ Network Diagnostics (ဥပမာ- Ping Command) အတွက် အသုံးပြုပါတယ်။

- **Layer 7 (Application Layer):**
  - **HTTP (Hypertext Transfer Protocol):** Web Browsers နဲ့ Web Servers တွေကြားမှာ ဆက်သွယ်ပြောဆိုတဲ့ Protocol ဖြစ်ပါတယ်။
  - **FTP (File Transfer Protocol):** File တွေကို ကွန်ရက်ပေါ်မှာ ပို့ဖို့ အသုံးပြုတဲ့ Protocol ဖြစ်ပါတယ်။
  - **SMTP (Simple Mail Transfer Protocol):** Email တွေကို ပို့ဖို့ အသုံးပြုတဲ့ Protocol ဖြစ်ပါတယ်။

### **အနှစ်ချုပ်:**

Protocols ဆိုတာ ကွန်ရက်တစ်ခုမှာ Devices တွေ အချင်းချင်း ချိတ်ဆက်ပြောဆိုနိုင်ဖို့ သတ်မှတ်ထားတဲ့ စည်းမျဉ်းတွေပဲ ဖြစ်ပါတယ်။ ဒါကြောင့် Network ရဲ့ စနစ်တကျ အလုပ်လုပ်နိုင်ဖို့အတွက် Protocols တွေဟာ မရှိမဖြစ် လိုအပ်ပါတယ်ခင်ဗျာ။
