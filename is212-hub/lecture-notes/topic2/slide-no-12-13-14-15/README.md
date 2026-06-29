# Slides 12 & 13: Implementation of Apriori (15 - 28.6.2026)

These slides explain the "behind-the-scenes" mechanics of how the computer generates its guesses (candidates) for popular groups of items.

ကွန်ပျူတာတစ်လုံးဟာ လူကြိုက်များနိုင်မယ့် ပစ္စည်းအုပ်စုအသစ်တွေ (Candidates) ကို နောက်ကွယ်မှာ ဘယ်လိုနည်းလမ်းတွေနဲ့ ခန့်မှန်းချက်စာရင်း(guess and test method) ထုတ်ပြီး ဖန်တီးလဲဆိုတဲ့ အသေးစိတ် လုပ်ဆောင်ပုံ တွေကို ရှင်းပြထားတာ ဖြစ်တယ်။

---

## Generating Candidates (The 2-Step Process)

To find larger groups without checking every single possibility, the computer uses two smart steps:

ဖြစ်နိုင်ခြေရှိတဲ့ အုပ်စုသေးသေးလေးတွေကို လိုက်ရှာမနေဘဲ အရွယ်အစား ပိုကြီးတဲ့ ပစ္စည်းအုပ်စုတွေကို ရှာဖွေနိုင်ဖို့အတွက် ကွန်ပျူတာဟာ အောက်ပါအဆင့် ၂ ဆင့်ကို အသုံးပြုတယ်။

**Step 1: Self-Joining (Lk):** The computer takes the list of popular groups of a certain size (like 3 items) and joins them together to make a "guess" for a group of the next size up (4 items).
**Example:** If {a,b,c} and {a,b,d} are both popular, the computer joins them to create a candidate for {a,b,c,d}.

ကွန်ပျူတာဟာ သတ်မှတ်ထားတဲ့ အရွယ်အစားတစ်ခု (ဥပမာ - ၃ ခုတွဲ) မှာ လူကြိုက်များခဲ့တဲ့ ပစ္စည်းအုပ်စုစာရင်းတွေကို ယူပြီး ၎င်းတို့အချင်းချင်း ပြန်ပေါင်းစပ်လိုက်တယ်။ ရည်ရွယ်ချက်ကတော့ ၎င်းထက် အရွယ်အစား တစ်ဆင့်ပိုကြီးတဲ့ (၄ ခုတွဲ) အုပ်စုအတွက် "ခန့်မှန်းချက် (Guess)" တစ်ခု ထုတ်ဖို့ ဖြစ်တယ်။

ဥပမာ: အကယ်၍ {a, b, c} နဲ့ {a, b, d} နှစ်ခုစလုံးဟာ လူကြိုက်များခဲ့ရင် (Frequent ဖြစ်ခဲ့ရင်)၊ ကွန်ပျူတာက သူတို့ကို ပေါင်းစပ်ပြီး {a, b, c, d} ဆိုတဲ့ Candidate ၄ ခုတွဲအသစ်ကို ဖန်တီးလိုက်တာ ဖြစ်ပါတယ်။

**Step 2: Pruning:** This is the "shortcut" step. The computer checks the new guess and asks: "Are all the smaller parts of this group also popular?".
**Example:** If it guesses {a,c,d,e}, it checks if the smaller group {a,d,e} is on its "popular" list. If {a,d,e} is not on the list, the computer immediately deletes (prunes) the guess {a,c,d,e} because the Apriori Property says it cannot possibly be popular.

ဒါကတော့ အလုပ်မြန်စေမယ့် ဖြတ်လမ်း (Shortcut) အဆင့် ဖြစ်ပါတယ်။ ကွန်ပျူတာက အသစ်ရလာတဲ့ ခန့်မှန်းချက်ကို ကြည့်ပြီး "ဒီအုပ်စုကြီးရဲ့ အစိတ်အပိုင်း အသေးလေးတွေ အားလုံးကော လူကြိုက်များစာရင်းထဲမှာ ပါခဲ့ရဲ့လား" ဆိုပြီး မေးခွန်းထုတ် စစ်ဆေးပါတယ်။

ဥပမာ: တကယ်လို့ ကွန်ပျူတာက {a, c, d, e} ဆိုပြီး ၄ ခုတွဲကို ခန့်မှန်းလိုက်တယ်ဆိုပါစို့။ သူက သူ့ထက်ငယ်တဲ့ ၃ ခုတွဲ ဖြစ်တဲ့ {a, d, e} လေးဟာ အရှေ့က လူကြိုက်များတဲ့စာရင်း (Frequent List) ထဲမှာ ရှိမရှိ လှမ်းစစ်ပါတယ်။ တကယ်လို့ {a, d, e} က စာရင်းထဲမှာ မရှိဘူး (လူဝယ်နည်းခဲ့တယ်) ဆိုရင် ကွန်ပျူတာက {a, c, d, e} ၄ ခုတွဲကြီးကို ချက်ချင်း ဖျက်ပစ် (Prune လုပ်) လိုက်ပါတယ်။ ဘာကြောင့်လဲဆိုတော့ Apriori Property စည်းမျဉ်းအရ အသေးလေးတောင် လူဝယ်နည်းရင် အုပ်စုအကြီးကြီးဟာလည်း ဘယ်လိုမှ လူကြိုက်များလာစရာ အကြောင်းမရှိလို့ ဖြစ်ပါတယ်။

---

## The Algorithm Loop

The algorithm is an iterative process, meaning it repeats a cycle:

ဒီ Algorithm ဟာ အဆင့်ဆင့် တောက်လျှောက် (စက်ဝိုင်းလိုမျိုး) ထပ်ခါထပ်ခါ လုပ်ဆောင်ရတဲ့ ပတ်လမ်းစဉ် (Iterative Process) တစ်ခု ဖြစ်ပါတယ်။

**Input:** It takes the database (D) and your minimum popularity threshold (min_sup).

သူက အလုပ်လုပ်ဖို့အတွက် မူရင်းdatabase(D) နဲ့ သင်သတ်မှတ်ပေးလိုက်တဲ့ အနည်းဆုံး လူကြိုက်များမှုနှုန်း သတ်မှတ်ချက် (min_sup) တို့ကို Input အနေနဲ့ ယူပါတယ်။

**Scan:** It scans the database to find popular single items.

အစောဆုံးအဆင့်မှာ databaseကို အစအဆုံး ပတ်ဖတ်ပြီး လူကြိုက်များတဲ့ ပစ္စည်းတစ်ခုချင်းစီ (Popular Single Items) ကို ရှာဖွေပါတယ်။

**Iterate:** It uses those items to generate candidates for pairs, scans the database to count them, and keeps only the popular ones.

ရလာတဲ့ ပစ္စည်းတစ်ခုချင်းစီကို အခြေခံပြီး နှစ်ခုတွဲအတွဲတွေ (Pairs) ဖြစ်နိုင်မယ့် Candidates တွေကို ဆောက်တယ်၊ databaseကို ထပ်ဖတ်ပြီး အရေအတွက် လိုက်ရေတွက်တယ်၊ ပြီးတော့မှ သတ်မှတ်ချက်ပြည့်မီတဲ့ လူကြိုက်များတဲ့ အတွဲတွေကိုပဲ ချန်ထားခဲ့ပါတယ်။

**Repeat:** It continues this "guess, scan, and keep" cycle for groups of 3, 4, and so on until no more popular groups can be found.

ဒီ "ခန့်မှန်း (Guess)၊ database scanဖတ် (Scan)၊ လူကြိုက်များတာပဲချန် (Keep)" ဆိုတဲ့ သုံးဆင့်ပတ်လမ်းကို ၃ ခုတွဲ၊ ၄ ခုတွဲ စသဖြင့်... လူကြိုက်များတဲ့အတွဲ ထပ်ရှာလို့မရတော့တဲ့အထိ အထပ်ထပ်အခါခါ ဆက်လုပ်သွားတာ ဖြစ်ပါတယ်။

---

# Slides 14 & 15: The Apriori Algorithm—An Example

These slides walk through a practical scenario to show exactly how the math and the scans work.

ဒီslideတွေကတော့ Apriori ရှာဖွေမှုမှာ နောက်ကွယ်က သင်္ချာတွက်ချက်မှုတွေနဲ့ databaseကို ပတ်ဖတ်ခြင်း (Scans) တွေ အမှန်တကယ် ဘယ်လို အလုပ်လုပ်သွားလဲဆိုတာကို လက်တွေ့ scenario တစ်ခုနဲ့ တဆင့်ချင်းစီ လုပ်ပြထားတာ ဖြစ်ပါတယ်။

---

## Example 1: The A, B, C, D, E Database (Slide 14)

Imagine a shop with only 4 sales (Tids) and a threshold where an item must appear at least 2 times to be "frequent" (min_sup=2).

ဆိုင်တစ်ဆိုင်မှာ အရောင်းစာရင်း (Transactions) စုစုပေါင်း ၄ ခု ပဲ ရှိပြီး၊ ပစ္စည်းတွေကို လူဝယ်များတယ်လို့ သတ်မှတ်ဖို့အတွက် အနည်းဆုံး ၂ ကြိမ် ပါဝင်ရမယ်လို့ စည်းကမ်းသတ်မှတ်ထားပါတယ်

**1st Scan:** We count how many times each item appeared. Item {D} only appeared once, so we discard it. Our popular singles (L1) are {A}, {B}, {C}, and {E}.

ပထမဆုံး ဆိုင်ထဲမှာရှိတဲ့ ပစ္စည်းတစ်ခုချင်းစီကို လူဘယ်နှယောက် ဝယ်သွားလဲ လိုက်ရေတွက်ပြီး C1 ဇယား ဆောက်ပါတယ်။ရေတွက်ချက် (C1): {A: 2, B: 3, C: 3, D: 1, E: 3} ခန့်မှန်းရရှိပါတယ်။သတ်မှတ်ချက်နဲ့ တိုက်စစ်ခြင်း: ပစ္စည်း {D} ဟာ ၁ ကြိမ်ပဲ ပါတဲ့အတွက် သတ်မှတ်ချက် min_sup = 2 အောက် ရောက်နေလို့ ၎င်းကို ဖျက်ချ (Discard) လိုက်ပါတယ်။အောင်မြင်သူများစာရင်း (L1): လူဝယ်များတဲ့ ၁ ခုတွဲစာရင်းအဖြစ် {A}, {B}, {C}, {E} တို့ ကျန်ခဲ့ပါတယ်။

**2nd Scan:** We create pairs using our popular singles. After checking the 4 sales, we find that pairs like {A, B} only appeared once, so they are dropped. Our popular pairs (L2) are {A, C}, {B, C}, {B, E}, and {C, E}.

ကျန်ခဲ့တဲ့ L1 ထဲက ပစ္စည်းတွေကို သုံးပြီး နှစ်ခုတွဲ C2 Candidates (ခန့်မှန်းချက်အတွဲများ) ဆောက်ပါတယ်။ (ဥပမာ - {A,B}, {A,C}, {A,E}, {B,C}, {B,E}, {C,E})။ ပြီးရင် databaseကို ဒုတိယအကြိမ် ပြန်ပတ်ဖတ်ပြီး အရေအတွက် လိုက်ရေတွက်ပါတယ်။သတ်မှတ်ချက်နဲ့ တိုက်စစ်ခြင်း: စစ်လိုက်တဲ့အခါ {A, B} ကဲ့သို့သော အတွဲအချို့ဟာ ၁ ကြိမ်ပဲ တွဲပါတာမို့လို့ min_sup မပြည့်လို့ ဖြတ်ချခံရပါတယ်။အောင်မြင်သူများစာရင်း (L2): သတ်မှတ်ချက် ၂ ကြိမ်နှင့်အထက် ပြည့်မီသွားတဲ့ နှစ်ခုတွဲစာရင်းအဖြစ် {A, C}, {B, C}, {B, E}, {C, E} ၄ တွဲပဲ အောင်မြင်ပြီး ကျန်ရစ်ပါတယ်။

**3rd Scan:** We try to make a group of three. The computer guesses {B, C, E}. After scanning the sales, it finds this group appeared twice, so it is a final frequent itemset.

အခု အောင်မြင်ထားတဲ့ L2 ထဲကအတွဲတွေကို သုံးပြီး ၃ ခုတွဲ ဆောက်ဖို့ ကြိုးစားပါတယ်။အရှေ့မှာ သင်ခဲ့တဲ့ Join Step အရ {B, C} နဲ့ {B, E} ကို ကြည့်ရင် အရှေ့စာလုံး B ချင်း တူတဲ့အတွက် ပေါင်းစပ်ပြီး {B, C, E} ဆိုတဲ့ ၃ ခုတွဲ Candidate (C3) ကို ရရှိပါတယ်။ databaseကို တတိယအကြိမ် ဖတ်ပြီး ရေတွက်တဲ့အခါ ဒီ ၃ ခုတွဲကြီးဟာ အရောင်းစာရင်း ၄ ခုထဲမှာ ၂ ကြိမ်တိတိ တွဲလျက်သား ပါဝင်နေတာကို တွေ့ရပါတယ်။အောင်မြင်သူများစာရင်း (L3): သတ်မှတ်ချက် ၂ ကြိမ်နဲ့ ကွက်တိပြည့်စုံတဲ့အတွက် {B, C, E} ဟာ နောက်ဆုံးအဆင့် သတ်မှတ်ချက်ပြည့်မီတဲ့ မဖြစ်မနေမှတ်သားရမယ့် Frequent Itemset (လူကြိုက်အများဆုံး အုပ်စု) အဖြစ် ထွက်ပေါ်လာတာ ဖြစ်ပါတယ်။

---

## Example 2: AllElectronics Transactions (Slide 15)

This slide shows a larger version of the process using 9 transactions (T100 to T900) at an electronics branch.

ဒီslideကတော့ လျှပ်စစ်ပစ္စည်းအရောင်းဆိုင်ခွဲတစ်ခုရဲ့ အရောင်းစာရင်း စုစုပေါင်း ၉ ခု (T100 မှ T900 အထိ) ကို အသုံးပြုပြီး ပိုမိုကြီးမားတဲ့ အဆင့်လိုက် တွက်ချက်ပုံ လုပ်ငန်းစဉ်ကို ပြသထားတာ ဖြစ်ပါတယ်။

**Counting Singles (C1→L1):** Items I1 through I5 are all counted. Because they all meet the popularity threshold, they all move into the "frequent" list (L1).

ဆိုင်မှာ ရောင်းရတဲ့ ပစ္စည်း ၅ မျိုး ရှိပါတယ် (I1 မှ I5 အထိ)။ ၎င်းတို့ကို databaseထဲမှာ တစ်ခုချင်းစီ လိုက်ရေတွက်ပါတယ်။ရလဒ်အနေနဲ့ ပစ္စည်း၅ မျိုးလုံးဟာ ပုစ္ဆာက သတ်မှတ်ထားတဲ့ အနည်းဆုံးလူကြိုက်များမှုနှုန်း (min_sup) သတ်မှတ်ချက်ကို အောင်အောင်မြင်မြင် ကျော်ဖြတ်နိုင်ခဲ့ပါတယ်။ရလဒ်စာရင်း (L1): ဒါကြောင့် ပစ္စည်း ၅ ခုလုံးဖြစ်တဲ့ {I1}, {I2}, {I3}, {I4}, {I5} အားလုံးဟာ လူဝယ်များတဲ့ အဆင့် ၁ စာရင်းထဲကို တန်းတက်သွားပါတယ်။

**Creating Pairs (C2→L2):** Many pairs are generated (like {I1, I2} or {I3, I4}). The computer scans the 9 transactions to count them. Only those that appeared enough times stay on the list.

အောင်မြင်သွားတဲ့ ပစ္စည်း ၅ ခုကို သုံးပြီး ဖြစ်နိုင်ခြေရှိတဲ့ နှစ်ခုတွဲ C2 Candidates တွေ (ဥပမာ - {I1, I2}, {I1, I3}, ..., {I4, I5}) ကို ပွားထုတ်လိုက်ပါတယ်။ဒေတာပတ်ဖတ်ခြင်း: ကွန်ပျူတာက အရောင်းစာရင်း ၉ ခုစလုံး (T100 to T900) ကို ဒုတိယအကြိမ် ပြန်ပတ်ဖတ်ပြီး အဆိုပါ အတွဲတွေ ဘယ်နှခါ တွဲပါလဲ လိုက်ရေတွက်ပါတယ်။ရလဒ်စာရင်း (L2): သတ်မှတ်ချက် ပြည့်မီအောင် ဝယ်သူမရှိတဲ့ အတွဲအချို့ (ဥပမာ - အရမ်းရောင်းရခက်တဲ့ တွဲဖက်မှုတွေ) ပြုတ်ကျန်ခဲ့ပြီး၊ တကယ် လူဝယ်များတဲ့ နှစ်ခုတွဲတွေပဲ အရည်အချင်းစစ်အောင်ပြီး L2 စာရင်းထဲ ကျန်ရစ်ပါတယ်။

**Final Discovery (C3→L3):** Using the popular pairs, the computer guesses groups of three. After the pruning step, it checks the database and discovers that {I1, I2, I3} and {I1, I2, I5} are the final, most popular groups in the shop.

အောင်မြင်ခဲ့တဲ့ L2 ထဲက အတွဲတွေကို သုံးပြီး ၃ ခုတွဲ ဖြစ်နိုင်ခြေစာရင်းကို "Join" လုပ်ပြီး ဆောက်ပါတယ်။ ဖြတ်ချခြင်း (Pruning): databaseထဲ သွားမစစ်ခင်၊ ၃ ခုတွဲတွေရဲ့ Subset အသေးလေးတွေထဲမှာ အဆင့် ၂ တုန်းက ရှုံးနိမ့်ခဲ့တဲ့အတွဲ ပါနေလားလို့ အရင်စစ်ပြီး ပါရင် ချက်ချင်း ဖြတ်ချ (Prune) ပစ်ပါတယ်။နောက်ဆုံးရလဒ် (L3): လက်ကျန် ကောင်တွေကို databaseထဲမှာ သွားရေတွက်လိုက်တဲ့အခါ တကယ့် AllElectronics ဆိုင်ရဲ့ လူကြိုက်အများဆုံး ၃ ခုတွဲ အုပ်စုကြီး ၂ စုကို အောင်မြင်စွာ ရှာဖွေတွေ့ရှိသွားပါတယ်။ အဲဒါတွေကတော့ -{I1, I2, I3}{I1, I2, I5}

---

## Summary

These slides show that instead of searching for everything at once, the computer starts small (singles), moves to medium (pairs), and finally large groups. By using the Pruning step, it saves time by never searching for a large group if its smaller parts aren't already popular.

---

# Key notes from Tchel Hsu Myat Mo


