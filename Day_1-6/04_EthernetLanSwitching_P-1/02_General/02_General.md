### တခြား Moboile device နဲ့ wifi အဆက်အသွယ်ရတဲ့ device. iOT တွေက ဘယ်လို Port နဲ့သွားတာလဲခင်ဗျ။ နဲနဲ ရှုပ်ထွေးသွားလို့ပါ။

ဟုတ်ကဲ့ခင်ဗျာ။ သင့်ရဲ့ မေးခွန်းက အလွန်ကောင်းမွန်တဲ့ မေးခွန်းဖြစ်ပြီး `Ethernet` နဲ့ `Wi-Fi` ရဲ့ ကွာခြားချက်ကို အခြေခံထားတဲ့ မေးခွန်းတစ်ခုပါပဲ။

`Wi-Fi` နဲ့ ချိတ်ဆက်တဲ့ Mobile Device တွေ၊ IoT (Internet of Things) Devices တွေက `Port` တွေနဲ့ မသွားပါဘူးခင်ဗျာ။ သူတို့ဟာ **Ethernet switching** ရဲ့ လုပ်ဆောင်ပုံနဲ့ အနည်းငယ်ကွာခြားပါတယ်။

### **Ethernet vs. Wi-Fi (Wireless)**

- **Ethernet** ဆိုတာ `Physical Port` (RJ-45) ကို အသုံးပြုပြီး **Cable ကြိုး** နဲ့ တိုက်ရိုက်ချိတ်ဆက်တဲ့ နည်းပညာဖြစ်ပါတယ်။ ဒါကြောင့် Switch လို Devices တွေက Ports တွေပေါ်မှာ Data တွေကို ပို့ဆောင်တာဖြစ်ပါတယ်။
- **Wi-Fi** ဆိုတာကတော့ `Wireless` (ကြိုးမဲ့) နည်းပညာဖြစ်ပြီး **Radio Frequency (RF)** လှိုင်းတွေကို အသုံးပြုပြီး Data တွေကို ပို့ဆောင်တာဖြစ်ပါတယ်။

### **Mobile & IoT Devices တွေရဲ့ Network Process**

Mobile Device (ဖုန်း၊ Tablet) တွေနဲ့ IoT Device (Smart TV, Smart Bulb) တွေဟာ Network ကို ချိတ်ဆက်တဲ့အခါ အောက်ပါအတိုင်း လုပ်ဆောင်ပါတယ်ခင်ဗျာ။

1.  **Access Point (AP) သို့မဟုတ် Wireless Router:**

    - ဒီ Devices တွေက `Wireless` နည်းပညာဖြစ်တဲ့ Wi-Fi Signal တွေကို လေထဲမှာ ထုတ်လွှတ်ပေးပါတယ်။
    - ဒီ `Wireless Router` မှာလည်း အတွင်းပိုင်းမှာ **Switch** တစ်ခုနဲ့ **Router** တစ်ခု ပါဝင်ပါတယ်။

2.  **Wireless Connection (Wireless "Port")**:

    - သင့်ရဲ့ Mobile Device ဒါမှမဟုတ် IoT Device က `Wireless Router` ကထုတ်လွှတ်ပေးလိုက်တဲ့ Wi-Fi Signal ကို ဖမ်းယူပြီး ချိတ်ဆက်ပါတယ်။
    - ဒီနေရာမှာ `Physical Port` (RJ-45) မပါတော့ဘဲ **Virtual Connection** (ကြိုးမဲ့ ဆက်သွယ်မှု) တစ်ခု ဖြစ်ပေါ်လာပါတယ်။
    - သင့်ရဲ့ Device (ဥပမာ- ဖုန်း) ကနေ `Wireless Router` ကို ချိတ်လိုက်တဲ့အခါ `Router` ကနေ သူ့ရဲ့ **MAC Address Table** ထဲမှာ သင့်ဖုန်းရဲ့ `MAC Address` ကို မှတ်သားလိုက်ပါတယ်။ ဒါဟာ Ethernet Switching ရဲ့ Learning Process နဲ့ ဆင်တူပါတယ်။

3.  **Data Transmission (ကြိုးမဲ့ ဒေတာပို့ဆောင်ခြင်း):**
    - သင့်ရဲ့ဖုန်းကနေ Data Packet ပို့လိုက်တဲ့အခါ ဒီ Packet ဟာ Wireless Signal အဖြစ်နဲ့ `Access Point` ဒါမှမဟုတ် `Wireless Router` ကို ရောက်ရှိသွားပါတယ်။
    - Router က Wireless Signal ကနေ Data Packet ကို လက်ခံယူပြီး **Ethernet (ကြိုး) နဲ့ ပြန်ပြောင်းလဲလိုက်ပါတယ်**။
    - ပြီးရင် Router ရဲ့အတွင်းပိုင်းက `Switch` ကိုဖြတ်ပြီး LAN အတွင်းက တခြား Device ဆီ (သို့မဟုတ်) `Router` ရဲ့ WAN Port ကနေတဆင့် Internet ကို ပို့ဆောင်ပေးတာပဲ ဖြစ်ပါတယ်။

### **အနှစ်ချုပ်:**

- **Wi-Fi Devices** (Mobile, IoT) တွေဟာ **RJ-45 Port** တွေနဲ့ မဆက်သွယ်ကြပါဘူး။
- သူတို့ဟာ **`Wireless Signal` (Radio Waves)** ကို အသုံးပြုပြီး Network ကို ချိတ်ဆက်ကြပါတယ်။
- သူတို့ရဲ့ `Data` တွေဟာ `Wireless Router` ကိုရောက်တဲ့အခါမှာ **Ethernet (ကြိုး) နဲ့ ပြန်လည်ပြောင်းလဲပြီးမှ** LAN ဒါမှမဟုတ် Internet ကို ဆက်လက်ပို့ဆောင်တာ ဖြစ်ပါတယ်။

ဒါကြောင့် သင့်ရဲ့ မေးခွန်းက အဖြေက `Mobile/IoT` Devices တွေဟာ **Physical Port** နဲ့သွားတာမဟုတ်ဘဲ **Wireless Connection** (ကြိုးမဲ့ဆက်သွယ်မှု) နဲ့ သွားတာဖြစ်ပါတယ်ခင်ဗျာ။
