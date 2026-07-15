# What Makes a Pattern Interesting? (slide 11 - 14.7.2026)

In data mining, computers can find thousands of different patterns. However, "interestingness" is the filter we use to decide which of those patterns are actually valuable knowledge. To do this, we look at two types of measurements.

Data Mining ပြုလုပ်တဲ့အခါ Pattern တွေ ထောင်နဲ့ချီ ထွက်လာတတ်ပေမယ့်... တကယ့် စီးပွားရေးအရ အသုံးချလို့ရတဲ့ အဖိုးတန်အသိပညာ (Valuable Knowledge) ဖြစ်မဖြစ် စစ်ထုတ်ပေးတဲ့ အရေးကြီးဆုံး စကာတင်အဆင့် ဖြစ်ပါတယ်။

---

## 1. Objective Measures (The Math)

**What they are:** These are mathematical or statistical ways to measure a pattern.

ဒါတွေကတော့ ဒေတာထဲက ပုံစံအတွဲ (Pattern) တစ်ခုကို တိုင်းတာဖို့အတွက် အသုံးပြုတဲ့ သင်္ချာနည်းလမ်းတွေ သို့မဟုတ် စာရင်းအင်းဗေဒ (Statistical) ဆိုင်ရာ ပေတံတွေ ဖြစ်ပါတယ်။ (ဥပမာ - Support, Confidence, Lift, Chi-square စတာတွေ ဖြစ်ပါတယ်)။

**The Limitation:** While these measures help identify patterns that are strong (like those that happen very frequently), they are often insufficient on their own. A pattern can be mathematically perfect but still be completely useless to a business or researcher.

ဒီပေတံတွေဟာ databaseထဲမှာ အဖြစ်များလွန်းပြီး ခိုင်မာအားကောင်းတဲ့ ပုံစံတွေကို ရှာဖွေဖော်ထုတ်ပေးနိုင်ပေမယ့် တကယ့်လက်တွေ့မှာတော့ ၎င်းတို့ချည်းပဲ သီးသန့်ရပ်တည်ဖို့အတွက် လုံးဝ မလုံလောက်ပါဘူး ပုံစံတစ်ခုဟာ သင်္ချာနည်းအရ တွက်ချက်လိုက်တဲ့အခါမှာ လုံးဝကို အပြစ်ပြောစရာမရှိအောင် ပြီးပြည့်စုံနေနိုင်ပေမယ့် တကယ့်လက်တွေ့ စီးပွားရေးလုပ်ငန်း သို့မဟုတ် သုတေသနပညာရှင်တွေအတွက်တော့ လုံးဝ အသုံးမဝင်တဲ့အရာ ဖြစ်နေနိုင်လို့ ဖြစ်ပါတယ်

---

## 2. Subjective Measures (The Human Element)

**What they are:** These measures reflect a specific user’s needs and interests.

ဒီတိုင်းတာမှုတွေကတော့ data miningလုပ်ပြီးရတဲ့ ရလဒ်တွေကို ကြည့်ရှုမယ့် သတ်မှတ်ထားတဲ့ အသုံးပြုသူ (User/Business Owner) တစ်ဦးချင်းစီရဲ့ တကယ့်လိုအပ်ချက်နဲ့ စိတ်ဝင်စားမှုတွေအပေါ် တိုက်ရိုက် ရောင်ပြန်ဟပ် စစ်ထုတ်ပေးတဲ့ ပေတံတွေ ဖြစ်ပါတယ်။

**User Beliefs:** Subjective measures are based on what the user already believes about the data.

Subjective measures တွေဟာ အသုံးပြုသူက အဆိုပါ ဒေတာတွေအပေါ် လက်ရှိအချိန်မှာ ဘာတွေကို ကြိုတင်သိရှိထားပြီးသားလဲ၊ ဘာတွေကို ယုံကြည်ထားသလဲ ဆိုတဲ့အချက် (Domain Knowledge) ပေါ်မှာ အခြေခံပြီး တည်ဆောက်ထားတာ ဖြစ်ပါတယ်။

**Why they matter:** A pattern is truly interesting if it tells the user something new, something they didn't expect, or something they can actually use to make a decision.

ပုံစံအတွဲ (Pattern) တစ်ခုဟာ သင်္ချာနည်းအရပဲ အောင်မြင်နေရုံနဲ့ မလုံလောက်ပါဘူး။ ၎င်းသည် အသုံးပြုသူကို -
၁။ ဆန်းသစ်သော အရာတစ်ခုခုကို ပြောပြနိုင်မှ (Tells something new)
၂။ မိမိတို့ မမျှော်လင့်ထားတဲ့အရာ ဖြစ်နေမှ (Something they didn't expect) သို့မဟုတ်
၃။ လုပ်ငန်းခွင်မှာ ဆုံးဖြတ်ချက်တစ်ခုခု ချမှတ်ဖို့အတွက် လက်တွေ့ တကယ်အသုံးချလို့ရမှ (Actually use to make a decision - Actionable) သာလျှင် တကယ့် စိတ်ဝင်စားစရာကောင်းတဲ့ ပုံစံအစစ်အမှန် ဖြစ်လာမှာမို့လို့ ဖြစ်ပါတယ်

---

## 3. The Perfect Match

To find truly "interesting" knowledge, a data mining system must combine both:

စိတ်ဝင်စားဖို့ကောင်းပြီး အသုံးဝင်တဲ့အသိပညာအစစ်အမှန် (Truly Interesting Knowledge) ကို ရှာဖွေနိုင်ဖို့အတွက်  အောက်ပါအချက် နှစ်ခုစလုံးကို မဖြစ်မနေ ပေါင်းစပ်အသုံးပြုရမှာ ဖြစ်ပါတယ်

**Objective Strength:** It must be mathematically proven.

အဆိုပါ ပုံစံအတွဲ (Pattern) ဟာ ဒေတာတွေအပေါ်မှာ သင်္ချာနည်းအရ၊ စာရင်းအင်းဗေဒ (Statistical) နည်းအရ ခိုင်ခိုင်မာမာ သက်သေပြနိုင်စွမ်း ရှိရပါမယ် (ဥပမာ - Support, Confidence, Lift စတာတွေ မြင့်မားနေခြင်း)။

**Subjective Value:** It must be useful and relevant to the person looking at the results.

အဆိုပါ ရလဒ်တွေကို ကြည့်ရှုအသုံးချမယ့်သူ (လုပ်ငန်းရှင်၊ သုတေသနပညာရှင်) ရဲ့ လုပ်ငန်းနယ်ပယ်နဲ့ ကိုက်ညီပြီး တကယ့်လက်တွေ့ ဆုံးဖြတ်ချက်ချဖို့အတွက် အသုံးဝင်တဲ့ သတင်းအချက်အလက် ဖြစ်ရပါမယ်။

---

## Summary

Think of a pattern like a news story.
An Objective Measure is checking if the story is true and has plenty of facts.
A Subjective Measure is deciding if you actually care about that story. A news story about a cat stuck in a tree in a different country might be "true" (Objective), but it isn't "interesting" to you because it doesn't affect your life (Subjective). In data mining, we only want the "stories" that are both true and useful.

---

# Key notes from Tchel Hsu Myat Mo



