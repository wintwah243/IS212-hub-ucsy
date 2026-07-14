# A Pattern-Growth Approach (FP-growth) (slide 22 - 12.7.2026)

While the Apriori algorithm is great, it can be slow because it has to scan the database many times. The Frequent Pattern-growth (FP-growth) method was designed to be much faster by using a "divide-and-conquer" strategy.

basic Apriori Algorithm ဟာ အလွန်ကောင်းမွန်ပြီး စနစ်ကျတယ်ဆိုပေမယ့်လည်းသူဟာ လူကြိုက်များတဲ့ ပစ္စည်းအတွဲတွေကို ရှာဖွေဖို့အတွက် ဒေတာဘေ့စ်ကြီးကို အခါခါ အထပ်ထပ် scan ဖတ်ရတဲ့အတွက် အလုပ်လုပ်ပုံ နှေးကွေးနိုင်ပါတယ်။

ဒါကြောင့် FP-growth နည်းလမ်းကို Apriori ထက် အဆပေါင်းများစွာ ပိုမိုမြန်ဆန်သွက်လက်လာစေရန်အတွက် "Divide-and-Conquer" (ခွဲခြမ်းစိပ်ဖြာပြီး ဖြေရှင်းခြင်း) ဗျူဟာကို အသုံးပြုပြီး အထူးဒီဇိုင်းထွင် ဖန်တီးခဲ့တာ ဖြစ်ပါတယ်။

---

## 1. The Strategy: Divide and Conquer

Instead of guessing which items are popular and checking the whole database over and over, FP-growth breaks the big problem into many tiny, manageable pieces.

မည်သည့်ပစ္စည်းအတွဲတွေ လူကြိုက်များမလဲဆိုတာကို အလွတ်လိုက်ခန့်မှန်းပြီး databaseတစ်ခုလုံးကို အခါခါ လိုက်ဖတ်နေမယ့်အစား FP-growth ဟာ ပြဿနာအကြီးကြီးကို သေးငယ်ပြီး ကိုင်တွယ်ရလွယ်ကူတဲ့ အစိတ်အပိုင်းလေးတွေအဖြစ် စိပ်ဖြာခွဲထုတ်ပစ်လိုက်ပါတယ်။

**Step 1:** Database Compression: The computer takes the massive original database and "squashes" it into a special, compact structure called a Frequent Pattern Tree (FP-tree).

ကွန်ပျူတာဟာ အလွန်ကြီးမားလှတဲ့ မူရင်းdatabaseကြီးကို ယူပြီး ၎င်းကို ကျစ်လျစ်သိပ်သည်းတဲ့ အထူး Data Structure တစ်ခုဖြစ်တဲ့ Frequent Pattern Tree (FP-tree) အဖြစ် ပြောင်းလဲကာ ချုံ့ပစ်လိုက်ပါတယ်။

**The Benefit:** This tree is much smaller than the original database, but it still retains all the important information about which items were bought together.

ဒီလို ဆောက်လိုက်တဲ့ သစ်ပင်ပုံစံ (FP-tree) ဟာ မူရင်းdatabaseကြီးထက် ပမာဏအားဖြင့် အဆပေါင်းများစွာ ပိုမိုသေးငယ်သွားပေမယ့်လည်း မည်သည့်ပစ္စည်းတွေက ဘယ်လိုတွဲဝယ်သွားကြလဲဆိုတဲ့ အရေးကြီးတဲ့ အရောင်းအဝယ် သတင်းအချက်အလက် (Transaction Information) အားလုံးကိုတော့ အပြည့်အဝ ဆက်လက်ထိန်းသိမ်းထားနိုင်ဆဲ ဖြစ်ပါတယ်။

---

## 2. How the Mining Works

Once the data is compressed into the tree, the algorithm performs the following steps:

ဒေတာတွေကို သစ်ပင် (FP-Tree) ပုံစံအဖြစ် အပြည့်အဝ ချုံ့သိမ်းပြီးသွားပြီဆိုရင် Algorithm ဟာ အောက်ပါ အဆင့်တွေအတိုင်း ဒေတာတွေကို ရှာဖွေ (Mine) ပါတော့တယ်။

**Conditional Databases:** It divides the tree into several small conditional databases (also called projected databases).

သူက Memory ထဲက FP-Tree ကြီးကို သေးငယ်တဲ့ ကန့်သတ်ချက်ရှိသော databaseလေးတွေ (Conditional/Projected Databases) အဖြစ် အပိုင်းပိုင်း ထပ်မံခွဲခြမ်းစိပ်ဖြာလိုက်ပါတယ်။

**Focusing on Fragments:** Each of these small databases is associated with one specific frequent item or "pattern fragment".

ဒီလို ခွဲလိုက်တဲ့ databaseအသေးလေး တစ်ခုချင်းစီဟာ သတ်မှတ်ထားတဲ့ လူကြိုက်များပစ္စည်းတစ်ခု သို့မဟုတ် "ပစ္စည်းအတွဲ အစိတ်အပိုင်းလေးတစ်ခု (Pattern Fragment)" နဲ့ တိုက်ရိုက် ဆက်နွှယ် ချိတ်ဆက်နေပါတယ်။

**Recursive Search:** The computer then searches for shorter patterns within these tiny databases. It repeats this process over and over (recursively) and then joins the results together to find the final long patterns.

ကွန်ပျူတာဟာ အဆိုပါ သေးငယ်လွန်းတဲ့ databaseလေးတွေထဲမှာတင် ပိုမိုတိုတောင်းတဲ့ ပုံစံအတွဲတွေကို အထပ်ထပ်အခါခါ (Recursively - ရှေ့ကအဆင့်ကို နောက်အဆင့်က ပြန်ခေါ်ပြီး) လိုက်ရှာပါတယ်။ ပြီးတဲ့အခါမှ ရလာတဲ့ အဖြေအသေးလေးတွေကို ပြန်လည်ပေါင်းစပ်လိုက်ပြီး နောက်ဆုံး တကယ့်အရှည်ကြီးဖြစ်တဲ့ လူကြိုက်များပုံစံအတွဲ (Final Long Patterns) တွေကို ရှာဖွေတွေ့ရှိသွားတာ ဖြစ်ပါတယ်။

---

## 3. Why is it so efficient?

**Uses a Suffix:** It starts its search using the least frequent items first as a "suffix". This is a smart trick because it narrows down the possibilities very quickly (this is called "good selectivity").

သူက လူကြိုက်များတဲ့ အုပ်စုတွေကို ရှာဖွေတဲ့အခါ အရှေ့ကနေ မဟုတ်ဘဲ အနည်းဆုံး ရောင်းရတဲ့ ပစ္စည်းတွေ (Least frequent items) ကို "နောက်ဆက်တွဲ (Suffix)" အဖြစ် သတ်မှတ်ပြီး အောက်ခြေကနေ အထက်ကို ပြောင်းပြန် (Bottom-up) စတင် ရှာဖွေပါတယ်။ ဒါဟာ ဖြစ်နိုင်ခြေရှိတဲ့ လမ်းကြောင်း အရေအတွက်ကို အစကတည်းက အလွန်လျင်မြန်စွာ ကျဉ်းမြောင်းပစ်လိုက်နိုင်တဲ့ ပါးနပ်တဲ့ လှည့်ကွက်တစ်ခု ဖြစ်ပါတယ် (ဒါကို "Good Selectivity - ကောင်းမွန်သော စစ်ထုတ်ရွေးချယ်မှု" လို့ ခေါ်ပါတယ်)။

**Reduces Costs:** Because it only has to look at small, compressed pieces of data instead of the whole giant database, it substantially reduces the search costs and the work the computer has to do.

မူရင်း databaseကြီးတစ်ခုလုံးကို အစအဆုံး လိုက်ပတ်ဖတ်နေမယ့်အစား ချုံ့ထားတဲ့ သစ်ပင်ပုံစံ (FP-Tree) ထဲက သေးငယ်ကျစ်လျစ်တဲ့ ဒေတာအပိုင်းအစလေးတွေကိုပဲ ကွက်ပြီး ကြည့်ရတာ ဖြစ်လို့ကွန်ပျူတာနောက်ကွယ်မှာ တွက်ချက်ရမယ့် ရှာဖွေမှုစရိတ်စကတွေနဲ့ အလုပ်လုပ်ရမယ့် ပမာဏ (Search costs and CPU work) ကို သိသိသာသာကြီး လျှော့ချပေးနိုင်ခြင်း ဖြစ်ပါတယ်။

---

## Summary

If the Apriori method is like searching for a specific book by walking through every single aisle of a massive library, the FP-growth method is like creating a digital index (the FP-tree) first. Instead of walking through the library, you just look at the index to find the exact "aisle" (the conditional database) where your book is, making the search much faster and easier.


---

# Key notes from Tchel Hsu Myat Mo



