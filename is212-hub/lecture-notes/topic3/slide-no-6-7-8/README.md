# Supervised Learning (Classification) (slide 6,7 and 8 - 14.7.2026)

Supervised learning is often described as "learning by examples".

Supervised learning ကို "နမူနာများမှတစ်ဆင့် သင်ယူခြင်း (Learning by Examples)" လို့လည်း တင်စားခေါ်ဆိုကြပါတယ်။ ၎င်းတွင် အဓိက အဆင့် ၃ ဆင့်ဖြင့် အလုပ်လုပ်ဆောင်ပါတယ် -

**The "Supervision" (The Labels):** It is called "supervised" because the training data is accompanied by labels. These labels tell the computer exactly which category each observation belongs to.

စနစ်ကို လေ့ကျင့်ပေးဖို့ ထည့်သွင်းလိုက်တဲ့ Training Data တွေမှာ Labels (အဖြေမှန်များ) အမြဲတမ်း တစ်ပါတည်း ပူးတွဲပါဝင်နေပါတယ်။
ဒီအဖြေတံဆိပ်တွေက ဒေတာတစ်ခုချင်းစီဟာ ဘယ်အုပ်စု/ဘယ်အမျိုးအစားထဲကို တိတိကျကျ သက်ဆိုင်နေလဲဆိုတာ ကွန်ပျူတာကို လမ်းညွှန်ပြသပေးထားတာ ဖြစ်ပါတယ်။

**Building the Model:** The computer looks at these labeled examples (like a table showing weather conditions and whether someone played golf) and creates a Model.

ကွန်ပျူတာဟာ အဖြေပါပြီးသား နမူနာဒေတာတွေကို အသေးစိတ် လေ့လာဆန်းစစ်ပြီး ၎င်းတို့ကြားက ဆက်စပ်မှုကို နားလည်အောင် ကြိုးစားကာ Model တစ်ခုကို တည်ဆောက်လိုက်ပါတယ်။
ဥပမာ - "မိုးလေဝသ အခြေအနေများ" (နေသာသည်၊ မိုးရွာသည်၊ လေပြင်းတိုက်သည်) စတဲ့ အချက်အလက်တွေနဲ့ ၎င်းနေ့မှာ လူတွေ "ဂေါက်သီး ကစားခဲ့သလား သို့မဟုတ် မကစားခဲ့ဘူးလား (Play Golf = Yes/No)" ဆိုတဲ့ အဖြေမှန် ကပ်လျက်ပါဝင်နေတဲ့ ဇယားကွက်ကြီးကို ကြည့်ပြီး စည်းမျဉ်းတွေကို သင်ယူမှတ်သားကာ Model တည်ဆောက်သွားတာမျိုး ဖြစ်ပါတယ်။

**Prediction:** Once the model is built, you can give it new data (test instances) that it hasn't seen before. The model uses its "training" to predict the label for this new data.

Model ကြီး တည်ဆောက်ပြီးသွားပြီဆိုရင်တော့... သူ့ကို တကယ့်လက်တွေ့စမ်းသပ်မှုအဖြစ် သူတစ်ခါမှ မမြင်ဖူးသေးတဲ့ ဒေတာအသစ် (Test Instances) တွေကို ထည့်သွင်းပေးလိုက်ပါတယ်။

Model ဟာ အဆင့် (၂) တုန်းက လေ့ကျင့်မှတ်သားခဲ့တဲ့ "ဦးနှောက်/အတွေ့အကြုံ (Training)" ကို အသုံးပြုပြီး ဝင်လာတဲ့ ဒေတာအသစ်ရဲ့ အမျိုးအစား (Label) က ဘာဖြစ်မလဲဆိုတာကို လျင်မြန်စွာနဲ့ အမှန်ကန်ဆုံး ခန့်မှန်း (Predict) ပေးလိုက်တာ ဖြစ်ပါတယ်

---

# What about Classification Accuracy?

Once a computer has made its predictions, we need a way to tell if it did a good job. This is where accuracy comes in.

ကွန်ပျူတာကနေ ဒေတာအသစ်တွေကို အမျိုးအစား ခွဲခြားခန့်မှန်းပြီးသွားတဲ့အခါ... သူလုပ်ဆောင်ခဲ့တာဟာ တကယ်ပဲ ကောင်းမွန်ရဲ့လားဆိုတာ ဆုံးဖြတ်ဖို့ နည်းလမ်းတစ်ခု လိုအပ်ပါတယ်။ ဒါဟာ တိကျနှုန်း (Accuracy) ရဲ့ အခန်းကဏ္ဍပဲ ဖြစ်ပါတယ်။

**Definition of Accuracy:** Accuracy is the percentage of correctly classified cases in a test set.

စမ်းသပ်ဒေတာစု (Test Set) တစ်ခုလုံးထဲမှာ ကွန်ပျူတာကနေ မှန်ကန်စွာ အမျိုးအစား ခွဲခြားပေးနိုင်ခဲ့တဲ့ ဖြစ်ရပ်များ၏ ရာခိုင်နှုန်း (Percentage) ကို ခေါ်တာ ဖြစ်ပါတယ်။

**How it's Calculated:** We take a "test set" where we already know the real labels. We let the model guess the labels and then compare its predictions to the real ones to see how many it got right.

အဖြေမှန်အစစ်အမှန်တွေ (Real Labels) ကို ကြိုတင်သိရှိထားပြီးသားဖြစ်တဲ့ "စမ်းသပ်ဒေတာစု (Test Set)" တစ်ခုကို ယူလိုက်ပါတယ်။ ပြီးရင် Model ကို ၎င်းရဲ့အဖြေတွေကို ခန့်မှန်း (Guess) ခိုင်းလိုက်ပြီး... ရလာတဲ့ ခန့်မှန်းချက်တွေနဲ့ မူရင်းအဖြေမှန်တွေကို တိုက်ဆိုင်ယှဉ်ကြည့်ကာ ဘယ်နှစ်ခု တိတိကျကျ မှန်ကန်သလဲဆိုတာကို တွက်ထုတ်တာ ဖြစ်ပါတယ်

**The Key Metrics (The "Scoreboard"):** To understand why a model is or isn't accurate, we look at four specific numbers:

Model တစ်ခု ဘာကြောင့် တိကျနေရသလဲ (ဒါမှမဟုတ်) ဘာကြောင့် မှားနေရသလဲဆိုတဲ့ နောက်ကွယ်က အကြောင်းရင်းကို အသေးစိတ် ခွဲခြမ်းစိပ်ဖြာနိုင်ဖို့အတွက် အဓိက ကိန်းဂဏန်း ၄ ခု ရှိတဲ့ ဇယားကွက် (Confusion Matrix) ကို ကြည့်ရပါတယ်

**True Positives (TP):** The model correctly guessed "Yes" (e.g., predicted someone would buy a computer, and they did).

Model ကလည်း "Yes (ဖြစ်နိုင်တယ်)" လို့ မှန်ကန်စွာ ခန့်မှန်းခဲ့ပြီး၊ တကယ့် အဖြေအစစ်အမှန်ကလည်း "Yes" ဖြစ်နေတဲ့ အခြေအနေပါ။

ဥပမာ - Model က "ဒီလူ ကွန်ပျူတာ ဝယ်လိမ့်မယ်" လို့ ခန့်မှန်းပြီး၊ တကယ်လည်း ဝယ်သွားတဲ့ ဖြစ်ရပ်မျိုးပါ။

**True Negatives (TN):** The model correctly guessed "No."

Model ကလည်း "No (မဖြစ်နိုင်ဘူး)" လို့ မှန်ကန်စွာ ခန့်မှန်းခဲ့ပြီး၊ တကယ့် အဖြေအစစ်အမှန်ကလည်း "No" ဖြစ်နေတဲ့ အခြေအနေပါ။

ဥပမာ - Model က "ဒီလူ ကွန်ပျူတာ ဝယ်မှာမဟုတ်ဘူး" လို့ ခန့်မှန်းပြီး၊ တကယ်လည်း ဝယ်မသွားတဲ့ ဖြစ်ရပ်မျိုးပါ။

**False Positives (FP):** The model guessed "Yes," but the real answer was "No" (a "false alarm").

Model က "Yes" လို့ ခန့်မှန်းခဲ့ပေမယ့်၊ တကယ့် အဖြေအစစ်အမှန်က "No" ဖြစ်နေတဲ့ အမှားမျိုးပါ။

ဥပမာ - မဝယ်မယ့်လူကို ဝယ်လိမ့်မယ်လို့ မှားယွင်းခန့်မှန်းတာမျိုး သို့မဟုတ် Normal Email ကို Spam Email လို့ မှားပြီး ဖမ်းလိုက်တာမျိုး ဖြစ်ပါတယ်။

**False Negatives (FN):** The model guessed "No," but the real answer was "Yes" (a "missed" prediction).

Model က "No" လို့ ခန့်မှန်းခဲ့ပေမယ့်၊ တကယ့် အဖြေအစစ်အမှန်က "Yes" ဖြစ်နေတဲ့ အမှားမျိုးပါ။

ဥပမာ - တကယ် ဝယ်မယ့်သူကို မဝယ်ဘူးလို့ ထင်ပြီး လွှတ်လိုက်မိတာမျိုး သို့မဟုတ် တကယ့် ရောဂါရှိသူကို ရောဂါမရှိဘူးလို့ မှားယွင်းထုတ်ပြန်မိတာမျိုး (လွဲချော်သွားတဲ့ ခန့်မှန်းချက်) ဖြစ်ပါတယ်

---

# How We Test the Model (Evaluation Methods)

To get a fair accuracy score, we must follow a strict workflow to ensure the computer isn't just "memorizing" the answers.

တရားမျှတပြီး အမှန်ကန်ဆုံးဖြစ်တဲ့ တိကျမှုရမှတ် (Fair Accuracy Score) ကို ရရှိဖို့အတွက်... ကွန်ပျူတာဟာ အဖြေတွေကို ရိုးရိုးရှင်းရှင်းကြီး အလွတ်ကျက်မှတ်သွားခြင်း (Memorizing) မရှိစေဖို့ တင်းကျပ်တဲ့ လုပ်ငန်းစဉ် (Strict Workflow) အတိုင်း စမ်းသပ်ရပါမယ်။

**The Data Split:** We divide our total data into two separate "piles":
ငါတို့မှာ ရှိနေတဲ့ စုစုပေါင်း ဒေတာအုပ်စုကြီးကို လုံးဝ မတူညီတဲ့ အစုအပုံကြီး နှစ်ခု (Two Separate Piles) အဖြစ် မဖြစ်မနေ သီးသန့် ခွဲထုတ်လိုက်ရပါမယ်။

**1.Training Set:** This is used by the computer to learn and build (derive) the model.

လေ့ကျင့်ခန်း ဒေတာစု (Training Set): ၎င်းဒေတာကိုတော့ ကွန်ပျူတာကနေ ပုံစံတွေ လေ့လာမှတ်သားပြီး Model တည်ဆောက် (Derive) ဖို့အတွက် ဆရာနဲ့သင်သလိုမျိုး အပြည့်အဝ အသုံးပြုခွင့် ပေးထားပါတယ်။

**2.Test Set:** This is "unseen" data used only at the end to estimate the accuracy of the model.

စမ်းသပ် ဒေတာစု (Test Set): ၎င်းဒေတာကိုတော့ ကွန်ပျူတာကို လုံးဝ ပေးမမြင်ဘဲ ဝှက်ထားရပါမယ်။ Model တစ်ခုလုံး ဆောက်ပြီးသွားတဲ့ အဆုံးသတ်ကျမှသာ Model ရဲ့ တကယ့် အရည်အချင်းစစ် တိကျနှုန်း (Accuracy) ကို တိုင်းတာဖို့အတွက် "သူတစ်ခါမှ မမြင်ဖူးသေးတဲ့ ဒေတာအသစ် (Unseen Data)" အဖြစ် အသုံးပြုတာ ဖြစ်ပါတယ်


**Testing Strategies:**
**1.Holdout Method:** You "hold out" a portion of your data (like 30%) and use it strictly for testing.

ကိုယ့်မှာရှိတဲ့ ဒေတာစုစုပေါင်းထဲက အချို့အပိုင်း (ဥပမာ - 70% ကို Training အတွက်သုံးပြီး ကျန်တဲ့ 30% ကိုတော့ accuracyစစ်ဖို့အတွက်) သီးသန့် ဖယ်ချန် ထားလိုက်တာ ဖြစ်ပါတယ်။

**2.Cross-Validation:** You split the data into k different parts and take turns using each part as the "test set" while the others are used for training. This helps ensure the results are reliable.

ဒေတာအားလုံးကို k လို့ခေါ်တဲ့ အပိုင်းအစ တူညီတဲ့ အစိတ်အပိုင်းလေးတွေ (ဥပမာ - ၁၀ ပိုင်း) အညီအမျှ ခွဲလိုက်ပါတယ်။
ပြီးရင် တစ်ခေါက်တွက်ရင် အပိုင်း (၁) ကို Test အဖြစ် သုံးပြီး ကျန်တဲ့ အပိုင်း ၉ ပိုင်းကို Train အဖြစ် သုံးပါတယ်။ 
နောက်တစ်ခေါက်ကျရင် အပိုင်း (၂) ကို Test အဖြစ် သုံးပြီး ကျန်တာကို Train အဖြစ် သုံးပါတယ်။
ဒီလိုမျိုး k အကြိမ်အထိ တစ်လှည့်စီ အပြန်အလှန် စမ်းသပ်တွက်ချက်ပြီးမှ ရလာတဲ့ Accuracy တွေအားလုံးကို ပျမ်းမျှ (Average) ပြန်ရှာတာ ဖြစ်ပါတယ်။

ဒီနည်းလမ်းဟာ ဒေတာအားလုံးကို Train ရော Test ရော အလှည့်ကျ နေရာစုံ သုံးသွားတာ ဖြစ်လို့ ရလဒ်ကို အလွန် ယုံကြည်စိတ်ချရပြီး တည်ငြိမ်စေပါတယ် (Highly Reliable)

---

## Summary

Think of Supervised Learning like a student studying with an answer key (Slide 6). Accuracy is the student's final grade on a test (Slide 7). To make sure the student actually learned the material and didn't just memorize the answer key, we give them a new test they've never seen before (Slide 8).

---

# Key notes from Tchel Hsu Myat Mo



