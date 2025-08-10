# Network address နဲ့ brodcast address

Network Address နဲ့ Broadcast Address ဆိုတာဟာ Subnetting မှာ မဖြစ်မနေသိထားရမယ့် အလွန်အရေးကြီးတဲ့ အယူအဆနှစ်ခုဖြစ်ပါတယ်။ ဒီနှစ်ခုလုံးဟာ Devices တွေကို Assign လုပ်လို့မရတဲ့ Special Address တွေ ဖြစ်ပါတယ်။

### **၁။ Network Address (Network ID)**

- **ဆိုလိုရင်း:** Network Address ဆိုတာဟာ Subnet တစ်ခုရဲ့ **`အစဆုံး Address`** ဖြစ်ပါတယ်။
- **တာဝန်:** ဒီ Address က **Network တစ်ခုလုံးကို ကိုယ်စားပြုတဲ့ ID** ဖြစ်ပြီး Devices တစ်ခုချင်းစီအတွက် မဟုတ်ပါဘူး။
- **တွက်ချက်ပုံ:** Network Address ကို တွက်ချက်ဖို့အတွက် IP Address ရဲ့ **`Host Portion မှာပါတဲ့ Bits တွေအားလုံးကို 0 (သုည) အဖြစ်ထားရပါတယ်`**။

**ဥပမာ:** `192.168.1.0/24` Network ကို ကြည့်ရအောင်။

- **IP Address:** `192.168.1.1` -> `11000000.10101000.00000001`.`00000001`
- `/24` ဆိုတော့ Host Portion မှာ နောက်ဆုံး 8 bits ပါ။
- Host Portion ကို `0` အဖြစ်ထားလိုက်ရင် `00000000` ဖြစ်ပါတယ်။
- ဒါကြောင့် **Network Address** က `192.168.1.0` ဖြစ်ပါတယ်။

### **၂။ Broadcast Address**

- **ဆိုလိုရင်း:** Broadcast Address ဆိုတာဟာ Subnet တစ်ခုရဲ့ **`အဆုံးဆုံး Address`** ဖြစ်ပါတယ်။
- **တာဝန်:** ဒီ Address ကို အသုံးပြုပြီး Network ထဲမှာရှိတဲ့ **`Devices အားလုံးဆီကို တစ်ပြိုင်တည်း Message ပို့ဆောင်နိုင်ပါတယ်`**။
- **တွက်ချက်ပုံ:** Broadcast Address ကို တွက်ချက်ဖို့အတွက် IP Address ရဲ့ **`Host Portion မှာပါတဲ့ Bits တွေအားလုံးကို 1 (တစ်) အဖြစ်ထားရပါတယ်`**။

**ဥပမာ:** `192.168.1.0/24` Network ကို ကြည့်ရအောင်။

- **IP Address:** `192.168.1.1` -> `11000000.10101000.00000001`.`00000001`
- `/24` ဆိုတော့ Host Portion မှာ နောက်ဆုံး 8 bits ပါ။
- Host Portion ကို `1` အဖြစ်ထားလိုက်ရင် `11111111` ဖြစ်ပါတယ်။
- ဒါကြောင့် **Broadcast Address** က `192.168.1.255` ဖြစ်ပါတယ်။

### **Usable Host Addresses (အသုံးပြုနိုင်တဲ့ Address များ)**

- Network Address နဲ့ Broadcast Address ကြားမှာရှိတဲ့ Address တွေအားလုံးကတော့ Devices တွေကို တကယ် assign လုပ်ပြီး အသုံးပြုနိုင်တဲ့ Address တွေဖြစ်ပါတယ်။
- ဥပမာ- `192.168.1.0/24` Network မှာ Usable Host Addresses တွေက `192.168.1.1` မှ `192.168.1.254` အထိဖြစ်ပါတယ်။

**အနှစ်ချုပ်:**

Network Address (`192.168.1.0`) နဲ့ Broadcast Address (`192.168.1.255`) တို့ဟာ အထူးသတ်မှတ်ထားတဲ့ Addresses တွေဖြစ်တဲ့အတွက် **Computer တွေ၊ Router တွေကို Assign လုပ်လို့မရပါဘူး**။ သူတို့ရဲ့ကြားမှာရှိတဲ့ Address တွေကိုသာ အသုံးပြုနိုင်ပါတယ်။
