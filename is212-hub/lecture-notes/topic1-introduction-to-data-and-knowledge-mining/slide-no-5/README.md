# What is Data Mining? (slide5 - 6.6.2026)

Data mining is a process where we use computers to semi-automatically look through very large databases to find patterns that are actually useful.

  Data miningဆိုတာက ကွန်ပျူတာကိုအသုံးပြုပြီး ရှုပ်ထွေးတဲ့ databaseထဲကdataတွေထဲကမှ (အထူးသဖြင့် businessအတွက်) လိုအပ်ပြီး အသုံးဝင်တဲ့ patternတွေကိုရှာဖွေတာကို Data miningလို့ခေါ်တယ်။

## 2. Turning Data into Knowledge

It is specifically about discovering interesting patterns, models, and knowledge that are hidden within massive amounts of data.

ဘာတွေကို ရှာတာလဲ? (What it discovers):

Interesting patterns – စိတ်ဝင်စားဖို့ကောင်းတဲ့ (အသုံးချလို့ရမယ့်) ဒေတာပုံစံတူညီချက်များ

Models – အနာဂတ်ကို ခန့်မှန်းတွက်ချက်ပေးနိုင်မယ့် မော်ဒယ်များ

Knowledge – လုပ်ငန်းခွင်အတွက် အဖိုးတန်တဲ့ အသိပညာနှင့် အချက်အလက်သစ်များ

---

# Key useful notes

- **Semi-Automatic Process:** This means the computer does the heavy lifting of searching through data, but humans still guide the process to ensure the results make sense.
- **Relationship to Machine Learning:** Data mining has similar goals to machine learning. The main difference is that data mining is designed to handle very large volumes of data.
- **The "KDD" Connection:** Data mining isn't a standalone task; it is one essential part of a larger field called Knowledge Discovery in Databases (KDD).

---

# Simple Workflow

- **Look at the Past:** You apply machine learning techniques to "past instances" or historical data.
- **Build a Model:** The computer uses that past data to form a model (a set of rules or patterns).
- **Predict the Future:** Once the model is ready, you use it to make predictions for new, incoming data.

---

# Key notes from Tchel Hsu Myat Mo

- Data ကနေ knowledgeပြောင်းရင် evaluationလိုတယ်။

- Evaluationမှာ Subjective နဲ့ Objective ဆိုပြီး ရှိ။ 
  ကွန်ပျူတာက ရှာဖွေပေးလိုက်တဲ့ ပုံစံတူညီချက် (Pattern) တွေက တကယ်ပဲ အသုံးဝင်လားဆိုတာကို နှစ်မျိုးနဲ့ တိုင်းတာတယ် -

  Objective Metrics: ဒါက Standard Metrics (စံနှုန်းဂဏန်းတွေ) နဲ့ တိုင်းတာတာ ဖြစ်တယ်။ လူရဲ့ ပုဂ္ဂိုလ်စွဲ ခံစားချက်မပါဘဲ သင်္ချာနည်းအရ သေချာတွက်ချက်ထားတဲ့ ဂဏန်းတွေ (ဥပမာ- Accuracy ဘယ်လောက် % ရှိလဲ) ပေါ်မှာပဲ မူတည်ပြီး ဆုံးဖြတ်တာ။

  Subjective Metrics: ဒါကတော့ လူ (အသုံးပြုသူ) ရဲ့ အမြင်၊ လိုအပ်ချက်နဲ့ အသိပညာပေါ် မူတည်တာ ဖြစ်ပါတယ်။ ဥပမာ- ကွန်ပျူတာက တွက်ထုတ်ပေးတဲ့ Pattern တစ်ခုက သင်္ချာနည်းအရ (Objective အရ) တန်ဖိုး တိကျနေပေမဲ့ လက်တွေ့လုပ်ငန်းခွင်မှာ လူတွေ သိပြီးသား သမိုင်းဟောင်း အချက်အလက်ကြီး ဖြစ်နေရင် "၎င်းသည် Subjective အရ စိတ်ဝင်စားစရာ မကောင်းဘူး (Not Interesting)" လို့ သတ်မှတ်တယ်။

- Classification မော်ဒယ်တွေရဲ့ စွမ်းဆောင်ရည်ကို တိုင်းတာဖို့အတွက် Accuracy ဟာ အသုံးအများဆုံးနဲ့ အခြေခံအကျဆုံး Specific Metric တစ်ခု ဖြစ်။

  Classification အတွက် မရှိမဖြစ် Standard Metrics များ
  
  Accuracy: မော်ဒယ်က ခန့်မှန်းလိုက်တဲ့အထဲကမှ အမှန်တကယ် မှန်ကန်သွားတဲ့ ရာခိုင်နှုန်း (Overall တိကျမှုကို ကြည့်တာ)။

  Precision: မော်ဒယ်က "မှန်တယ်" လို့ ခန့်မှန်းခဲ့တဲ့အထဲမှာ တကယ်ပဲ အမှန်တကယ် မှန်ကန်နေတဲ့ နှုန်း။

  Recall (Sensitivity): တကယ်ရှိနေတဲ့ အမှန်တရားတွေထဲကနေ မော်ဒယ်က ဘယ်နှခုကို မိအောင် ဖမ်းနိုင်ခဲ့သလဲဆိုတဲ့နှုန်း (ဥပမာ- လူနာ ၁၀ ယောက်မှာ ရောဂါရှိတာကို ၈ ယောက် မိအောင် ရှာနိုင်ရင် Recall 80%)။

  F1-Score: Precision နဲ့ Recall နှစ်ခုကြား မျှတမှုရှိမရှိကို ပေါင်းစပ်တွက်ချက်ထားတဲ့ Metric။



