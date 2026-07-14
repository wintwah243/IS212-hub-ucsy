# A Misleading “Strong” Association Rule (slide 25,26,27 - 12.7.2026)

This slide introduces a critical warning: High confidence does not always mean a rule is useful. Sometimes, a rule can pass all our "strength" tests (minimum support and confidence) but still be completely misleading.

ဒီslideကတော့ အလွန်အရေးကြီးတဲ့ သတိပေးချက် တစ်ခုကို ချပြထားတာ ဖြစ်ပါတယ် - Confidence နှုန်း မြင့်မားနေခြင်းဟာ အဆိုပါ စည်းမျဉ်းက တကယ်အသုံးဝင်နေတာကို အမြဲတမ်း ဆိုလိုခြင်း မဟုတ်ပါဘူး။

---

## 1. The Trap: The Case of Games and Videos

To understand why a rule can be misleading, the sources provide a case study of 10,000 shopping transactions at a store:

ဆက်စပ်မှုစည်းမျဉ်းတစ်ခုက လူကို ဘယ်လို လမ်းမှားရောက်စေနိုင်လဲ (Misleading ဖြစ်စေနိုင်လဲ) ဆိုတာကို နားလည်စေဖို့အတွက် အရင်းအမြစ်တွေကနေ ဆိုင်တစ်ဆိုင်ရဲ့ အရောင်းပြေစာမှတ်တမ်း စုစုပေါင်း ၁၀,၀၀၀ (10,000 Transactions) ကို အသုံးပြုပြီး လက်တွေ့လေ့လာမှု တစ်ခုကို ချပြထားပါတယ် -

**Total Customers:** 10,000.

ဝယ်သူစုစုပေါင်း: ၁၀,၀၀၀ ယောက်

**Bought Computer Games:** 6,000 (60% of all shoppers).

ကွန်ပျူတာဂိမ်း ဝယ်သူ: ၆,၀၀၀ ယောက် (ဝယ်သူအားလုံးရဲ့ 60%)

**Bought Videos:** 7,500 (75% of all shoppers).

ဗီဒီယိုခွေ ဝယ်သူ: ၇,၅၀၀ ယောက် (ဝယ်သူအားလုံးရဲ့ 75%)

**Bought Both:** 4,000 (40% of all shoppers).

နှစ်ခုစလုံး တွဲဝယ်သူ: ၄,၀၀၀ ယောက် (ဝယ်သူအားလုံးရဲ့ 40%)

**The Computer's Result:** The system finds this rule: If a customer buys a Game, they will buy a Video.

**Support =** 40%: This is high (it meets a 30% threshold).

**Confidence =** 66%: This also seems high (it meets a 60% threshold).

---

## 2. Why is this rule misleading?

At first glance, 66% confidence looks great. However, when we look at the entire population, we see the truth:

ပထမဆုံး အကြိမ် ကြည့်လိုက်ရင်တော့ Confidence 66% ဆိုတာ အရမ်းကောင်းတယ်လို့ ထင်ရပါတယ်။ ဒါပေမဲ့ကိုယ်က databaseတစ်ခုလုံး ရဲ့ သဘာဝအမှန်ကို လှမ်းကြည့်လိုက်တဲ့အခါမှာ -

75% of ALL shoppers buy videos, regardless of what else they buy.
If a shopper buys a computer game, their chance of buying a video actually drops from 75% down to 66%.

ဝယ်သူအားလုံးထဲက 75% သော လူတွေဟာ အခြားဘာပစ္စည်းပဲ ဝယ်ဝယ်၊ မဝယ်ဝယ် ဗီဒီယိုခွေ (Videos) ကိုတော့ ပင်ကိုယ် သဘာဝအတိုင်း ဆိုင်ထဲမှာ အမြဲတမ်း ဝယ်ယူနေကြတာ ဖြစ်ပါတယ်။

**The Reality:** Buying a computer game actually makes a person less likely to buy a video. The rule is misleading because it suggests a positive relationship when the relationship is actually negative.

ဒါပေမဲ့ ဝယ်သူတစ်ယောက်က ကွန်ပျူတာဂိမ်း (Computer Game) ကို ဝယ်လိုက်ပြီဆိုရင်တော့ သူ ဗီဒီယိုခွေပါ ထပ်ဝယ်ဖို့ ဖြစ်နိုင်ခြေ Chance ဟာ မူလ 75% ရှိနေရာကနေ 66% အထိ သိသိသာသာကြီး ထိုးကျသွားတာ (Drops) ကို တွေ့ရမှာ ဖြစ်ပါတယ်။

---

## 3. The Solution: Correlation and Lift

To avoid being tricked by these misleading rules, we use a third measure called Lift (or Correlation).

အရှေ့မှာ တွေ့ခဲ့ရတဲ့ လှည့်စားတတ်တဲ့ စည်းမျဉ်းတွေရဲ့ ထောင်ချောက်ထဲ မကျရောက်စေဖို့အတွက် တတိယမြောက် သင်္ချာပေတံတစ်ခုဖြစ်တဲ့ Lift သို့မဟုတ် Correlation (ဆက်စပ်မှုနှုန်း) ကို ထပ်မံအသုံးပြုပြီး စစ်ထုတ်ရပါမယ်။

Lift = 1: The two items have no relationship; they are independent.

ပစ္စည်းနှစ်ခုစလုံးဟာ တစ်ခုနဲ့တစ်ခု ဘာဆက်စပ်မှုမှ မရှိကြပါဘူး။ ၎င်းတို့ဟာ သီးခြားစီ လွတ်လပ်စွာ ဖြစ်ပွားနေတာ (Independent) ဖြစ်ပါတယ်။

Lift > 1: The items are positively correlated (buying one truly increases the chance of buying the other).

ပစ္စည်းနှစ်ခုဟာ ကောင်းမွန်တဲ့ ဆက်စပ်မှု (Positively Correlated) ရှိကြပါတယ်။ ဆိုလိုတာက ဘယ်ဘက်ကောင် (LHS) ကို ဝယ်ယူခြင်းဟာ ညာဘက်ကောင် (RHS) ကိုပါ ထပ်မံဝယ်ယူဖို့ အခွင့်အလမ်းကို တကယ်ပဲ မြှင့်တင်ပေးလိုက်တာ (Truly Increases) ဖြစ်ပါတယ်။

Lift < 1: The items are negatively correlated (buying one actually decreases the chance of buying the other).

ပစ္စည်းနှစ်ခုဟာ ဆန့်ကျင်ဘက် ဆက်စပ်မှု (Negatively Correlated) ရှိနေပါတယ်။ ဆိုလိုတာက ဘယ်ဘက်ကောင်ကို ဝယ်လိုက်ခြင်းဟာ ညာဘက်ကောင်ကို ထပ်ဝယ်ဖို့ ရာခိုင်နှုန်းကို တကယ်တမ်းမှာတော့ ပိုပြီး လျော့နည်းသွားအောင် (Decreases) ဆွဲချပစ်လိုက်တာ ဖြစ်ပါတယ်။

**The Result for our Example:** The lift for the Game and Video rule is 0.89. Since this is less than 1, we know the rule is misleading and should be ignored.

---

## Summary

Imagine a rule that says: "If a person is a professional athlete, they probably have a heartbeat." The confidence would be 100%, but the rule is misleading because everyone has a heartbeat. Being an athlete doesn't "cause" the heartbeat. In data mining, we use Lift to make sure our rules are actually telling us something special, rather than just stating something that is already very common in the general population.


---

# Key notes from Tchel Hsu Myat Mo



