# The Two Main Categories of Mining (slide10 and 11 - 7.6.2026)

Data mining tasks are generally divided into two big categories depending on what we want to achieve with our data: Predictive tasks and Descriptive tasks.

Data Mining Tasks တွေကို မိမိတို့ရဲ့ ဒေတာတွေကနေ ဘာကို ရလဒ်အဖြစ် ရချင်တာလဲ (What we want to achieve) ပေါ် မူတည်ပြီး အုပ်စု ၂ ခု ခွဲခြားနိုင်။

## 1. Predictive Mining Tasks

- **The Goal:** To look at the data we have now and use it to make guesses or predictions about the future or about unknown values.

လက်ရှိ ရှိနေတဲ့ ဒေတာ (Data we have now) တွေကို ကြည့်ပြီး အနာဂတ် (Future) မှာ ဘာဖြစ်မလဲ၊ ဒါမှမဟုတ် မသိရသေးတဲ့ တန်ဖိုးတွေ (Unknown values) က ဘာဖြစ်မလဲဆိုတာကို ခန့်မှန်းတွက်ချက်ရန် ဖြစ်တယ်။

- **How it works:** The computer performs "induction," which means it learns rules from current data to apply to new, unseen information.

ကွန်ပျူတာက "Induction" (စုံစမ်းသိရှိခြင်းနည်းလမ်း) ကို လုပ်ဆောင်တယ်။ ဆိုလိုတာက လက်ရှိရှိနေတဲ့ ဒေတာတွေဆီကနေ စည်းမျဉ်းစည်းကမ်း (Rules) တွေ၊ ပုံစံတွေကို သင်ယူလေ့လာပြီး၊ အဲဒီသင်ယူထားတဲ့ အသိပညာကို တစ်ခါမှ မမြင်ဖူးသေးတဲ့ ဒေတာအသစ် (New, unseen information) တွေပေါ်မှာ သက်ရောက်အသုံးချတာ ဖြစ်တယ်။

- **Core Mechanisms for Prediction:** 

    **Classification:** This is like sorting items into labeled "buckets" or classes.
    The computer uses training instances (examples where the answer is already known) to learn the rules.
    Example: Predicting if a new credit card applicant is a "good risk" or a "bad risk" based on their income and age.

    Classificationက အချက်အလက်တွေကို နာမည်တပ်ထားတဲ့ "အုပ်စု (Labeled buckets or classes)" တွေထဲကို စနစ်တကျ ရွေးထုတ် ထည့်သွင်းတာနဲ့ တူတယ်။ (ဥပမာ: ခရက်ဒစ်ကတ် လျှောက်ထားသူအသစ်တစ်ယောက်ရဲ့ အဝင်လစာ (Income) နဲ့ အသက် (Age) ကို ကြည့်ပြီး သူက ဘဏ်အတွက် "အန္တရာယ်ကင်းတဲ့သူ (Good risk)" လား၊ ဒါမှမဟုတ် "အန္တရာယ်ရှိတဲ့သူ (Bad risk)" လားဆိုပြီး အုပ်စုနှစ်ခုထဲက တစ်ခုခုထဲ ရောက်အောင် ကြိုတင်ခန့်မှန်းပေးတာမျိုး)

    **Regression:** This is used when we want to predict a specific numerical value or a mathematical result rather than just a category.

    ငါတို့ခန့်မှန်းချင်တဲ့အရာက အပေါ်ကလိုမျိုး Yes/No သို့မဟုတ် Good/Bad စတဲ့ အုပ်စု (Category) မျိုး မဟုတ်ဘဲ၊ တိကျတဲ့ ကိန်းဂဏန်း တန်ဖိုးတစ်ခု (Specific numerical value) သို့မဟုတ် သင်္ချာနည်းအရ ထွက်လာမယ့် ရလဒ်မျိုး ဖြစ်နေတဲ့အခါမှာ Regression ကို အသုံးပြုတယ်။ (ဥပမာ- ရှယ်ယာဈေးနှုန်း၊ အိမ်ဈေးနှုန်း စတဲ့ Continuous values တွေ တွက်တာမျိုး)။

---

## 2. Descriptive Mining Tasks

- **The Goal:** To characterize and summarize the properties of the data we already have.

ငါတို့ဆီမှာ ရှိနှင့်ပြီးသား ဒေတာတွေ (Data we already have) ရဲ့ ဂုဏ်သတ္တိတွေကို ဖော်ထုတ်ပေးဖို့နဲ့ အနှစ်ချုပ် (Summarize) ပေးဖို့ ဖြစ်တယ်။

- **How it works:** Instead of looking forward, these tasks look at the "target data set" to explain what is happening inside it.

အနာဂတ်ကို မျှော်ကြည့်တာမျိုး (Looking forward) မဟုတ်ဘဲ၊ လက်ရှိလေ့လာနေတဲ့ "Target data set (ပစ်မှတ်ဒေတာအစုအဝေး)" ရဲ့ အတွင်းပိုင်းမှာ ဘာတွေ ဖြစ်ပျက်နေသလဲ (What is happening inside) ဆိုတာကို ပုံဖော်ရှင်းလင်းပြသပေးတာ ဖြစ်တယ်။

- **Example (Associations):** Finding items that are frequently bought together. (for example-If customers who buy "Book A" often buy "Book B," the system describes this relationship so the store can suggest "Book B" to new buyers)

လူတွေ ဆိုင်မှာ ပစ္စည်းဝယ်တဲ့အခါ ဘယ်ပစ္စည်းတွေကို အမြဲတမ်း တွဲလျက် ဝယ်လေ့ရှိကြသလဲ (Frequently bought together) ဆိုတဲ့ ပုံစံတူညီချက်တွေကို ရှာဖွေပေးတာ ဖြစ်တယ်။

---

# Summary

Think of Predictive tasks like a weather forecast (using today's clouds to guess tomorrow's rain) and Descriptive tasks like a census report (summarizing exactly who lives in the city right now).

---

# Key notes from Tchel Hsu Myat Mo

- descriptive task က ရှိနေတဲ့ dataရဲ့ propertiesကိုကြည့်ပြီး analysisလုပ်သွားတာ။ clusteringလုပ်ပြီး တူရာတူရာစုသွားတာ။

- descriptive task မှာဆိုရင် check frequence before association

