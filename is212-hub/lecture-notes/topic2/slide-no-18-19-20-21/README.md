# slide 18, 19, 20, 21 - 29.6.2026

# Slide 18: Transaction Reduction

The main goal here is to reduce the amount of data the computer has to read in every scan.

အဓိက goalကတော့ ကွန်ပျူတာက databaseကို အဆင့်တိုင်းမှာ တောက်လျှောက် ပတ်ဖတ်ရတဲ့အခါ (Every Scan) ဖတ်ရမယ့် ဒေတာပမာဏ (Transactions) ကြီးကို သေးသွားအောင်လျှော့ချပစ်ဖို့ ဖြစ်ပါတယ်။

**The Logic:** If a specific transaction (like a single receipt) does not contain any popular pairs of items, it definitely cannot contain a popular group of three or four items.

အကယ်၍ တကယ့် အရောင်းစာရင်းတစ်ခု (ဥပမာ - ဝယ်သူတစ်ယောက်ရဲ့ ပြေစာစာရင်း) ထဲမှာ အဆင့် ၂ တုန်းက အောင်မြင်ခဲ့တဲ့ လူကြိုက်များတဲ့ "နှစ်ခုတွဲအတွဲ (Frequent 2-itemsets)" တစ်တွဲမှ ပါမနေဘူးဆိုရင် ၎င်းစာရင်းထဲမှာ ၃ ခုတွဲ ဒါမှမဟုတ် ၄ ခုတွဲ အုပ်စုအကြီးကြီးတွေလည်း လုံးဝ ပါဝင်နေစရာ အကြောင်းမရှိပါဘူး။

**The Action:** Once the computer identifies a transaction that doesn't have any frequent patterns, it marks or removes it from future consideration.

ကွန်ပျူတာက လူကြိုက်များတဲ့ ပုံစံ/အတွဲတွေ လုံးဝမပါဝင်တော့တဲ့ အဆိုပါ အရောင်းစာရင်း (Transaction) ကို ရှာဖွေတွေ့ရှိတာနဲ့ ၎င်းကို အမှတ်အသားလုပ် (Mark) ထားလိုက်ပြီး နောက်ထပ် ဖတ်မယ့် အဆင့်တွေအတွက် စာရင်းထဲကနေ လုံးဝ ဖယ်ထုတ်ပစ်လိုက်ပါတယ်။

**The Benefit:** In later scans (for larger groups), the computer skips these "useless" transactions, which saves a lot of time.

အရှေ့ထက် ပိုကြီးတဲ့ ပစ္စည်းအုပ်စုတွေကို ထပ်ရှာမယ့် နောက်နောင် scanဖတ်မှုတွေ (Later Scans) မှာ ကွန်ပျူတာဟာ အဆိုပါ အသုံးမဝင်တော့တဲ့ "အလဟဿ" အရောင်းစာရင်းတွေကို လုံးဝ ကျော်လိုက်တဲ့အတွက် (Skips) ဒေတာဖတ်ရမယ့် အချိန်ကို အများကြီး သက်သာစေတာ ဖြစ်ပါတယ်။

---

# Slide 19: Partitioning

This technique follows a "divide and conquer" strategy to find frequent patterns in just two database scans.

ဒီနည်းပညာဟာ မူရင်းdatabaseကြီးကို ၂ ကြိမ်တည်းသာ scanဖတ်ပြီး (Just 2 database scans) လူကြိုက်များတဲ့ အုပ်စုတွေကို ရှာဖွေနိုင်ဖို့အတွက် "Divide and Conquer" (ခွဲခြမ်းစိပ်ဖြာပြီး ဖြေရှင်းခြင်း) ဗျူဟာကို အသုံးပြုထားတာ ဖြစ်ပါတယ်။

**Phase I (Local Search):**
-The database is divided into n smaller sections called partitions.
-The computer finds all the popular patterns inside each specific partition (these are called "local" frequent itemsets).

ပထမဆုံးအဆင့်မှာ ဒေတာဘေ့စ်ကြီး တစ်ခုလုံးကို Memory ထဲ တန်းတင်မနေတော့ဘဲ သေးငယ်တဲ့ အပိုင်း n ခု (Partitions) အဖြစ် စိပ်ဖြာခွဲထုတ်လိုက်ပါတယ်။
**လုပ်ဆောင်ချက်:** ကွန်ပျူတာဟာ ခွဲထားတဲ့ အပိုင်းလေးတစ်ခုချင်းစီထဲကိုပဲ သီးသန့်ဝင်ရောက်ပြီး ၎င်းအပိုင်းအလိုက် လူကြိုက်များတဲ့ ပစ္စည်းအတွဲတွေ (Local Frequent Itemsets) ကို ရှာဖွေပါတယ်။
**သင်္ချာလျှို့ဝှက်ချက်:** ဒီနေရာမှာ သုံးတဲ့ local thereshold ဟာ မူရင်း min_sup * Partition Size ဖြစ်ပါတယ်။
**ရလဒ်:** "တကယ်လို့ ပစ္စည်းအတွဲတစ်ခုဟာ databaseတစ်ခုလုံးမှာ တကယ်လူဝယ်များမယ့်item ဖြစ်ရင် သူဟာ အပိုင်း n ခုထဲက အနည်းဆုံး အပိုင်းတစ်ခုခုမှာတော့ မဖြစ်မနေ Local Frequent ဖြစ်နေရမယ်" ဆိုတဲ့ သီအိုရီအရ localတွင်းအောင်မြင်သူစာရင်းအဖြစ်သတ်မှတ်လိုက်တာ ဖြစ်ပါတယ်။

**Phase II (Global Search):**
-The computer combines all the local popular patterns from every section to create a list of "candidates" for the whole database.
-It then does one final scan to see which of these candidates are popular across the entire database (the "global" frequent itemsets).

ဒုတိယအဆင့်မှာတော့ အပိုင်းအားလုံးကနေ ထွက်လာတဲ့ ဒေသတွင်းအောင်မြင်သူ (Local Frequent) စာရင်းအားလုံးကို စုပေါင်း (Combine) လိုက်ပြီး ဒေတာဘေ့စ်တစ်ခုလုံးအတွက် Global Candidates (ကမ္ဘာလုံးဆိုင်ရာ ခန့်မှန်းချက်အတွဲများ) အဖြစ် သတ်မှတ်လိုက်ပါတယ်။
**လုပ်ဆောင်ချက်:** ရလာတဲ့ Candidate တွေကို ကိုင်ပြီး databaseကြီးတစ်ခုလုံးကို ဒုတိယအကြိမ် (နောက်ဆုံးအကြိမ်) အစအဆုံး ပတ်ဖတ် (Scan) လိုက်ပါတယ်။
**ရလဒ်:** ဒေတာဘေ့စ်တစ်ခုလုံးမှာ တကယ့် min_sup အောင်မှတ် ပြည့်မီသွားတဲ့ အတွဲတွေကို စစ်ထုတ်ပြီး Global Frequent Itemsets (နောက်ဆုံး တကယ့်လူကြိုက်အများဆုံး အုပ်စုများ) ကို အောင်မြင်စွာ ရရှိသွားတာ ဖြစ်ပါတယ်။

သာမန် Apriori ဆိုရင် ပစ္စည်းအုပ်စုက ၅ ခုတွဲအထိ ရှိရင် Database ကို ၅ ခေါက် ဖတ်ရမှာပါ။ ဒေတာပမာဏက Terabytes ချီများနေရင် ကွန်ပျူတာ မနိုင်တော့ပါဘူး။

ဒါပေမဲ့ Partitioning နည်းလမ်းကို သုံးလိုက်ရင် ဒေတာဘေ့စ်က ဘယ်လောက်ပဲ ကြီးကြီး၊ ပစ္စည်းအတွဲတွေ ဘယ်လောက်ပဲ အရှည်ကြီး ထွက်ထွက်... Database ကြီးကို ၂ ခေါက်တိတိပဲ ဖတ်ဖို့ လိုအပ်တော့တာ ဖြစ်ပါတယ်။ 
Scan ၁: Local Frequent တွေ ရှာပြီး Candidates စာရင်းစုဆောင်းရန်။

Scan ၂: ၎င်း Candidates တွေထဲက တကယ့် Global အောင်မြင်သူကို အတည်ပြုရန်။

---

# Slide 20: Sampling

Sometimes the database is so massive that looking at every single row is too slow. Sampling is a shortcut that prioritises speed.

တခါတရံမှာ databaseကြီးဟာ ဘယ်လောက်တောင် ကြီးမားကျယ်ပြန့်လဲဆိုရင် Row တစ်ခုချင်းစီကို လိုက်ဖတ်နေဖို့က အချိန်အလွန်အမင်း ကြာမြင့်တတ်ပါတယ်။ Sampling နည်းပညာကတော့ တိကျမှုထက် လုပ်ဆောင်ချက် မြန်ဆန်မှုကို အဓိက ဦးစားပေးတဲ့ ဖြတ်လမ်းနည်းတစ်ခု ဖြစ်ပါတယ်။

**The Strategy:** Instead of searching the whole database (D), the computer picks a random sample (S) and searches only that subset.

database တစ်ခုလုံး (D) ကို အစအဆုံး လိုက်ရှာမယ့်အစား ကွန်ပျူတာက ၎င်းထဲကနေ ကိုယ်စားပြုနိုင်မယ့် အစိတ်အပိုင်း အနည်းငယ်ကိုပဲ random စနစ်တကျ ရွေးထုတ်ပြီး နမူနာအုပ်စု (Sample - S) တစ်ခု ဆောက်လိုက်ပါတယ်။ ပြီးရင် အဲဒီ Sample S ထဲမှာပဲ လူကြိုက်များတဲ့အတွဲ (Frequent Itemsets) တွေကို လိုက်ရှာတော့တာ ဖြစ်ပါတယ်။

**The Trade-off:** You trade some accuracy for much higher efficiency.

ဒေတာ သဘာဝအတိုင်း ရလဒ် "တိကျမှု (Accuracy)" ကို အနည်းငယ် အနစ်နာခံပြီး၊ အလွန် မြင့်မားတဲ့ "မြန်ဆန်သွက်လက်မှု (Efficiency)" ကို ပြန်လည် ရယူလိုက်တာ ဖြစ်ပါတယ်။

**The Risk:** Because you aren't looking at everything, you might miss a few popular patterns that exist in the main database but weren't in your small sample.

ဒေတာအကုန်လုံးကို လိုက်မကြည့်တဲ့အတွက် တကယ့် မူရင်းdatabaseကြီးထဲမှာ လူဝယ်များနေပေမယ့် ကိုယ်ကောက်လိုက်တဲ့ နမူနာပုံစံအသေးလေးထဲမှာ မတော်တဆ ပါမလာခဲ့တဲ့ လူကြိုက်များအတွဲအချို့ (Frequent Patterns) ကို လွတ်သွားနိုင်ခြေ (Miss ဖြစ်သွားနိုင်ခြေ) ရှိပါတယ်။

**When to use it:** This is best for very complex tasks that need to be run frequently where "fast" is better than "perfect".

တွက်ချက်ရမယ့် အပိုင်းတွေက အရမ်းရှုပ်ထွေးနေပြီး နေ့တိုင်း ခဏခဏ Run ပေးနေရတဲ့ စနစ်မျိုးတွေမှာ သုံးဖို့ အကောင်းဆုံး ဖြစ်ပါတယ်။ ပြောရရင် "ပြီးပြည့်စုံနေဖို့ထက် ချက်ချင်း လက်ငင်း အမြန်ရဖို့က ပိုအရေးကြီးတဲ့ အခြေအနေမျိုး (Fast is better than perfect)" မှာ သုံးရတာ ဖြစ်ပါတယ်။

---

# Slide 21: Dynamic Itemset Counting

This is a more flexible way to count patterns compared to the standard Apriori method.

ဒါကတော့ ပုံမှန်အခြေခံ Apriori နည်းလမ်းနဲ့ ယှဉ်ရင် ပစ္စည်းအတွဲပုံစံ (Patterns) တွေကို ပိုမိုပြောင်းလွယ်ပြင်လွယ်ရှိတဲ့ နည်းလမ်းနဲ့ လိုက်လံရေတွက်တဲ့ စနစ်တစ်ခု ဖြစ်ပါတယ်။

**Standard Apriori:** The computer must finish a full scan of the database before it can start thinking about the next size of itemsets (e.g., it must finish counting all pairs before it starts counting groups of three).

ကွန်ပျူတာဟာ နောက်ထပ် အရွယ်အစား ပိုကြီးတဲ့ ပစ္စည်းအတွဲတွေအကြောင်းကို စတင်စဉ်းစားဖို့အတွက် အရှေ့က အဆင့်တစ်ခုလုံးရဲ့ databaseတစ်ခုလုံး ပတ်ဖတ်ခြင်း (Full Scan) ကြီး ပြီးဆုံးသွားတဲ့အထိ မဖြစ်မနေ စောင့်ရပါတယ်။ (ဥပမာ - နှစ်ခုတွဲအတွဲတွေ အားလုံးကို ဒေတာဘေ့စ်အစအဆုံး ဖတ်ပြီး ရေတွက်လို့ မပြီးမချင်း ၃ ခုတွဲအတွဲတွေကို လုံးဝ စတင်ရေတွက်ခွင့် မရှိပါဘူး)။

**Dynamic Counting:** This method allows the computer to add new candidates at any point during a scan.

ဒီနည်းလမ်းကတော့ databaseကို ဖတ်နေတဲ့ ဘယ်အချိန်၊ ဘယ်နေရာမှာမဆို (at any point during a scan) ကိုယ်စားလှယ်အတွဲသစ် (Candidates) တွေကို လိုအပ်သလို အချိန်မရွေး လှမ်းထည့်ပြီး တန်းစီရေတွက်ခွင့် ပေးလိုက်တာ ဖြစ်ပါတယ်။

**The Benefit:** It doesn't have to wait for a full scan to finish to start gathering data on new potential patterns, which can make the whole process move much faster.

အရွယ်အစား ပိုကြီးတဲ့ ဖြစ်နိုင်ခြေရှိတဲ့ အတွဲသစ်တွေအတွက် ဒေတာစုဆောင်းဖို့အတွက် databaseကြီး တစ်ခေါက်လုံး အပြီးဖတ်ရမှာကို စောင့်နေစရာ မလိုတော့ပါဘူး။ ဒါကြောင့် လုပ်ငန်းစဉ်တစ်ခုလုံးကို အများကြီး ပိုမိုမြန်ဆန် သွက်လက်သွားစေတာ ဖြစ်ပါတယ်။

---

## Summary

Think of these as four different ways to finish a giant chore faster:

**Transaction Reduction** is like throwing away the trash before you start deep-cleaning.

**Partitioning** is like splitting a big room into small zones and cleaning each zone one by one.

**Sampling** is like just cleaning the visible parts of the room because you're in a huge hurry.

**Dynamic Counting** is like starting to polish the furniture while you are still dusting, instead of waiting to finish all the dusting first.

---

# Key notes from Tchel Hsu Myat Mo



