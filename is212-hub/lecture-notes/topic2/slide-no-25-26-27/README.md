# Slides 25 & 26: Introduction to Association Rules (slide 25,26,27 - 12.7.2026)

Association rules are used to find interesting relationships between different items in large sets of data.

Association Rules ဆိုတာက databaseအကြီးကြီးတွေထဲမှာ ရှိနေတဲ့ မတူညီတဲ့ ပစ္စည်းတွေအကြားက စိတ်ဝင်စားဖို့ကောင်းတဲ့ ဆက်ဆံရေး ပတ်သက်မှုတွေ (Interesting Relationships) ကို ရှာဖွေဖော်ထုတ်ဖို့ အသုံးပြုတဲ့ နည်းလမ်း ဖြစ်ပါတယ်။

**The Retail Perspective:** Shops are very interested in these rules to understand what customers buy together.

ဆိုင်ပိုင်ရှင်တွေဟာ ဝယ်သူတွေက ဆိုင်ထဲမှာ ဘယ်ပစ္စည်းတွေကို တွဲဖက်ပြီး ဝယ်ယူလေ့ရှိကြလဲဆိုတာကို နားလည်ဖို့အတွက် ဒီစည်းမျဉ်းတွေကို အလွန် စိတ်ဝင်စားကြပါတယ်။

**Common Examples:** Someone who buys bread is very likely to also buy milk.

ဆိုင်တစ်ဆိုင်မှာ "ပါမုန့်" ဝယ်တဲ့သူဟာ "နို့" ကိုပါ တစ်ပါတည်း တွဲဝယ်သွားဖို့ ရာခိုင်နှုန်း အလွန်များပြားတာမျိုး ဖြစ်ပါတယ်။

**E-commerce:** If you buy a textbook on Database Systems, a shop might suggest a book on Operating Systems because they are frequently bought together.

အကယ်၍ သင်က အွန်လိုင်းမှာ Database Systems ကျောင်းသုံးစာအုပ်ကို ဝယ်လိုက်မယ်ဆိုရင်အဲဒီဝက်ဘ်ဆိုက်က သင့်ကို Operating Systems စာအုပ်ကိုပါ ဝယ်ဖို့ လှမ်းပြီး Suggest ပေးလာတတ်ပါတယ်။ ဘာလို့လဲဆိုတော့ ကျောင်းသားအများစုဟာ ဒီစာအုပ်နှစ်အုပ်ကို အမြဲတမ်း တွဲဝယ်လေ့ရှိကြလို့ ဖြစ်ပါတယ်။

**The Structure of a Rule:** Every association rule has two parts, separated by an arrow (⇒):

ဆက်စပ်မှုစည်းမျဉ်း တိုင်းမှာ မြှားခေါင်းပုံစံ ($\Rightarrow$) လေးနဲ့ ပိုင်းခြားထားတဲ့ အစိတ်အပိုင်း နှစ်ခု အမြဲတမ်း ပါဝင်ပါတယ်

**Antecedent (Left Hand Side):** The "If" part of the rule (the item already in the basket).

မြှားရဲ့ ဘယ်ဘက်ခြမ်း မှာ ရှိတဲ့အပိုင်း ဖြစ်ပြီး၊ ၎င်းကို "အကြောင်းအရင်း (If)" အပိုင်းလို့ ခေါ်ပါတယ်။

အဓိပ္ပာယ်ကတော့ ဝယ်သူရဲ့ ခြင်းတောင်းထဲမှာ လက်ရှိ အမှန်တကယ် ပါဝင်နေပြီးသား ပစ္စည်း ကို ပြောတာ ဖြစ်ပါတယ်။

**Consequent (Right Hand Side):** The "Then" part of the rule (the item likely to be added).

မြှားရဲ့ ညာဘက်ခြမ်း မှာ ရှိတဲ့အပိုင်း ဖြစ်ပြီး၊ ၎င်းကို "ရလဒ် (Then)" အပိုင်းလို့ ခေါ်ပါတယ်။

အဓိပ္ပာယ်ကတော့ ဘယ်ဘက်ခြမ်းက ပစ္စည်းကို ဝယ်ပြီးတဲ့နောက်မှာ ဝယ်သူက ခြင်းတောင်းထဲကို ထပ်မံ ထည့်သွင်း ဝယ်ယူသွားဖို့ ရာခိုင်နှုန်းများတဲ့ ပစ္စည်း ကို ပြောတာ ဖြစ်ပါတယ်။

**The Population:** A rule must be based on a specific group of data, such as the set of all sales (transactions) made at a shop.

ဆက်စပ်မှုစည်းမျဉ်းတစ်ခုဟာ စိတ်ကူးယဉ်ပြီး သတ်မှတ်တာ မဟုတ်ပါဘူး။ ဆိုင်တစ်ဆိုင်မှာ တကယ်ဖြစ်ပျက်ခဲ့ဖူးတဲ့ စုစုပေါင်း အရောင်းပြေစာမှတ်တမ်းများ (All Sales Transactions) ဆိုတဲ့ သတ်မှတ်ထားတဲ့ databaseကြီးတစ်ခုလုံးပေါ်မှာ အခြေခံပြီး သင်္ချာနည်းအရ တွက်ချက်ထုတ်ယူထားတာ ဖြစ်ပါတယ်။

---

# Slide 27: Measuring Rule "Strength" (Support & Confidence)

Not all rules are useful. We use two main mathematical "yardsticks" to decide if a rule is strong enough to be considered "knowledge".

ထွက်လာသမျှ ဆက်စပ်မှုစည်းမျဉ်းတိုင်းဟာ လုပ်ငန်းခွင်မှာ အသုံးဝင်နေတာ မဟုတ်ပါဘူး။ ဒါကြောင့် စည်းမျဉ်းတစ်ခုဟာ တကယ်ပဲ ခိုင်မာအားကောင်းပြီး လုပ်ငန်းခွင်မှာ အသုံးချလို့ရတဲ့ "အသိပညာ ဗျူဟာ (Knowledge)" ဖြစ်မဖြစ် ဆုံးဖြတ်ဖို့အတွက် အဓိက သင်္ချာပေတံ (Yardsticks) နှစ်ခုကို အသုံးပြုပါတယ်။

## 1. Support (How common is the whole pattern?)

**Definition:** The fraction of the total population that contains both the antecedent and the consequent.

databaseတစ်ခုလုံး (Total Population) ထဲမှာ မြှားရဲ့ ဘယ်ဘက်ခြမ်း (Antecedent) ရော၊ ညာဘက်ခြမ်း (Consequent) ရော နှစ်ခုစလုံး တစ်ပြိုင်နက်တည်း တွဲလျက်သား ပါဝင်နေတဲ့ အချိုးအစား (Fraction) ကို ပြောတာ ဖြစ်ပါတယ်။

**In Plain English:** If only 1 out of 1,000 customers buys both "Milk" and "Screwdrivers," the support for that rule is very low (0.1%), meaning it’s a rare occurrence.

တကယ်လို့ ဝယ်သူ စုစုပေါင်း ၁,၀၀၀ ရှိတဲ့အနက်မှ "နို့" နဲ့ "ဝက်အူလှည့်" နှစ်ခုစလုံးကို တွဲဝယ်သွားတဲ့သူက ၁ ယောက်ပဲ ရှိတယ်ဆိုရင်အဲဒီစည်းမျဉ်းရဲ့ Support ဟာ အလွန်နည်းပါးလွန်းပါတယ် (0.1% ပဲ ရှိပါတယ်)။ ဒါဟာ ဆိုင်ထဲမှာ အလွန်ဖြစ်တောင့်ဖြစ်ခဲတဲ့ ပုံစံမျိုး ဖြစ်လို့ စီးပွားရေးအရ အသုံးမဝင်ပါဘူး။

**Example:** A rule like age(20..29) ^ income(40K..49K) => buys(laptop) might have a support of 2%, meaning 2% of all people in the data fit this entire description.

---

## 2. Confidence (How reliable is the prediction?)

**Definition:** A measure of how often the consequent is true when the antecedent is already true.

မြှားရဲ့ ဘယ်ဘက်ခြမ်း (Antecedent) က အခြေအနေဟာ အမှန်တကယ် ဖြစ်ပွားနေပြီးသား အချိန်မှာ ညာဘက်ခြမ်း (Consequent) က အခြေအနေပါ ထပ်မံ မှန်ကန်လာဖို့ ဘယ်လောက်အထိ အကြိမ်ရေ ဖြစ်ပွားလေ့ရှိသလဲ (How often) ဆိုတာကို တိုင်းတာတဲ့ နှုန်းထား ဖြစ်ပါတယ်။

**In Plain English:** If 80% of people who buy bread also buy milk, then the rule Bread => Milk has a confidence of 80%.

အကယ်၍ ဆိုင်ထဲမှာ "ပါမုန့်" ဝယ်သွားတဲ့ လူအားလုံးထဲက 80% သော လူတွေဟာ "နို့" ကိုပါ တစ်ပါတည်း တွဲဝယ်သွားကြတယ် ဆိုရင် Bread => Milk ဆိုတဲ့ စည်းမျဉ်းရဲ့ Confidence ဟာ 80% ရှိတယ်လို့ သတ်မှတ်ပါတယ်။

**Example:** In the rule mentioned above for buying a laptop, a confidence of 60% means that if we find someone aged 20–29 with that specific income, there is a 60% chance they will buy a laptop.

အရှေ့က Slide တုန်းက ပြောခဲ့တဲ့ လက်ပ်တော့ပ် (Laptop) ဝယ်ယူမှု စည်းမျဉ်းမှာပဲဖြစ်ဖြစ်၊ Confidence က 60% ရှိတယ်လို့ ပေးထားရင်၎င်းရဲ့ အဓိပ္ပာယ်ကတော့ "အသက် ၂၀ မှ ၂၉ ကြားရှိပြီး ဝင်ငွေ ၄ သောင်းကျော်ရှိတဲ့ လူတစ်ယောက်ကို ကိုယ်က တွေ့လိုက်ပြီ (If) ဆိုတာနဲ့ထိုလူဟာ laptopဝယ်ယူဖို့အတွက် 60% သော ဖြစ်နိုင်ခြေ (Chance) ရှိနေတယ်" လို့ ယုံကြည်စိတ်ချစွာ ခန့်မှန်းနိုင်ခြင်း ဖြစ်ပါတယ်

---

## Summary

Think of Association Rules as the "If-Then" logic of shopping. Support tells you how popular the entire combination is across the whole store, while Confidence tells you how accurate your "Then" guess is once you know the "If" part. Shops use these rules to place items near each other or to show you "Customers also bought..." suggestions online.


---

# Key notes from Tchel Hsu Myat Mo



