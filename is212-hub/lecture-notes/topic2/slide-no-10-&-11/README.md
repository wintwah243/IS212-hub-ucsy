# The Apriori Algorithm (slide 9 - 15.6.2026)

The Apriori Algorithm is a classic and foundational method in data mining. It was first proposed by R. Agrawal and R. Srikanth in 1994.

**The Name:** Its name comes from the fact that the algorithm uses prior knowledge (information we already have) about the properties of frequent itemsets to find new patterns.

**The Strategy:** It uses an iterative, level-wise search. This means it finds popular individual items first, then uses those to find popular pairs, then uses the pairs to find groups of three, and so on.

သူက အထပ်ထပ်အခါခါ ရှာဖွေတဲ့ အဆင့်လိုက်နည်းလမ်း (Iterative, Level-wise search) ကို သုံးတယ်။ ဆိုလိုတာက လူကြိုက်အများဆုံး (ဝယ်အများဆုံး) ပစ္စည်း တစ်ခုချင်းစီကို အရင်ရှာတယ်၊ ပြီးမှ အဲဒီအပေါ် အခြေခံပြီး လူကြိုက်များတဲ့ နှစ်ခုတွဲအတွဲတွေကို ဆက်ရှာတယ်၊ ပြီးမှ အဲဒီနှစ်ခုတွဲတွေအပေါ် အခြေခံပြီး သုံးခုတွဲအတွဲတွေကို ဆက်ရှာတယ်၊ စသဖြင့် အဆင့်ဆင့် လုပ်ဆောင်သွားတာ ဖြစ်တယ်။

**The Apriori Property:** This is the most important rule of the algorithm. It states: "All nonempty subsets of a frequent itemset must also be frequent".
In plain English: If a big group is popular, then every smaller part of that group must also be popular.

လူဝယ်များတဲ့ ပစ္စည်းအတွဲတစ်ခုရဲ့ မည်သည့် ပစ္စည်းစုခွဲ (Subset) မဆိုဟာလည်း မဖြစ်မနေ လူဝယ်များနေရမှာ ဖြစ်တယ်။

ဉပမာ- ပစ္စည်းအုပ်စုအကြီးကြီးတစ်ခုက လူကြိုက်များတယ် (လူဝယ်များတယ်) ဆိုရင်၊ အဲဒီအုပ်စုထဲက ခွဲထုတ်လိုက်တဲ့ ပစ္စည်းအသေးစုလေးတွေ အားလုံးဟာလည်း လူကြိုက်များ (လူဝယ်များ) နေရပါမယ်။

---

# The Apriori Method (The Steps)

This slide explains the actual "recipe" the computer follows to perform an Apriori search efficiently.

**The 3-Step Method:**

**Initial Scan:** The computer scans the database once to find all the frequent 1-itemsets (individual items that meet your minimum popularity threshold).

ကွန်ပျူတာက databaseကို အစအဆုံး တစ်ခေါက် အရင်ဆုံး ပတ်ဖတ်ပါတယ်။ ရည်ရွယ်ချက်ကတော့ userသတ်မှတ်ထားတဲ့ အနည်းဆုံးလူကြိုက်များမှုနှုန်း (Minimum Popularity Threshold - min_sup) ပြည့်မီတဲ့ ပစ္စည်းတစ်ခုချင်းစီအတွဲ (Frequent 1-itemsets) အားလုံးကို ရှာဖွေဖို့ ဖြစ်တယ်။

**Level-by-Level Generation:** It generates larger "candidate" groups of size (k+1) by using the frequent groups found at size k. (For example, it uses popular pairs to guess which groups of three might be popular).

ရရှိလာတဲ့ အရွယ်အစား k ရှိတဲ့ လူကြိုက်များတဲ့ အုပ်စုတွေကို အခြေခံပြီး၊ ၎င်းထက် အရွယ်အစား တစ်ဆင့်ကြီးတဲ့ အရွယ်အစား k+1 ရှိတဲ့ ဖြစ်နိုင်ခြေရှိတဲ့ အုပ်စုအသစ်တွေကို ထပ်မံဖန်တီးပါတယ်။ (ဥပမာ - လူကြိုက်များတဲ့ ၂ ခုတွဲအတွဲတွေကို သုံးပြီး ဘယ်လို ၃ ခုတွဲအတွဲတွေ လူကြိုက်များနိုင်မလဲဆိုတာကို ခန့်မှန်းတာမျိုးပါ)။

**Termination:** The process keeps going until the computer can no longer generate any more candidates or frequent sets.

ဒီလုပ်ငန်းစဉ်ကို ကွန်ပျူတာကနေ လူကြိုက်များတဲ့အတွဲ (Frequent Sets) တွေ ထပ်မံ မဆောက်နိုင်တော့တဲ့ အခြေအနေ ရောက်တဲ့အထိ အထပ်ထပ်အခါခါ ဆက်လုပ်သွားပြီး အဆုံးသတ်ပါတယ်။

**Why the "Apriori Property" is a Life-Saver:** Checking every possible combination in a huge database is impossible. The Apriori property is used to reduce the search space, making the process much faster.

**The "Pruning" Logic:** If the computer finds that a small group is not frequent, it knows immediately that any larger group containing it will never be frequent. It can "prune" (ignore) those larger groups entirely without even looking at them.

တကယ်လို့ ကွန်ပျူတာက ပစ္စည်းအတွဲအသေးလေးတစ်ခုဟာ လူကြိုက်မများဘူး (min_supမပြည့်ဘူး) လို့ သိလိုက်ရတာနဲ့ ၎င်းပစ္စည်းအတွဲ ပါဝင်နေမယ့် မည်သည့်အုပ်စုအကြီးကြီးမဆိုဟာလည်း ဘယ်တော့မှ လူကြိုက်များလာမှာ မဟုတ်ဘူး ဆိုတာကို ချက်ချင်း ကောက်ချက်ချလိုက်ပါတယ်။ဒါကြောင့် အဆိုပါ အုပ်စုအကြီးကြီးတွေကို တကယ့်ဒေတာဘေ့စ်ထဲမှာ သွားပြီး ပင်ပန်းခံ လိုက်ရှာမနေတော့ဘဲ"Prune" (ဖြတ်ချ) ပစ်လိုက်ပါတယ်။

**Example:** If the group {Beer, Diaper, Nuts} is frequent, then the smaller group {Beer, Diaper} must also be frequent. If {Beer, Diaper} was not popular, the computer would have never even bothered to check {Beer, Diaper, Nuts}.

---

## Summary

The Apriori Algorithm is like building a tower of blocks. You can only place a block on the second level if there are stable blocks on the first level to support it. By checking the "subsets" first, the algorithm ensures it only spends time looking at combinations that have a real chance of being popular.

---

# Key notes from Tchel Hsu Myat Mo



