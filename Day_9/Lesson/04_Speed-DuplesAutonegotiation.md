## Speed/Duplex Autonegotiation

### Autonegotiation ဆိုတာဘာလဲ

Autonegotiation ဆိုတာက Ethernet Device နှစ်ခု (ဥပမာ- Router နဲ့ PC) တို့ကြားမှာ အမြန်ဆုံး Speed နဲ့ အကောင်းဆုံး Duplex mode ကို အလိုအလျောက် သတ်မှတ်ပေးတဲ့ လုပ်ဆောင်ချက် ဖြစ်ပါတယ်။

### ဘယ်လိုအလုပ်လုပ်လဲ

1.  **Capability Exchange:** Device တစ်ခုကို Cable နဲ့ ချိတ်ဆက်လိုက်တာနဲ့ Device နှစ်ခုစလုံးက သူတို့ရဲ့ ဘယ်လို Speed တွေ (10 Mbps, 100 Mbps, 1 Gbps) နဲ့ Duplex (Half-duplex, Full-duplex) တွေမှာ အလုပ်လုပ်နိုင်တယ်ဆိုတာကို Fast Link Pulses (FLPs) လို့ခေါ်တဲ့ Signal တွေနဲ့ အချင်းချင်းအပြန်အလှန် ပို့လွှတ်ပြီး ကြေညာပေးကြပါတယ်။
2.  **Agreement:** Device နှစ်ခုစလုံးက လက်ခံနိုင်တဲ့ အမြန်နှုန်းတွေထဲက အမြန်ဆုံး Speed နဲ့ အကောင်းဆုံး Duplex (Full-duplex ကို ဦးစားပေးပါတယ်) ကို ရွေးချယ်ပြီး အချင်းချင်း သဘောတူညီကြပါတယ်။

### Autonegotiation ရဲ့ အားသာချက်

- **ရိုးရှင်းခြင်း:** Network Admin တွေအနေနဲ့ Device တိုင်းမှာ Speed နဲ့ Duplex ကို Manual သွားသတ်မှတ်နေစရာ မလိုတော့ပါဘူး။
- **စွမ်းဆောင်ရည်အမြင့်ဆုံး:** Network ကို အမြန်ဆုံးနဲ့ အကောင်းဆုံး Mode နဲ့ အမြဲတမ်းချိတ်ဆက်ပေးနိုင်တဲ့အတွက် စွမ်းဆောင်ရည်အမြင့်ဆုံးကို ရရှိစေပါတယ်။

### Duplex Mismatch

Autonegotiation မှာ ဖြစ်တတ်တဲ့ အဓိက ပြဿနာကတော့ **Duplex Mismatch** ဖြစ်ပါတယ်။

- ဒါဟာ Device တစ်ဖက်က Full-duplex ဖြစ်နေပြီး၊ ကျန်တစ်ဖက်က Half-duplex ဖြစ်နေတဲ့အခါမျိုးမှာ ဖြစ်တတ်ပါတယ်။
- ဒီလိုဖြစ်တဲ့အခါ Packet Errors, Collisions တွေအများအပြားဖြစ်ပေါ်လာပြီး Network ဟာ အလွန်နှေးကွေးသွားနိုင်ပါတယ်။
- ဒါကြောင့် Device တစ်ခုမှာ Speed နဲ့ Duplex ကို Manual သတ်မှတ်မယ်ဆိုရင် ချိတ်ဆက်မယ့် Device မှာလည်း အတူတူ သတ်မှတ်ပေးဖို့ အရေးကြီးပါတယ်။
