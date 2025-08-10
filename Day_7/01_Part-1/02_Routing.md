# Routing

<img src="img/routing.png">

Routing ရဲ့ အခြေခံသဘောတရားကို ရှင်းရှင်းလင်းလင်းမြင်သာစေတဲ့ ပုံဖြစ်ပါတယ်။

ဒီပုံလေးကို အခြေခံပြီး Routing အကြောင်းကို အသေးစိတ်ရှင်းပြပေးပါမယ်ခင်ဗျာ။

### **Routing ဆိုတာ ဘာလဲ။**

Routing ဆိုတာကတော့ Data Packet တွေကို **Network တစ်ခုကနေ နောက် Network တစ်ခုကို ပို့ဆောင်ပေးတဲ့ လုပ်ငန်းစဉ်** ဖြစ်ပါတယ်။ ဒီလုပ်ငန်းစဉ်ကို **Router** လို့ခေါ်တဲ့ Device ကနေ အဓိကလုပ်ဆောင်ပါတယ်။

ပုံထဲမှာ Network နှစ်ခုကို Router (R1) တစ်ခုနဲ့ ချိတ်ဆက်ထားတာကို တွေ့ရပါလိမ့်မယ်။

- **LAN 1:** `192.168.1.0/24` Network (PC1, PC2)
- **LAN 2:** `192.168.2.0/24` Network (PC3, PC4)

### **PC1 ကနေ PC3 ကို Data ပို့ပုံ**

PC1 ကနေ PC3 ကို Data Packet တစ်ခု ပို့မယ်ဆိုရင် အောက်ပါအဆင့်တွေအတိုင်း အလုပ်လုပ်ပါတယ်။

**အဆင့် ၁။ PC1 ရဲ့ ဆုံးဖြတ်ချက်**

- PC1 ဟာ PC3 ရဲ့ IP Address (`192.168.2.1`) ကို သိရှိထားပါတယ်။
- PC1 ဟာ သူ့ရဲ့ IP (`192.168.1.1`) နဲ့ PC3 ရဲ့ IP ကို နှိုင်းယှဉ်ပြီး Destination ဟာ **`ကွဲပြားတဲ့ Network`** မှာရှိတယ်ဆိုတာကို သိရှိသွားပါတယ်။
- ဒီလို ကွဲပြားတဲ့ Network ကိုသွားဖို့အတွက် PC1 ဟာ Data Packet ကို တိုက်ရိုက်မပို့တော့ဘဲ သူ့ရဲ့ **`Default Gateway`** ဖြစ်တဲ့ Router (R1) ဆီကို အရင်ဆုံး ပို့ဆောင်ရပါမယ်။

**အဆင့် ၂။ Data Packet ကို Router ဆီပို့ဆောင်ခြင်း**

- PC1 ဟာ Destination IP Address အနေနဲ့ PC3 ရဲ့ IP (`192.168.2.1`) ကို ထည့်သွင်းပါတယ်။
- ဒါပေမယ့် Destination MAC Address အနေနဲ့ PC3 ရဲ့ MAC Address ကို မထည့်တော့ဘဲ **`Router R1 ရဲ့ G0/0 Interface MAC Address`** ကို ထည့်သွင်းပြီး Frame ကို တည်ဆောက်ပါတယ်။
- SW1 Switch က Frame ကိုလက်ခံရရှိပြီး Router ရဲ့ MAC Address Table ထဲက Entry ကိုကြည့်ပြီး Data Frame ကို R1 ရဲ့ G0/0 Interface ဆီကို ပို့ဆောင်ပေးပါတယ်။

**အဆင့် ၃။ Router (R1) ရဲ့ လုပ်ဆောင်ချက်**

- Router (R1) ဟာ G0/0 Interface ကနေ Data Packet ကို လက်ခံရရှိပါတယ်။
- Router ဟာ Data Packet ရဲ့ Destination IP Address (`192.168.2.1`) ကိုကြည့်ပြီး သူ့ရဲ့ **`Routing Table`** ကို စစ်ဆေးပါတယ်။
- Routing Table ကနေ `192.168.2.0/24` Network ဟာ သူ့ရဲ့ **G0/1 Interface** နဲ့ ချိတ်ဆက်ထားတယ်ဆိုတာကို သိရှိသွားပါတယ်။

**အဆင့် ၄။ Packet ကို Forwarding လုပ်ခြင်း**

- Router ဟာ Data Packet ကို LAN 2 ကိုပို့ဖို့အတွက် **အသစ်ပြန်ပြီး Frame ကိုတည်ဆောက်ပါတယ်**။
- ဒီ Frame မှာ Source MAC Address အနေနဲ့ Router ရဲ့ G0/1 Interface MAC Address ကိုထည့်သွင်းပြီး၊ Destination MAC Address အနေနဲ့ PC3 ရဲ့ MAC Address ကို ထည့်သွင်းပါတယ်။
- ပြီးတဲ့အခါ Router ဟာ ဒီ Frame ကို G0/1 Interface ကနေ SW2 Switch ဆီကို ပို့ဆောင်ပေးလိုက်ပါတယ်။

**အဆင့် ၅။ နောက်ဆုံး Data လက်ခံရရှိခြင်း**

- SW2 Switch ဟာ Frame ကိုလက်ခံရရှိပြီး သူ့ရဲ့ MAC Address Table ကိုကြည့်ပြီး PC3 ရဲ့ MAC Address ရှိတဲ့ Port ကို တိုက်ရိုက်ပို့ဆောင်ပေးလိုက်ပါတယ်။
- ဒီလိုနည်းနဲ့ PC1 ကနေ PC3 ဆီကို Data ရောက်ရှိသွားပါတယ်။

**အနှစ်ချုပ်:**

**Routing** ဆိုတာ Router ကနေ **IP Address** ကို အခြေခံပြီး Network တစ်ခုနဲ့တစ်ခုကြားမှာ Data Packet တွေကို ပို့ဆောင်ပေးတဲ့ လုပ်ငန်းစဉ်ပဲ ဖြစ်ပါတယ်ခင်ဗျာ။
