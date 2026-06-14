# The Problem of "Too Much" Information (slide 6 - 14.6.2026)

While finding patterns is the goal of data mining, this slide highlights a major technical hurdle: if we aren't careful, the computer will find so many patterns that it becomes impossible for a human to read them all.

Data miningရဲ့ ရည်မှန်းချက်က Patterns တွေ ရှာဖို့ဆိုပေမဲ့၊ စည်းကမ်းသတ်မှတ်ချက်တွေကို သေသေချာချာ မထိန်းချုပ်ထားဘူးဆိုရင် ကွန်ပျူတာကနေ လူသားတစ်ယောက်အနေနဲ့ လိုက်မဖတ်နိုင်လောက်အောင် ထောင်သောင်းချီတဲ့ စည်းမျဉ်းတွေ အများကြီး အဓိပ္ပာယ်မရှိ ထုတ်ပေးလာတတ်ပုံကို ရှင်းပြထားတာပါ။

---

## 1. The "Combinatorial Explosion"

**The Problem:** When the computer finds one long, frequent pattern, that pattern actually contains thousands or even billions of smaller "sub-patterns" inside it.

အကယ်၍ ငါတို့ရဲ့ Algorithm ကနေ ပစ္စည်းအများကြီး ပါဝင်တဲ့ ရှည်လျားတဲ့ Frequent Pattern ကြီးတစ်ခု (Long Frequent Pattern) ကို ရှာတွေ့ခဲ့တယ်ဆိုပါစို့။ အပြင်ပန်းကြည့်ရင် Pattern ၁ ခုတည်းလို့ ထင်ရပေမဲ့၊ ၎င်းရဲ့ အတွင်းပိုင်းမှာ ပေါင်းစပ်ဖန်တီးနိုင်တဲ့ "Sub-patterns (အစုခွဲငယ်လေးများ)" သန်းပေါင်း၊ ဘီလီယံပေါင်းများစွာ ကိန်းအောင်းနေပါတယ်။

**The Math:** If you find a pattern with 100 items (like a very large shopping list), that list contains 2 power 100 − 1 possible sub-combinations.

Item အရေအတွက် d ခုရှိတဲ့ အစုအဝေးတစ်ခုကနေ ထွက်လာနိုင်မယ့် ပေါင်းစပ်မှု (Subsets) စုစုပေါင်း ဖော်မြူလာကတော့ 2^d(2 power d) ဖြစ်ပါတယ်။ ဒါပေမဲ့ ဘာပစ္စည်းမှမပါတဲ့ အစုအလွတ် (Empty set) ၁ ခုကို ဖယ်ထုတ်ရမှာဖြစ်လို့ ဖြစ်နိုင်ခြေရှိတဲ့ ကာစတန်မာ တွဲဖက်ဝယ်ယူနိုင်ခြေ စုစုပေါင်းဟာ2^d - 1 (2 power d - 1) 

**Why it Matters:** This is a number with 30 zeros! A computer cannot list every single one of those combinations; it would take too much memory and time.

2^100(2 power 100) ဆိုတဲ့ ကိန်းဂဏန်းဟာ ဒသမကိန်းပြောင်းလိုက်ရင် အကြမ်းဖျင်း 
1.26 * 10^30 (ကိန်းဂဏန်းအနောက်မှာ သုည ၃၀ လုံး ပါဝင်တဲ့ အရေအတွက်) ဖြစ်တယ်။ ဒါဟာ စကြဝဠာထဲမှာရှိတဲ့ သဲပွင့်စုစုပေါင်းထက်တောင် ပိုမိုများပြားတဲ့ ပမာဏဖြစ်လို့ ဘယ်လောက်ပဲ စွမ်းဆောင်ရည်မြင့်တဲ့ Supercomputer ဖြစ်ပါစေ၊ Memory (RAM) ကော အချိန် (Time) ပါ မလုံလောက်ဘဲ စနစ်ကြီးတစ်ခုလုံး လုံးဝပြိုလဲသွားပါလိမ့်မယ်။

---

## 2. The Solution: Smarter Mining

To avoid being overwhelmed by billions of tiny patterns, we use a technique called "lossless compression". Instead of finding everything, we focus on two specific types of "representative" patterns:

သန်းပေါင်းများစွာသော Sub-patterns တွေကြားထဲမှာ နစ်မွန်းမသွားစေဖို့အတွက် ငါတို့က အောက်ပါ အုပ်စုကြီး ၂ ခုကိုပဲ ဦးတည်ပြီး ရှာဖွေရမှာဖြစ်တယ် -

**Closed Frequent Itemsets:**
- A pattern is "closed" if there is no larger version of it that happens just as often.

ပစ္စည်းအစုအဝေးတစ်ခုဟာ "Closed" ဖြစ်တယ်ဆိုတာ ၎င်းထက် ပိုကြီးတဲ့ အစုအဝေး (Super-set) တွေထဲမှာ ၎င်းကဲ့သို့ တူညီတဲ့ အကြိမ်ရေအထိ (Just as often) လိုက်ပါဖြစ်ပွားနိုင်ခြင်း မရှိတော့တဲ့ အခြေအနေကို ပြောတာပါ။

- It acts as a perfect summary because it tells you the frequency of all its sub-patterns without needing to list them individually.

 Closed Frequent Itemsets ကအကောင်းဆုံး ပြည့်စုံတဲ့ "Summary (အနှစ်ချုပ်)" ဖြစ်ပါတယ်။ ဘာဖြစ်လို့လဲဆိုတော့ Closed Itemset တစ်ခုရဲ့ ဖြစ်ပွားနှုန်း (Support Count) ကို သိရုံနဲ့၊ ၎င်းရဲ့ အတွင်းထဲမှာရှိတဲ့ Sub-patterns တွေအားလုံးကို တစ်ခုချင်းစီ လိုက်စာရင်းမထုတ်ဘဲ ၎င်းတို့ရဲ့ ဖြစ်ပွားနှုန်းကိုပါ အလိုအလျောက် တိကျစွာ သိရှိနိုင်လို့ ဖြစ်ပါတယ်။

**Maximal Frequent Itemsets (Max-Patterns):**
- This is the largest possible group of items that is still considered frequent.

Maximal Frequent Itemsetsသည် သတ်မှတ်ထားတဲ့ အနိမ့်ဆုံး စံနှုန်း (minsup) ကို ပြည့်မီနေသေးသမျှ ကာလပတ်လုံး ဖွဲ့စည်းနိုင်တဲ့ "အကြီးမားဆုံး Item အစုအဝေးကြီး" ဖြစ်ပါတယ်။

- No matter how hard you look, you won't find a bigger group that meets your "minimum support" threshold.

သူ့ထက် ပိုကြီးတဲ့ အစုအဝေးတစ်ခုကို ထပ်တိုးဖို့ ကြိုးစားရင် (minsup) သတ်မှတ်ချက်အောက်ကို ချက်ချင်း လျှောကျသွားမှာ ဖြစ်လို့၊ ဒါဟာ ရှာဖွေနိုင်သမျှထဲမှာ အစွန်ဆုံး နယ်နိမိတ် Boundary လို့ မှတ်ယူနိုင်ပါတယ်။

---

## Summary

Imagine you are a detective looking at a group of 100 suspects who always commit crimes together.

**The Problem:** If you try to write a separate report for every possible combination of those 100 people (e.g., Suspect A and B, Suspect A and C, etc.), you will end up with billions of reports.

**The Solution:** You write one report for the entire group of 100. This "Closed Pattern" tells you everything you need to know about the smaller groups without the extra paperwork.

---

# Key notes from Tchel Hsu Myat Mo

- Associationမရှာခင် ​frequent patternအရင်ရှာ။

- userသတ်မှတ်ထားတဲ့ threshold valueထက်ကျော်မှ frequent patternလို့သတ်မှတ်တယ်။

- Associationရှာမယ်ဆိုရင် Probabilityကိုစဉ်းစားရတယ်။

- ထွက်လာတဲ့ Associationတိုင်းက strongဖြစ်ချင်မှဖြစ်မယ်။

