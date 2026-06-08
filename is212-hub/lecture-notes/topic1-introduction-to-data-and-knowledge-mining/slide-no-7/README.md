# Completing the KDD Process & Types of Data (slide7 - 7.6.2026)

This slide covers the final three "intelligent" steps of the Knowledge Discovery from Data (KDD) process and lists where we usually find this data.

    ဒီ Slide ကတော့ KDD (Knowledge Discovery from Data) လုပ်ငန်းစဉ်ရဲ့ နောက်ဆုံး သုံးဆင့်ဖြစ်တဲ့ "အသိဉာဏ်ဖြင့် ခွဲခြမ်းစိတ်ဖြာခြင်း (Intelligent Steps)" အကြောင်းနဲ့ ဒီလိုဒေတာတွေကို ပုံမှန်အားဖြင့် ဘယ်နေရာတွေမှာ ရှာဖွေတွေ့ရှိနိုင်သလဲဆိုတဲ့ အရင်းအမြစ် (Data Sources) တွေအကြောင်းကို ခြုံငုံဖော်ပြထားတာ ဖြစ်တယ်။

## 1. The Final Steps of Knowledge Discovery

After the data is cleaned and prepared (from the previous slide like cleaning, integration, ect.), we perform these final steps:

- **Data Mining:** This is the core "intelligent" step where we use specific computer methods to actually extract patterns from the data.

    Algorithm များနှင့် တွက်ချက်မှုနည်းလမ်းများကို သုံးပြီး ဒေတာအမြောက်အမြားထဲကနေ စိတ်ဝင်စားဖွယ်ရာ ပုံစံတူညီချက်များ (Patterns) သို့မဟုတ် ဆက်နွှယ်မှုများကို အလိုအလျောက် ရှာဖွေဖော်ထုတ်ခြင်း။

- **Pattern Evaluation:** Not every pattern found is useful. In this step, we use "interestingness measures" to identify which patterns truly represent valuable knowledge.

    ရှာဖွေတွေ့ရှိလာတဲ့ Pattern တွေထဲကမှ ဘယ်အရာက တကယ်ပဲ အသုံးဝင်လဲ၊ အဓိပ္ပာယ်ရှိလဲ၊ လက်တွေ့အသုံးချလို့ရလဲဆိုတာကို သတ်မှတ်ချက်စံနှုန်းများဖြင့် စစ်ဆေးအကဲဖြတ်ခြင်း။(လူကနေ စိစစ်တဲ့အဆင့်)

- **Knowledge Presentation:** Finally, we use visualization and special representation techniques to show the results to people in a way that is easy to understand.

    ရလာတဲ့ သတင်းအချက်အလက်နဲ့ အသိပညာတွေကို လူတွေ နားလည်လွယ်စေဖို့အတွက် Graph များ၊ Chart များ၊ Visualization Tool များသုံးပြီး သပ်ရပ်လှပစွာ ထုတ်ဖော်ပြသခြင်း။

---

## 2. Where does the data come from?

Data mining can be applied to many different types of data sets and applications, ranging from traditional systems to advanced ones:

## Traditional Database-Oriented Data:

- **Relational Databases:**  Organized tables of data (like Excel sheets).

- **Data Warehouses:** Large collections of data pulled together from many different sources.

- **Transactional Databases:** Systems that record daily transactions, like a store's sales records.

---

# Summary

If the previous slide was about "preparing the ingredients," this slide is about the actual cooking (Data Mining), tasting it to see if it’s good (Pattern Evaluation), and serving it on a plate so people can enjoy it (Knowledge Presentation). It also tells us we can get our "ingredients" from regular store databases or from high-tech sensors.

---

# Key notes from Tchel Hsu Myat Mo
- Transaction database ဆိုတာfrequently updateဖြစ်နေတာ။ Multi value ဖြစ်လို့ရတယ်။

- Relational database မှာACID propertiesရှိရမယ်။ Multi valueဖြစ်ရင် normalizeလုပ်ရမယ်။ columnတစ်ခုမှာ valueတစ်ခုပဲရှိရမယ်။

- data warehouse နဲ့ data warehousing မတူ။ data warehouseက collection of data(storage) ဖြစ်ပြီး data warehousing က warehouseပေါ်မှာလုပ်တဲ့ OLAP.



