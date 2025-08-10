# ARP vs Unicast

- ARP Request နဲ့ ARP Reply ဆိုလိုတာက Known unicast နဲ့ unknown unicast လိုပေါ့နော်။

သင့်ရဲ့အတွေးအခေါ်က အလွန်ကောင်းမွန်ပါတယ်။ သင်ဟာ သင်ယူထားတဲ့ Concept တွေကို ဆက်စပ်တွေးတောပြီး ကိုယ်ပိုင် Models တွေတည်ဆောက်နေတာကို တွေ့ရပါတယ်ခင်ဗျာ။ ဒါဟာ အသိပညာကို အလွတ်ကျက်မှတ်တာထက် ပိုမိုနက်ရှိုင်းစွာ နားလည်စေပါတယ်။

ဒါပေမယ့် သင်တွေးထားတဲ့ `ARP Request/Reply` ကို `Unknown Unicast/Known Unicast` နဲ့ ယှဉ်ပြထားတဲ့ analogy ကတော့ အနည်းငယ်လွဲချော်နေပါတယ်ခင်ဗျာ။ ဒီနှစ်ခုရဲ့ ခြားနားချက်ကို ရှင်းရှင်းလင်းလင်းဖြစ်သွားအောင် ရှင်းပြပေးပါမယ်။

### **၁။ ARP Request vs. ARP Reply**

- ဒါတွေဟာ **`ARP Protocol`** ရဲ့ အစိတ်အပိုင်းနှစ်ခုပဲ ဖြစ်ပါတယ်။
- **ARP Request:** MAC Address ရှာဖို့အတွက် **Broadcast** အနေနဲ့ ပို့တဲ့ မေးခွန်းပါ။
- **ARP Reply:** မေးခွန်းကိုဖြေတဲ့အနေနဲ့ Destination ရဲ့ MAC Address ပါတဲ့ **Unicast** အနေနဲ့ ပြန်ပို့တဲ့ အဖြေပါ။
- ဒါကြောင့် ARP Request/Reply ဟာ **လုပ်ဆောင်ချက်တစ်ခုရဲ့ အဆင့်နှစ်ဆင့်** ဖြစ်ပါတယ်။

### **၂။ Unknown Unicast vs. Known Unicast**

- ဒါတွေကတော့ **`Switch`** ရဲ့ **`Frame Forwarding Behavior`** နှစ်ခုပဲ ဖြစ်ပါတယ်။
- **Unknown Unicast:** Switch ရဲ့ MAC Table ထဲမှာမရှိသေးတဲ့ MAC Address ပါတဲ့ Frame ကို Switch ကနေ **Flood** လုပ်ပေးလိုက်တဲ့ အပြုအမူပါ။
- **Known Unicast:** Switch က MAC Table ထဲမှာ ရှိပြီးသား MAC Address ကိုသာ သက်ဆိုင်ရာ Port ဆီကို **တိုက်ရိုက်ပို့ဆောင်** ပေးတဲ့ အပြုအမူပါ။

### **အမှန်တကယ် ဆက်စပ်ပုံ**

ဒီနှစ်ခုကို တူညီတဲ့ Analogical ပုံစံမျိုးနဲ့ ယှဉ်ကြည့်လို့မရပါဘူး။ သူတို့ရဲ့ ဆက်စပ်မှုကတော့ အောက်ပါအတိုင်း ဖြစ်ပါတယ်ခင်ဗျာ။

1.  **ARP Request:** သင်က PC1 အနေနဲ့ PC2 ကို Data ပို့ဖို့ PC2 ရဲ့ MAC Address ကို မသိသေးဘူး။ ဒါကြောင့် MAC Address ရှာဖို့ **ARP Request (Broadcast)** ကို ပို့လိုက်တယ်။
2.  **Unknown Unicast:** အကယ်၍ Switch ရဲ့ MAC Table ထဲမှာ PC1 ရဲ့ MAC Address မရှိသေးဘူးဆိုရင် Switch က PC1 ရဲ့ ARP Request Frame (Broadcast) ကို **Unknown Unicast လိုမျိုး Ports အားလုံးဆီကို Flood လုပ်ပေးလိုက်တယ်**။ (ဒါပေမယ့် ARP Request ဟာ Broadcast Frame ဖြစ်တဲ့အတွက် Flood လုပ်တာဟာ Unknown Unicast မဟုတ်ဘဲ Broadcast ရဲ့ သဘာဝပါ)။
3.  **ARP Reply:** PC2 က သူ့ MAC Address ကို **ARP Reply (Unicast)** အနေနဲ့ PC1 ဆီပြန်ပို့တယ်။ ဒီ Reply မှာ PC2 ရဲ့ MAC Address ပါပါတယ်။
4.  **Known Unicast:** PC1 က PC2 ရဲ့ MAC Address ကိုသိသွားတဲ့အတွက် အခုဆိုရင် **Data Frame (Unicast)** ကို PC2 ရဲ့ MAC Address နဲ့ တည်ဆောက်ပြီးပို့နိုင်ပြီ။ Switch ကလည်း သူ့ရဲ့ Table မှာ PC2 ရဲ့ MAC Address ရှိတဲ့ Port ကိုသိရှိသွားပြီဖြစ်တဲ့အတွက် ဒီ Frame ကို **Known Unicast** အနေနဲ့ PC2 ဆီကို တိုက်ရိုက်ပို့ပေးတော့မှာ ဖြစ်ပါတယ်။

ဒါကြောင့် **`ARP` ဟာ Address ကို ရှာဖွေတဲ့ Protocol တစ်ခုဖြစ်ပြီး**၊ **`Unicast` ကတော့ Switch ကနေ Frame တွေကို ပို့တဲ့အပြုအမူပဲ ဖြစ်ပါတယ်**။ သူတို့ရဲ့ ရည်ရွယ်ချက် မတူပါဘူးခင်ဗျာ။

<hr>

- Good afternoon!
  `clear mac address-table dynamic` ဒီ command line က mac address ကို clear လုပ်တာ ဘာရည်ရွယ်ချက်နဲ့ လုပ်ရတာလဲခင်ဗျ။

- Good Afternoon!

သင့်ရဲ့မေးခွန်းက အလွန်လက်တွေ့ကျပြီး Network Troubleshooting နဲ့ Maintenance မှာ အရေးကြီးတဲ့ Command တစ်ခုအကြောင်းကို မေးလိုက်တာဖြစ်ပါတယ်ခင်ဗျာ။

`clear mac address-table dynamic` ဆိုတဲ့ Command ရဲ့ အဓိကရည်ရွယ်ချက်ကတော့ **Switch ရဲ့ MAC Address Table ထဲမှာရှိတဲ့ Dynamic Entries (အလိုအလျောက် မှတ်သားထားတဲ့ အချက်အလက်များ) အားလုံးကို ဖျက်ပစ်ဖို့** ဖြစ်ပါတယ်။

ဒါကို ဘာရည်ရွယ်ချက်နဲ့ လုပ်ရလဲဆိုတော့ အောက်ပါအကြောင်းရင်းများကြောင့်ဖြစ်ပါတယ်ခင်ဗျာ။

### **၁။ Troubleshooting (ပြဿနာရှာဖွေခြင်း)**

- **Device တွေနေရာရွေ့ပြောင်းခြင်း:** Computer တစ်လုံးကို Switch ရဲ့ Port တစ်ခုကနေ နောက် Port တစ်ခုဆီကို ရွှေ့လိုက်တဲ့အခါ Switch ရဲ့ Table မှာ အဟောင်း entries တွေကျန်နေနိုင်ပါတယ်။ ဒီအခါမှာ Traffic တွေက မှားယွင်းတဲ့ Port ကို ရောက်သွားနိုင်ပါတယ်။ ဒီ Command ကိုရိုက်လိုက်ရင် Switch ဟာ အဲဒီ Device တွေရဲ့ တည်နေရာအသစ်ကို ပြန်လည်မှတ်သား (Re-learn) ပြီး ပြဿနာကို ဖြေရှင်းပေးနိုင်ပါတယ်။
- **Network Loop များ:** Network ထဲမှာ Loop တစ်ခုဖြစ်သွားတဲ့အခါ Switch ရဲ့ MAC Table ထဲမှာ မမှန်ကန်တဲ့ entries တွေဝင်လာပြီး Network Performance ကို ကျဆင်းစေနိုင်ပါတယ်။ Table ကို clear လုပ်လိုက်ခြင်းဖြင့် Loop ကြောင့်ဖြစ်ပေါ်လာတဲ့ မှားယွင်းတဲ့ entries တွေကို ရှင်းလင်းနိုင်ပါတယ်။

### **၂။ Security (လုံခြုံရေး)**

- **MAC Flooding Attack:** Attacker တစ်ယောက်က Switch ရဲ့ MAC Table ကို Fake MAC Address တွေနဲ့ ပြည့်အောင်လုပ်ပြီး Attack လုပ်တဲ့အခါ Switch ဟာ Hub တစ်ခုလို Behavior ဖြစ်သွားပါတယ်။ Table ကို clear လုပ်လိုက်ခြင်းဖြင့် Attacker ရဲ့ Fake entries တွေကို ဖျက်ပစ်ပြီး Attack ကို ခေတ္တရပ်တန့်စေနိုင်ပါတယ်။
- **ARP Spoofing:** ARP Spoofing Attack တစ်ခုဖြစ်တဲ့အခါ MAC Table ထဲမှာ Attacker ရဲ့ MAC Address တွေ မှတ်သားမိနေနိုင်ပါတယ်။ Command ရိုက်ပြီး Table ကို ရှင်းလိုက်တဲ့အခါ မမှန်ကန်တဲ့ entries တွေကို ဖျက်ပစ်လိုက်နိုင်ပါတယ်။

### **၃။ Performance Issue (စွမ်းဆောင်ရည်ပြဿနာများ)**

- အလွန်ကြီးမားတဲ့ Network တွေမှာ Mac Table အရမ်းကြီးသွားတဲ့အခါ Switch ရဲ့ Performance ကို အနည်းငယ်ကျဆင်းစေနိုင်ပါတယ်။ ဒီ Command က Table ကိုရှင်းပြီး Performance ကို အနည်းငယ်မြှင့်တင်ပေးနိုင်ပါတယ်။

**အနှစ်ချုပ်:**

`clear mac address-table dynamic` Command ရဲ့ အဓိကရည်ရွယ်ချက်ကတော့ **ပြဿနာတွေရှိတဲ့အခါ Switch ရဲ့ MAC Table ကို ရှင်းလင်းပြီး Network မှာရှိတဲ့ Devices တွေရဲ့ တည်နေရာကို အသစ်ပြန်လည်မှတ်သားစေဖို့ပဲ ဖြစ်ပါတယ်**။ ဒါပေမယ့် ဒီ Command ကို ရိုက်လိုက်တဲ့အခါ Network Traffic တွေဟာ ခဏတာ Flooding ဖြစ်သွားနိုင်တဲ့အတွက် Production Environment မှာတော့ သတိထားပြီး အသုံးပြုရပါတယ်ခင်ဗျာ။

<hr>

- ဟုတ်ကဲ့ switch ရဲ့ Mac table ကို clear လုပ်ပြီး Mac address တွေကို adminstrator က အသစ်ပြန်ပြီး သတ်မှတ်ပေးရတာလား။ အသစ်ပြန်ပြီး ပေးရမယ်ဆိုရင် switch တွေ ထောင်သောင်းမက ရှိနေရင်တော့ အခက်တွေ့နိုင်ပါတယ်လို့ ယူဆမိပါတယ်။

သင့်ရဲ့မေးခွန်းက အလွန်ကောင်းမွန်ပါတယ်။ သင်ဟာ နက်ဝပ်စီမံခန့်ခွဲမှုရဲ့ လက်တွေ့ကျတဲ့ အခက်အခဲတွေကိုပါ ထည့်သွင်းစဉ်းစားတာကို တွေ့ရပါတယ်ခင်ဗျာ။

သင့်ရဲ့ယူဆချက်က မှန်ကန်ပါတယ်၊ Switch တွေ ထောင်သောင်းမကရှိတဲ့ Network ကြီးတစ်ခုမှာ MAC Address တွေကို Administrator ကနေ ကိုယ်တိုင်ပြန်ပြီး သတ်မှတ်ပေးရမယ်ဆိုရင် ဒါဟာ လုံးဝမဖြစ်နိုင်တဲ့ အခက်အခဲတစ်ခုဖြစ်မှာပါ။

ဒါပေမယ့် သင့်ရဲ့ယူဆချက်က မှားယွင်းနေပါတယ်ခင်ဗျာ။ Administrator အနေနဲ့ MAC Address တွေကို **`အသစ်ပြန်ပြီး သတ်မှတ်ပေးစရာမလိုပါဘူး`**။

### **Switch ရဲ့ MAC Address မှတ်သားပုံ (Dynamic Learning)**

- Switch ရဲ့ အဓိကတာဝန်တွေထဲက တစ်ခုကတော့ **`Dynamic Learning`** လို့ခေါ်တဲ့ အလိုအလျောက်သင်ယူခြင်းပဲ ဖြစ်ပါတယ်။
- Switch တစ်လုံးဟာ Port တစ်ခုကနေ Frame တစ်ခုကို လက်ခံရရှိတဲ့အခါ အဲဒီ Frame ရဲ့ **Source MAC Address** ကိုဖတ်ပြီး ဘယ် MAC Address ဟာ ဘယ် Port မှာရှိတယ်ဆိုတာကို အလိုအလျောက် မှတ်သားထားပါတယ်။
- ဒီလို အလိုအလျောက်မှတ်သားထားတဲ့ Entries တွေကို **`Dynamic Entries`** လို့ခေါ်ပါတယ်။

### **Command ရဲ့ အလုပ်လုပ်ပုံ**

- `clear mac address-table dynamic` ဆိုတဲ့ Command ဟာ အဲဒီလို **`အလိုအလျောက်မှတ်သားထားတဲ့ Entries တွေကိုသာ`** ဖျက်ပစ်တာ ဖြစ်ပါတယ်။
- ဒီ Command ကိုရိုက်ပြီးနောက် MAC Address Table မှာ Entries တွေမရှိတော့ပေမယ့် Network ထဲက Devices တွေက Data တွေစပြီးပြန်ပို့တာနဲ့ Switch ဟာ သူတို့ရဲ့ MAC Address တွေကို **`အလိုအလျောက်`** ပြန်လည်မှတ်သားသွားမှာ ဖြစ်ပါတယ်။
- ဒီဖြစ်စဉ်ဟာ အလွန်မြန်ဆန်တဲ့အတွက် Network Disruption (ပြတ်တောက်မှု) ကလည်း ခဏတာပဲ ဖြစ်ပါတယ်။

### **အနှစ်ချုပ်**

Administrator အနေနဲ့ Switch ရဲ့ MAC Table ကို ကိုယ်တိုင်ပြန်ဖြည့်ပေးစရာမလိုပါဘူး။ `clear mac address-table dynamic` Command ရဲ့ ရည်ရွယ်ချက်ဟာ **`Manual ပြန်ထည့်ဖို့မဟုတ်ဘဲ`** Switch ရဲ့ **`Automatic Learning Process`** ကို ပြန်လည်စတင်စေဖို့ပဲ ဖြစ်ပါတယ်။ ဒီလိုလုပ်ဆောင်နိုင်တဲ့အတွက် Network ကြီးတွေမှာတောင် Switch တွေကို လွယ်လွယ်ကူကူ Maintenance လုပ်နိုင်တာ ဖြစ်ပါတယ်ခင်ဗျာ။

<hr>

- ကျနော် သိပ်မရှင်းလို့ပါ။ Switch မသုံးထားတဲ့ ကျနော်တို့ အိမ်သုံး Router တွေမှာ ဆိုရင် wifi အသုံးပြုသူတွေက နေ့တိုင်း သုံးနေတော့ အချိန်တွေကြာလာတာနဲ့ အမျှ ခုနကပြောတဲ့ mac table တွေမှာ မလိုအပ်တာတွေ ပြည့်နေပြီး wifi signal တွေကျဆင်းနိုင်လားခင်ဗျ။ Router ကလည်း Switch လို အလုပ်လုပ်ပါသလား။ မရှင်းဘူးဖြစ်နေပါတယ်။

သင့်ရဲ့မေးခွန်းက အိမ်သုံး Router တွေရဲ့ သဘောတရားကို နက်နက်နဲနဲ စဉ်းစားပြီး မေးလိုက်တာဖြစ်ပါတယ်ခင်ဗျာ။ ဒါဟာ Network Beginners တွေ အများဆုံး Confuse ဖြစ်တတ်တဲ့ အချက်တစ်ခုပါပဲ။

သင့်ရဲ့မေးခွန်းနှစ်ခုလုံးကို ရှင်းလင်းအောင် ဖြေပေးပါမယ်ခင်ဗျာ။

### **၁။ Router က Switch လို အလုပ်လုပ်ပါသလား။**

- **`ဟုတ်ကဲ့၊ အလုပ်လုပ်ပါတယ်`**။
- သင်အသုံးပြုနေတဲ့ အိမ်သုံး Router တွေဟာ တကယ်တော့ Router, Switch, Firewall နဲ့ Wireless Access Point ဆိုတဲ့ Devices လေးခုပေါင်းထားတဲ့ All-in-one Device တစ်ခုဖြစ်ပါတယ်။
- Router ရဲ့ နောက်ကျောမှာပါတဲ့ Wired Port တွေ (များသောအားဖြင့် 4 Port) က **Switch အနေနဲ့ အလုပ်လုပ်ပါတယ်**။
- အဲဒီ Built-in Switch နဲ့ Wireless Access Point (Wi-Fi) တို့ဟာ သူတို့နဲ့ချိတ်ဆက်ထားတဲ့ Devices တွေရဲ့ MAC Address တွေကို သင်ပြောခဲ့တဲ့ **MAC Address Table ထဲမှာ မှတ်သားထားပါတယ်**။

### **၂။ MAC Table ပြည့်ပြီး Wi-Fi ကျဆင်းနိုင်ပါသလား။**

- **`ဒီလိုဖြစ်ဖို့ အလွန်ကို မဖြစ်နိုင်ပါဘူး`**။
- သီအိုရီအရတော့ MAC Table ပြည့်သွားရင် Network Performance ကျဆင်းနိုင်ပါတယ်။ ဒါပေမယ့် လက်တွေ့ အိမ်သုံး Network မှာတော့ ဒီလိုဖြစ်ဖို့ ခဲယဉ်းပါတယ်။
- **အကြောင်းရင်းများ:**
  - **Table အရွယ်အစား:** ခေတ်ပေါ် Router တွေရဲ့ MAC Table ဟာ အိမ်သုံးမှာ သုံးနေကျ Devices အရေအတွက်ထက် အဆပေါင်းများစွာ ပိုများပါတယ် (ဥပမာ- 1K မှ 8K အထိ)။
  - **Aging Time (သက်တမ်းကုန်ဆုံးချိန်):** MAC Address Table ထဲက Entry တွေဟာ ထာဝရရှိနေတာမဟုတ်ပါဘူး။ Device တစ်ခုဟာ အချိန်တစ်ခုအထိ Traffic မပို့တော့ဘူးဆိုရင် (ဥပမာ- မိနစ် ၅ မိနစ်) သူ့ရဲ့ Entry ဟာ Table ကနေ အလိုအလျောက် ပျက်သွားပါတယ်။ ဒါကြောင့် Table ဟာ နေ့တိုင်းအသစ်ဖြစ်နေတာပါ။
  - **Home Network Devices:** အိမ်သုံး Network မှာ Devices (Computer, Phone, TV, etc.) အရေအတွက်ဟာ အများဆုံး ၁၀ လုံးကနေ ၂၀ လုံးလောက်ပဲ ရှိတတ်တဲ့အတွက် MAC Table ပြည့်သွားဖို့ဆိုတာ မဖြစ်နိုင်သလောက်ပါပဲ။

### **Wi-Fi Signal တွေ ဘာကြောင့်ကျဆင်းတာလဲ။**

သင့်ရဲ့ Wi-Fi Signal ကျဆင်းတာဟာ MAC Table ပြည့်လို့မဟုတ်ဘဲ အောက်ပါအကြောင်းရင်းတွေကြောင့် အများဆုံးဖြစ်တတ်ပါတယ်။

1.  **Interference:** ဘေးအိမ်က Wi-Fi Router နဲ့ သင့် Router ဟာ တူညီတဲ့ Channel ကို အသုံးပြုနေတဲ့အတွက် Signal တွေ ထပ်နေခြင်း။
2.  **Physical Obstructions:** သင့် Router နဲ့ သင့် Device ကြားမှာ နံရံတွေ၊ ပရိဘောဂတွေ ကာနေခြင်း။
3.  **Bandwidth Saturation:** Network ထဲက Device အများအပြားဟာ တစ်ပြိုင်တည်း Video တွေကြည့်တာ၊ Download လုပ်တာတွေလုပ်နေခြင်း။
4.  **Hardware Issue:** သင့်ရဲ့ Router ဟာ အိုနေခြင်း သို့မဟုတ် အပူလွန်ကဲနေခြင်း။

**အနှစ်ချုပ်:**

သင့်ရဲ့ အိမ်သုံး Router ဟာ Switch လိုပဲ MAC Table တွေကို အသုံးပြုပေမယ့်၊ အဲဒီ Table တွေ ပြည့်သွားလို့ Wi-Fi Signal ကျဆင်းတာမျိုးတော့ မဖြစ်နိုင်ပါဘူးခင်ဗျာ။
