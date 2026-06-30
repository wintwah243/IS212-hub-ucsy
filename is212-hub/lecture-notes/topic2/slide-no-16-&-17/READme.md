# Improving Efficiency: Hash-Based Technique (slide 16 and 17 - 28.6.2026)

Even though the basic Apriori algorithm is smart, it can still generate a massive number of "candidate" pairs to check. The Hash-based technique is used to shrink that list of candidates before the computer even starts counting them.

အခြေခံ Apriori Algorithm ဟာ အရမ်းစနစ်ကျတယ်ဆိုပေမယ့်လည်း databaseအကြီးကြီးတွေနဲ့ တွေ့တဲ့အခါ စစ်ဆေးဖို့အတွက် ထွက်လာတဲ့ "Candidate (ခန့်မှန်းချက်)" နှစ်ခုတွဲအတွဲ အရေအတွက်ဟာ သန်းနဲ့ချီပြီး အလွန်အမင်း များပြားနေနိုင်ပါသေးတယ်။
ဒါကြောင့် Hash-based Technique ကို အသုံးပြုပြီး ကွန်ပျူတာက အဲဒီအတွဲတွေကို databaseထဲမှာ တကယ့်တကယ် လိုက်မရေတွက်ရသေးခင် (Before counting) ကတည်းက အဆိုပါ ခန့်မှန်းချက်စာရင်းကို အများကြီး သေးသွားအောင် ချုံ့ပစ်လိုက်တာ (Shrink) ဖြစ်ပါတယ်။

---

## How it Works:

**Look Ahead:** While the computer is scanning the database to count single items (finding L1), it performs an extra task: it looks at every transaction and creates all possible pairs (2-itemsets) from that transaction.

ကွန်ပျူတာဟာ ပထမအဆင့်မှာ ပစ္စည်းတစ်ခုချင်းစီကို ရေတွက်ဖို့အတွက် databaseကို ပတ်ဖတ်နေစဉ်မှာတင် (1st Scan ဖတ်နေတုန်းမှာတင်) အပိုအလုပ်တစ်ခုကိုပါ တစ်ပြိုင်နက်တည်း လုပ်ဆောင်ပါတယ်။ အဲဒါကတော့ ဝယ်ယူမှု (Transaction) တစ်ခုချင်းစီကို ကြည့်ပြီး ၎င်းထဲကနေ ထွက်လာနိုင်မယ့် ဖြစ်နိုင်ခြေရှိတဲ့ နှစ်ခုတွဲအတွဲ (2-itemsets) အားလုံးကို ကြိုတင်ပွားထုတ်လိုက်တာ ဖြစ်ပါတယ်။

**The "Bucket" System (Hashing):** Instead of keeping a giant list, the computer "hashes" (maps) these pairs into different buckets in a hash table.

ထွက်လာတဲ့ အတွဲတွေကို စာရင်းအကြီးကြီးအဖြစ် သိမ်းထားမယ့်အစား၊ ကွန်ပျူတာဟာ Hash Table ထဲက မတူညီတဲ့ Buckets (ခြင်းတောင်းလေးတွေ) ထဲကို သင်္ချာနည်းအရ လမ်းကြောင်းလွှဲပြီး ခွဲထည့်လိုက်ပါတယ်။

**The Filter:** Each time a pair is hashed into a bucket, the "bucket count" goes up.

အတွဲတစ်ခုစီကို သက်ဆိုင်ရာ Bucket ထဲ လှမ်းထည့်လိုက်တိုင်း အဲဒီ Bucket ရဲ့ အရေအတွက် (Bucket Count) ကို +1 ဆိုပြီး တိုးတိုးပေးသွားတာ ဖြစ်ပါတယ်။

**The Pruning Rule:** If a bucket's total count is lower than the minimum support threshold, the computer knows that none of the pairs inside that bucket can possibly be frequent.

databaseဖတ်လို့လည်း ပြီးရော တကယ်လို့ Bucket တစ်ခုရဲ့ စုစုပေါင်း အရေအတွက် (Total Count) ဟာ သတ်မှတ်ထားတဲ့ အနည်းဆုံးတန်ဖိုး (min_sup) ထက် နည်းနေရင်၊ ကွန်ပျူတာက ယုတ္တိဗေဒအရ "အဲဒီ ခြင်းတောင်း (Bucket) ထဲကို ရောက်သွားတဲ့ အတွဲတွေထဲက မည်သည့်အတွဲမှ လူဝယ်များတဲ့အတွဲ (Frequent) ဘယ်လိုမှ ဖြစ်မလာနိုင်တော့ဘူး" ဆိုတာကို ချက်ချင်း သတ်မှတ်လိုက်ပါတယ်။

**The Result:** By using this technique, the computer can ignore entire groups of pairs at once. This substantially reduces the number of candidate 2-itemsets (C2) that the computer has to examine in the next step.

ဒီနည်းပညာကို သုံးလိုက်ခြင်းအားဖြင့် ကွန်ပျူတာဟာ မဖြစ်နိုင်တဲ့ အတွဲတွေကို တစ်ခုချင်းစီ လိုက်စစ်မနေတော့ဘဲ အုပ်စုလိုက်ကြီး (Entire Groups) ကို တစ်ခါတည်း ဖြတ်ချ လိုက်နိုင်ပါတယ်။ ဒါဟာ နောက်တစ်ဆင့်မှာ ကွန်ပျူတာက အသေးစိတ် လိုက်စစ်ရမယ့် ဖြစ်နိုင်ခြေရှိတဲ့ နှစ်ခုတွဲကိုယ်စားလှယ်စာရင်း (C2 Candidates) ပမာဏကို သိသိသာသာကြီး လျှော့ချပေးသွားတာ ဖြစ်ပါတယ်။

---

## Slide 17: The Hash-Based Technique (Visual Example)

This slide provides a mathematical example of a Hash Table (H2) used for candidate 2-itemsets.

Candidate ၂ ခုတွဲအတွဲ (C2) တွေကို ဇကာတင်စစ်ထုတ်ဖို့အတွက် Hash Table (H2) ကို လက်တွေ့သင်္ချာနည်းအရ ဘယ်လို အသုံးပြုလဲဆိုတာကို ဥပမာပေး ရှင်းပြထားတာ ဖြစ်ပါတယ်။

**The Hash Function:** The computer uses a specific formula to decide which bucket a pair belongs to. In this example, the formula is:
h(x,y)=((order of x)×10+(order of y))(mod7).

ကွန်ပျူတာက ပစ္စည်းအတွဲတစ်ခုကို ဘယ်Bucket ထဲ ထည့်ရမလဲဆိုတာ ဆုံးဖြတ်ဖို့ အောက်ပါ ဖော်မြူလာကို သုံးပါတယ် 
h(x,y)=((order of x)×10+(order of y))(mod7).
**order of x နှင့် order of y:** ပစ္စည်းတွေရဲ့ အိုင်ဒီ ID နံပါတ် အစီအစဉ်ကို ပြောတာပါ။ (ဥပမာ - I1 ဆိုရင် order က 1 ဖြစ်ပြီး၊ I2 ဆိုရင် order က 2 ဖြစ်ပါတယ်)။
**mod 7 (Modulus 7) :** ရလာတဲ့ ရလဒ်ကိုမှ ၇ နဲ့ စားပြီး အကြွင်း (Remainder) ကို ယူတာ ဖြစ်ပါတယ်။ ဒါကြောင့် ထွက်လာမယ့် အဖြေ (bucketလိပ်စာ) ဟာ 0 ကနေ 6 အထိပဲ ရှိနိုင်တော့တာ ဖြစ်ပါတယ် 
**လက်တွေ့ တွက်ချက်ပုံ နမူနာ -**တကယ်လို့ အတွဲက {I1, I4} ဆိုပါစို့။ x = 1, y = 4 ဖြစ်တဲ့အတွက် -
(1) ဖော်မြူလာထဲ ထည့်တွက်မယ် -> (1 * 10) + 4 = 14
(2) အောက်ခြေ ၇ နဲ့ စားမယ် -> 14 div 7 = 2 ရပြီး အကြွင်းက 0 ဖြစ်ပါတယ်။
(3) ဒါကြောင့် {I1, I4} ဆိုတဲ့ အတွဲဟာ Bucket Address 0 ထဲကို ရောက်သွားတာ ဖြစ်ပါတယ်။

**The Table Structure:**

**Bucket Address:** The slots in the table (numbered 0 to 6).

0 ကနေ 6 အထိ ရှိတဲ့ အကန့်လေးတွေ ဖြစ်ပါတယ်။

**Bucket Contents:** The specific pairs (like {I1,I2} or {I2,I3}) that were assigned to that slot by the formula.

ဖော်မြူလာနဲ့ တွက်လို့ အဖြေတူပြီး တစ်အိုးတည်း လာစုနေတဲ့ ပစ္စည်းအတွဲတွေ ဖြစ်ပါတယ်။ (ဥပမာ - အတွဲ {I1, I4} ရော {I3, I5} ရောက တွက်လိုက်ရင် အကြွင်း 0 ထွက်လို့ Bucket 0 ထဲ အတူတူ ရောက်သွားကြတာမျိုးပါ)။

**Bucket Count:** How many times pairs landed in that specific slot.

အဲဒီအကန့်ထဲကို အတွဲတွေ ဘယ်နှခါ လာကျသလဲဆိုတဲ့ စုစုပေါင်း အကြိမ်ရေ ဖြစ်ပါတယ်။

**Decision Making:** If your threshold (minsup) was, for example, 3, the computer would look at Bucket 0 (which only has a count of 2) and immediately throw away the pairs {I1,I4} and {I3,I5} without even checking the main database for them.

ဥပမာ: အောင်မှတ် သတ်မှတ်ချက် min_sup = 3 လို့ ထားပါစို့။ (ဆိုလိုတာက ၃ ကြိမ်နှင့်အထက် ပါမှ အောင်မှာပါ)။
လက်တွေ့ စစ်ဆေးချက် : ကွန်ပျူတာက Bucket 0 ကို လှမ်းကြည့်တဲ့အခါ သူ့ရဲ့ စုစုပေါင်း Bucket Count က 2 ပဲ ရှိနေတာကို တွေ့ရပါတယ်။
ဖြတ်ချခြင်း (Pruning) : အောင်မှတ်က ၃ ဖြစ်ပြီး ဒီခြင်းတောင်းတစ်ခုလုံးရဲ့ Count က ၂ ပဲ ရှိတဲ့အတွက် ကွန်ပျူတာက ၎င်းခြင်းတောင်းထဲမှာ ရှိနေတဲ့ {I1, I4} ရော {I3, I5} အတွဲနှစ်ခုစလုံးကို မဖြစ်မနေ ရှုံးနိမ့်သူတွေအဖြစ် သတ်မှတ်ပြီး ချက်ချင်း လွှတ်ပစ် (Throw away) လိုက်ပါတယ်။

---

## Summary

Think of the Hash-based technique like sorting mail into cubby holes. Instead of the computer reading every single envelope one-by-one, it throws all the envelopes into 7 different boxes. If a box is nearly empty, the computer knows there aren't enough "popular" letters inside to bother opening them. This lets the computer focus only on the "heavy" boxes that actually have a chance of containing frequent patterns.


---

# Key notes from Tchel Hsu Myat Mo



