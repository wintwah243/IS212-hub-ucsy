# Data Mining as Part of a Process (slide6 - 6.6.2026)

It is important to understand that Data Mining is not a single, isolated task. It is actually one vital step in a much larger cycle called the Knowledge Discovery Process.

Data Miningဆိုတာ သီးခြားစီ သီးသန့်လုပ်ဆောင်ရတဲ့ လုပ်ငန်းစဉ်တစ်ခု မဟုတ်။ 
သူဟာ Knowledge Discovery Process လို့ခေါ်တဲ့ ပိုမိုကြီးမားတဲ့ processထဲက အလွန်အရေးကြီးတဲ့ အဆင့်တစ်ခုသာ ဖြစ်တယ်။

Before the computer can actually "mine" for patterns, the data must go through several preparation steps:

ကွန်ပျူတာကနေပြီး Data တွေထဲက Patternsတွေကို မရှာဖွေခင်မှာ အဲဒီ Data တွေကို အဆင့်ဆင့်ကို အရင်ဆုံး ဖြတ်သန်းရ။ အပြင်ကရလာတဲ့ Raw Data တွေထဲမှာ အမှိုက်တွေ၊ အမှားတွေ ပါနေတတ်လို့ အဲဒါတွေကို အရင်ဖယ်ရှားဖို့လို။

## 1. Data Cleaning

- **Purpose:** To tidy up the information.
- **What happens:** We remove "noise" (useless or random errors) and fix inconsistent data (where the same information might be recorded in different ways).

---

## 2. Data Integration

- **Purpose:** To bring everything together.
- **What happens:** Often, information is stored in many different places. In this step, we combine multiple data sources into one single "warehouse" so we can look at the big picture.

---

## 3. Data Selection

- **Purpose:** To focus on what matters.
- **What happens:** We don't always need every single piece of data we have. Here, we retrieve only the specific data that is relevant to the task we are trying to solve.

**Example for Data Selection process-** ကျောင်းသားတွေရဲ့ စာမေးပွဲအောင်ချက်ကို Data Mining လုပ်ပြီး ခန့်မှန်းမယ်ဆိုရင် ကျောင်းသား Database ထဲမှာ ကျောင်းသားအမည်၊ အသက်၊ ဖုန်းနံပါတ်၊ လိပ်စာ၊ အိမ်စာအမှတ်၊ Attendanceတွေ အကုန်ပါနေမယ်။

ဒါပေမဲ့ အောင်ချက်ကို တွက်ဖို့အတွက် "ဖုန်းနံပါတ်" နဲ့ "လိပ်စာ" က မလိုအပ်ပါဘူး။ ဒါကြောင့် အဲဒီမလိုတာတွေကို ဖယ်ပြီး တကယ်လိုအပ်တဲ့ "အိမ်စာအမှတ်" နဲ့ "Attendance" ဒေတာတွေကိုပဲ ရွေးထုတ်ယူလိုက်တဲ့အဆင့်ကို Data Selection လို့ ခေါ်။

---

## 4. Data Transformation

- **Purpose:** To make the data ready for the computer.
- **What happens:** Data is converted or "consolidated" into a form that is appropriate for mining. A common way to do this is through aggregation (grouping data together, like turning daily sales into a monthly total).

**Example for Data Transformation process-** ကွန်ပျူတာက စာသားတွေကို တိုက်ရိုက်တွက်ရတာထက် ဂဏန်းတွေကို ပိုတွက်ရလွယ်ပါတယ်။ ဒါကြောင့် ဥပမာ- Gender နေရာမှာ Male / Female လို့ ရှိနေရင် ကွန်ပျူတာ ဖတ်ရလွယ်အောင် Male = 1၊ Female = 0 ဆိုပြီး ဂဏန်းပုံစံ ပြောင်းလဲပေးလိုက်တဲ့ လုပ်ငန်းစဉ်မျိုး ဖြစ်တယ်။

---

# Summary

Think of this slide like cooking a meal. Before you actually cook (the Data Mining step), you have to wash your vegetables (Cleaning), gather all your ingredients from different cupboards (Integration), pick only the ones you need for the recipe (Selection), and chop them up so they are ready for the pan (Transformation).


