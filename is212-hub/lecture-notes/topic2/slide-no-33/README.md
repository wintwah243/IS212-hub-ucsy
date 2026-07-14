# Correlation Analysis (Nominal Data) (slide 33 - 12.7.2026)

This slide introduces a mathematical tool called the χ2
(Chi-square) test. It is used specifically for nominal data, which are items that are categorized by name or type rather than by numbers (for example, "Game" vs. "Video" or "Blue" vs. "Red").

ဒီslideက Chi-square ဟုခေါ်သော စာရင်းအင်းဗေဒဆိုင်ရာ သင်္ချာကိရိယာအသစ်တစ်ခုကို မိတ်ဆက်ပေးထားတာ ဖြစ်ပါတယ်။၎င်းကို ကိန်းဂဏန်းတန်ဖိုးတွေ မဟုတ်ဘဲ အမည် သို့မဟုတ် အမျိုးအစားအလိုက် ခွဲခြားသတ်မှတ်ထားတဲ့ Nominal Data (အမည်သတ်မှတ်ချက်ဒေတာ) တွေအကြား ဆက်စပ်မှု ရှိမရှိ စစ်ဆေးဖို့အတွက် သီးသန့်အသုံးပြုပါတယ် (ဥပမာ - "ဂိမ်း" နှင့် "ဗီဒီယို"၊ သို့မဟုတ် "အပြာရောင်" နှင့် "အနီရောင်" စသဖြင့် နာမည်တွေနဲ့ပဲ သတ်မှတ်ထားတဲ့ ပစ္စည်းတွေ ဖြစ်ပါတယ်)။

---

## 1. The χ 2 (Chi-square) Test

**The Purpose:** This test helps us determine if two different categories of data are related to each other or if they are just happening independently.

ဒီtestကမတူညီတဲ့ ဒေတာအမျိုးအစား (Categories) နှစ်ခုဟာ တစ်ခုနဲ့တစ်ခု တကယ်ပဲ ဆက်စပ်ပတ်သက်မှု ရှိနေကြတာလား သို့မဟုတ် ၎င်းတို့ဟာ အချင်းချင်း ဘာမှမဆိုင်ဘဲ သီးခြားစီ လွတ်လပ်စွာ ဖြစ်ပွားနေတာလား (Independently) ဆိုတာကို အပြတ်အသတ် ဆုံးဖြတ်နိုင်အောင် ကူညီပေးပါတယ်။

**The Logic:**
**The Result:** The larger the χ2 value, the more likely it is that the two variables are strongly related.

တွက်ချက်လို့ ရလာတဲ့ chi^2 တန်ဖိုး ပိုမိုကြီးမားလေလေ ၎င်း Variable ဒေတာနှစ်ခုဟာ တစ်ခုနဲ့တစ်ခု လုံးဝ လွတ်လပ်နေတာ မဟုတ်ဘဲ အလွန်ခိုင်မာစွာ ဆက်စပ်ပတ်သက်နေဖို့ ရာခိုင်နှုန်း ပိုမိုသေချာလေလေ (Strongly Related) ဖြစ်ပါတယ်။

**The Comparison:** To get this value, the computer compares the Actual Count (what we really observed in the data) against the Expected Count (what we would expect to see if the two things had no relationship at all).

chi^2 တန်ဖိုးကို ရှာဖို့အတွက် လက်တွေ့တန်ဖိုး (Observed) နဲ့ မျှော်မှန်းတန်ဖိုး (Expected) တို့ကြားက ကွာဟချက်ကို ရှာ၊ ၎င်းကို နှစ်ထပ်ကိန်းတင်၊ ပြီးရင် မျှော်မှန်းတန်ဖိုးနဲ့ ပြန်စားပြီး စုစုပေါင်းကို ပေါင်းရတာ ဖြစ်ပါတယ်။

**The Formula:** You calculate the difference between the observed and expected counts, square that difference, and divide it by the expected count: χ2=∑expected(observed−expected)2

---

## 2. Correlation vs. Causality (A Vital Warning)

One of the most important lessons in data mining is that correlation does not imply causality.

**What it means:** Just because two things happen together (correlation), it does not mean that one thing causes the other to happen.

အရာဝတ္ထု နှစ်ခုဟာ ဒေတာထဲမှာ တပြိုင်နက်တည်း အတူတူ ဖြစ်ပျက်နေရုံမျှနဲ့ Correlationတစ်ခုက အခြားတစ်ခုကို ဖြစ်ပွားအောင် ဖန်တီးခိုင်းစေနေတာ (Causality) လို့ လုံးဝ ကောက်ချက်ချလို့ မရပါဘူး။

**The Famous Example:** In a city, the number of hospitals and the number of car thefts might be highly correlated (they both go up at the same time).

Does more hospitals cause more car theft? No.

Does more car theft cause more hospitals? No.

**The Truth:** They are both linked to a third variable: Population. As a city gets bigger, you naturally get more hospitals and more crime.

---


## Summary

Think of the Chi-square test like a "relationship detector" for categories. If the math result (χ2) is high, it tells you that a relationship exists. However, you must always use common sense—just because a relationship exists, it doesn't mean one thing is causing the other; there might be a "hidden" third reason (like population) behind it all.



---

# Key notes from Tchel Hsu Myat Mo



