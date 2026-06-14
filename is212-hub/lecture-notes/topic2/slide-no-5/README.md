# Introduction to Association Rule Mining (slide 5 - 14.6.2026)

This slide explains that finding rules and patterns in data is not done in one giant leap. Instead, it is a two-step process designed to make the search efficient and accurate.

Data Mining မှာ အလွန်အရေးပါတဲ့ Association Rule Mining (ဥပမာ - Apriori Algorithm) တွေဟာ database အကြီးကြီးတွေကို ကိုင်တွယ်တဲ့အခါ Computational Cost သက်သာစေဖို့အတွက် အောက်ပါအတိုင်း အဆင့် ၂ ဆင့် (Two-step process) နဲ့ အလုပ်လုပ်ကြတယ် -

---

## Step 1. Find All Frequent Itemsets

**The Goal:** The computer first looks for groups of items (itemsets) that appear together "frequently" in your data.

ဒေတာတွေထဲမှာ တစ်ခုချင်းစီတင်မကဘဲ အုပ်စုလိုက် (Itemsets အနေနဲ့) အမြဲတမ်းလိုလို တွဲပြီး ပါဝင်နေတတ်တဲ့ ပစ္စည်းအစုအဝေးတွေကို လိုက်ရှာတာ ဖြစ်ပါတယ်။ (ဥပမာ - {Bread, Milk, Butter} သည် အမြဲတွဲရောင်းရလေ့ရှိသော အစုအဝေးတစ်ခု ဖြစ်တယ်)။

**The Threshold (minsup):** We don't want to see every single random combination. We set a limit called minimum support count (minsup).

Databaseထဲမှာ မတော်တဆ ဒါမှမဟုတ် ကျပန်း (Random) အနေနဲ့ တစ်ခါတရံမှ တွဲပါလာတဲ့ အသုံးမဝင်တဲ့ ပေါင်းစပ်မှုတွေကို လိုက်မတွက်ချင်တဲ့အတွက် ငါတို့က ဖြတ်တောက်မယ့် အနိမ့်ဆုံးသတ်မှတ်ချက်လိုင်း Minimum Support Count (minsup) တစ်ခုကို ကြိုတင် ကန့်သတ်ပေးရတယ်။

**What it means:** For a group of items to be called "frequent," it must appear in the database at least as many times as the minsup number we decided on.

ပစ္စည်းအစုအဝေး (Itemset) တစ်ခုကို "Frequent (မကြာခဏ ဖြစ်ပွားတယ်)" လို့ သတ်မှတ် နိုင်ဖို့အတွက် အာ့အစုအဝေးဟာ databaseထဲမှာ ပါဝင်ဖြစ်ပွားခဲ့တဲ့ အကြိမ်အရေအတွက် (Support Count) သည် ကိုယ်သတ်မှတ်ထားတဲ့ minsup အရေအတွက်ထက် ကြီးလျှင် သို့မဟုတ် ညီမျှလျှင် သာ သတ်မှတ်တာ ဖြစ်တယ်။

---

## Step 2. Generate Strong Association Rules

**The Goal:** After finding the frequent groups, we turn them into "if-then" rules (for example: "If a customer buys Bread, they also buy Milk").

ရလာတဲ့ ပစ္စည်းအစုအဝေး(itemset) တွေကို "If A, then B" (A => B) ဆိုတဲ့ ဆက်စပ်မှုပုံစံ ပြောင်းလဲတာ ဖြစ်တယ်။ (ဥပမာ - "ဝယ်သူက ပေါင်မုန့်ဝယ်လျှင်၊ နို့ကိုပါ တွဲဖက်ဝယ်ယူတတ်သည်")။ဤနေရာတွင် A ကို Antecedent (ရှေ့ဖြစ်ရပ်) ဟုခေါ်ပြီး B ကို Consequent (နောက်ဆက်တွဲဖြစ်ရပ်) ဟု ခေါ်တယ်။

**The "Strong" Test:** A rule isn't useful just because it exists. To be considered a strong association rule, it must pass two specific tests:

**Minimum Support:** It must happen often enough to be significant.

**Minimum Confidence:** It must be reliable (meaning the second item is very likely to be there when the first one is).

ထွက်လာတဲ့ စည်းမျဉ်းတိုင်းက အသုံးဝင်နေတာ မဟုတ်ပါဘူး။ စည်းမျဉ်းတစ်ခုကို Strong Association Rule  လို့ သတ်မှတ်နိုင်ဖို့အတွက် သတ်မှတ်ချက် စံနှုန်း (၂) ခုစလုံးကို မဖြစ်မနေ တစ်ပြိုင်နက် တိုင်းတာရတယ် -

1. Minimum Support (minsup): ထိုစည်းမျဉ်းထဲက ပစ္စည်းအားလုံး (A ကော B ကော) တွဲလျက်သား ပါဝင်နှုန်းဟာ databaseတစ်ခုလုံးမှာ အရေးပါလောက်အောင် များပြားရပါမယ်။

2. Minimum Confidence (minconf): စည်းမျဉ်းရဲ့ ယုံကြည်စိတ်ချရမှုနှုန်း ဖြစ်ပါတယ်။ ဆိုလိုတာက ဝယ်သူက ရှေ့ပစ္စည်း (A) ကို ဝယ်ပြီးခါမှ နောက်ပစ္စည်း (B) ကိုပါ ထပ်မံဝယ်ယူဖို့ ဖြစ်နိုင်ခြေ ဘယ်လောက်အထိ သေချာသလဲဆိုတာကို တိုင်းတာတာ ဖြစ်တယ်။ (Conditional Probability သဘောတရား ဖြစ်တယ်)။

---

## Summary

Imagine you are a store manager looking at thousands of receipts:

Step 1 is like sorting through all the receipts to find which items are popular together (e.g., finding that many people buy Cereal and Milk at the same time).

Step 2 is deciding if that pattern is strong enough to act on—like moving the Milk next to the Cereal to make it easier for customers.

---

# Key notes from Tchel Hsu Myat Mo

- Associationမရှာခင် ​frequent patternအရင်ရှာ။

- userသတ်မှတ်ထားတဲ့ threshold valueထက်ကျော်မှ frequent patternလို့သတ်မှတ်တယ်။

- Associationရှာမယ်ဆိုရင် Probabilityကိုစဉ်းစားရတယ်။

- ထွက်လာတဲ့ Associationတိုင်းက strongဖြစ်ချင်မှဖြစ်မယ်။

