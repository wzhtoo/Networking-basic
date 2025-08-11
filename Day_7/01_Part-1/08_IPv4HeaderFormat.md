# IPv4 Header

<img src="img/IPv4Header.png">

IPv4 Header ဆိုတာကတော့ Network ပေါ်မှာ Data တွေကို ပို့ဆောင်ပေးတဲ့ IP Packet တစ်ခုရဲ့ အရေးအကြီးဆုံး အစိတ်အပိုင်းတစ်ခုပဲ ဖြစ်ပါတယ်။

IPv4 Header ဟာ Packet ရဲ့ ရှေ့ဆုံးမှာ ပါရှိပြီး Data ကို မှန်ကန်စွာ ပို့ဆောင်ဖို့အတွက် လိုအပ်တဲ့ အချက်အလက်အားလုံးကို ထည့်သွင်းပေးထားပါတယ်။

- **Version (4 bits):** IP Protocol ရဲ့ Version ကို ဖော်ပြပါတယ်။ (ဥပမာ- IPv4)။
- **Header Length (4 bits):** IP Header ရဲ့ စုစုပေါင်းအရှည်ကို ဖော်ပြပါတယ်။
- **DSCP:** Network ထဲမှာ Traffic တွေကို ဦးစားပေးမှု (Quality of Service - QoS) ပေးဖို့အတွက် အသုံးပြုပါတယ်။ ဥပမာ- Video Call လိုမျိုး Data တွေက ပုံမှန် Website ဖွင့်တာထက် Priority ပိုမြင့်စေဖို့ သတ်မှတ်နိုင်ပါတယ်။
- **ECN:** Network မှာ Traffic များလာလို့ Congestion (ပိတ်ဆို့မှု) ဖြစ်တဲ့အခါ Data Packet တွေကို လျှော့ချပစ်စရာမလိုဘဲ Sender ဆီကို ပြန်လည်အသိပေးဖို့ အသုံးပြုပါတယ်။
- **Total Length (16 bits):** IP Header နဲ့ Data (Payload) နှစ်ခုပေါင်းရဲ့ စုစုပေါင်းအရှည်ကို ဖော်ပြပါတယ်။
- **Identification (16 bits):** Packet တစ်ခုကို အပိုင်းပိုင်းခွဲ (Fragment) ပြီးပို့တဲ့အခါ မူရင်း Packet ကို ပြန်လည်စုစည်းနိုင်ဖို့အတွက် ခွဲထားတဲ့အပိုင်းတွေကို နံပါတ်စဉ်ပေးထားတာဖြစ်ပါတယ်။
- **Flags (3 bits):** Data Packet ကို အပိုင်းပိုင်းခွဲခြားဖို့ (Fragmentation) ထိန်းချုပ်တဲ့ Flag သုံးခုဖြစ်ပါတယ်။
  - **Bit 1:** Reserved ဖြစ်ပြီး သုံးစွဲခြင်းမရှိပါ။
  - **Bit 2 (Don't Fragment - DF):** ဒီ Bit ကို `1` လို့သတ်မှတ်လိုက်ရင် Packet ကို အပိုင်းပိုင်းခွဲခွင့်မပြုပါဘူး။
  - **Bit 3 (More Fragments - MF):** ဒီ Bit ကို `1` လို့သတ်မှတ်ထားရင် လက်ရှိ Packet ရဲ့နောက်မှာ နောက်ထပ်အပိုင်းဆက်တွေ ပါလာဦးမယ်လို့ ညွှန်ပြပါတယ်။
- **Fragment Offset (13 bits):**
  - ဒီ Bit တွေကတော့ Original Packet ကို Fragment တွေအဖြစ် ခွဲလိုက်တဲ့အခါ Fragment တစ်ခုချင်းစီဟာ မူရင်း Packet ရဲ့ ဘယ်နေရာမှာ ရှိခဲ့လဲဆိုတာကို ဖော်ပြပေးတဲ့ Offset Position တွေဖြစ်ပါတယ်။ ဒါမှ Packet တွေအားလုံး Destination သို့ရောက်တဲ့အခါမှာ မှန်ကန်စွာပြန်လည်စုစည်းနိုင်မှာဖြစ်ပါတယ်။
- **Time to Live (TTL) (8 bits):** Packet တစ်ခု လမ်းကြောင်းမှာ အဆုံးမသတ်ဘဲ ပတ်နေတာမျိုးမဖြစ်အောင် အများဆုံးဖြတ်သန်းနိုင်တဲ့ Router အရေအတွက် (Hop Count) ကို သတ်မှတ်ထားတာဖြစ်ပါတယ်။
- **Protocol (8 bits):** Packet အတွင်းမှာပါရှိတဲ့ Data တွေကို ဘယ် Protocol နဲ့ ပို့ဆောင်ထားလဲဆိုတာကို ဖော်ပြပါတယ်။ (ဥပမာ- TCP (6), UDP (17))။
- **Header Checksum (16 bits):** Header ထဲမှာ Error တစ်ခုခုပါမပါ စစ်ဆေးဖို့အတွက် အသုံးပြုပါတယ်။
- **Source IP Address (32 bits):** Packet ကို ပို့ဆောင်တဲ့ Computer (Source) ရဲ့ IP Address ကို ဖော်ပြပါတယ်။
- **Destination IP Address (32 bits):** Packet ကို လက်ခံမယ့် Computer (Destination) ရဲ့ IP Address ကို ဖော်ပြပါတယ်။

အချုပ်အားဖြင့်ဆိုရသော် IPv4 Header ဟာ စာတစ်စောင်ရဲ့ စာအိတ်ပေါ်မှာ ရေးထားတဲ့ လိပ်စာအပြည့်အစုံနဲ့တူပါတယ်။ Header မှာပါတဲ့ အချက်အလက်တွေကိုကြည့်ပြီး Router တွေက Packet ကို ဘယ်ဆီကို ပို့ဆောင်ရမလဲဆိုတာကို ဆုံးဖြတ်ပါတယ်။
