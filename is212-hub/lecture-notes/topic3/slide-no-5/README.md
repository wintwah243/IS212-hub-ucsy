# Introduction to Classification (slide 5 - 14.7.2026)

As introduced in the previous slide, data classification is a two-step process: first, we build a model (Learning), and then we use it to make predictions (Classification). Slide 5 dives deeper into how that first step actually works.

ဒေတာခွဲခြားသတ်မှတ်ခြင်း (Data Classification) ဆိုတာ အဆင့် နှစ်ဆင့် (Two-step Process) နဲ့ အလုပ်လုပ်တာ ဖြစ်ပါတယ် -

အဆင့် ၁ - သင်ယူခြင်း (Learning Phase): ဒေတာတွေကို လေ့လာပြီး Model တစ်ခု တည်ဆောက်ခြင်း။

အဆင့် ၂ - ခန့်မှန်းခြင်း (Classification Phase): တည်ဆောက်ထားတဲ့ Model ကို သုံးပြီး ဒေတာအသစ်တွေကို အမျိုးအစား လိုက်လံခွဲခြား ခန့်မှန်းခြင်း။

---

## 1. The Goal: Finding a "Mapping" Function

**The Idea:** In the learning step, the computer tries to find a mathematical formula or "mapping" that can link data to a specific category.

သင်ယူခြင်းအဆင့် (Learning Step) မှာ ကွန်ပျူတာဟာ မိမိဆီကို ရောက်လာမယ့် ဒေတာတွေနဲ့ သတ်မှတ်ထားတဲ့ အမျိုးအစား (Category) တွေကို တစ်ခုနဲ့တစ်ခု အမှားအယွင်းမရှိ ချိတ်ဆက်ပေးနိုင်မယ့် သင်္ချာဖော်မြူလာ သို့မဟုတ် Mapping Function တစ်ခုကို ရှာဖွေဖို့ ကြိုးစားတာ ဖြစ်ပါတယ်။

**The Formula:** You might see this written as y=f(X).

**X:** This is the information (data tuple) you give to the computer.

ဒါကတော့ ကွန်ပျူတာဆီကို ကိုယ်က ထည့်သွင်းပေးလိုက်တဲ့ သတင်းအချက်အလက်တွေ (ဥပမာ - ဝယ်သူတစ်ယောက်ရဲ့ အသက် = ၂၅၊ ဝင်ငွေ = ၄ သောင်း၊ ကျောင်းသား = ဟုတ်ကဲ့) ဆိုတဲ့ attributes/features အစုအဝေး ဖြစ်ပါတယ်။

**y:** This is the "class label" or category the computer predicts.

ဒါကတော့ ကွန်ပျူတာကနေ နောက်ဆုံး အမျိုးအစား ခွဲခြားပြီး ခန့်မှန်းထုတ်ပေးလိုက်မယ့် အဖြေမှန် (ဥပမာ - ကွန်ပျူတာ ဝယ်ယူမည် (Yes) သို့မဟုတ် မဝယ်ယူပါ (No)) ဆိုတဲ့ Category/Class ဖြစ်ပါတယ်။

**Why we do it:** We want the computer to learn a function that can effectively separate different classes of data from each other.

အဓိက ရည်ရွယ်ချက်ကတော့ ကွန်ပျူတာကို မတူညီတဲ့ ဒေတာအုပ်စုတွေကို တစ်ခုနဲ့တစ်ခု သဲသဲကွဲကွဲ ခွဲခြားနိုင်မယ့် စွမ်းရည် ရှိသွားစေချင်လို့ ဖြစ်ပါတယ်။

---

## 2. Supervised Learning: "Learning by Examples"

**What it is:** The learning process in classification is called supervised.

Classification (ဒေတာအမျိုးအစား ခွဲခြားခြင်း) ရဲ့ သင်ယူပုံလုပ်ငန်းစဉ်ကို Supervised Learning လို့ ခေါ်ပါတယ်။

**The Teacher:** It is called "supervised" because the computer is provided with a "training set" where the correct answers are already included.

ကွန်ပျူတာကို လေ့ကျင့်ပေးတဲ့အခါ "အဖြေမှန်" တွေ တစ်ခါတည်း ကြိုတင်ထည့်သွင်းပေးထားတဲ့ လေ့ကျင့်ခန်းဒေတာစု (Training Set) ကို ပေးထားတာ ဖြစ်လို့ ၎င်းကို "Supervised" စနစ်လို့ ခေါ်ရခြင်း ဖြစ်ပါတယ်။

**Labels:** Every piece of data in the training set is accompanied by a class label that tells the computer exactly which group it belongs to.

Training Set ထဲမှာ ရှိသမျှ ဒေတာအပိုင်းအစတိုင်းကို ၎င်းဒေတာဟာ ဘယ်အုပ်စုထဲကို အတိအကျ သက်ဆိုင်သလဲဆိုတာ ပြောပြပေးထားတဲ့ Class Label ကပ်ပေးထားပြီးသား ဖြစ်ပါတယ်။
ဥပမာ - အီးမေးလ်တစ်ခုချင်းစီရဲ့ ဘေးမှာ [Spam] သို့မဟုတ် [Not Spam] ဆိုပြီး အဖြေမှန် ကပ်ပေးထားတာမျိုး ဖြစ်ပါတယ်

**The Process:** Think of this as the computer studying for a test by looking at thousands of completed examples.

ကျောင်းသားတစ်ယောက်ဟာ စာမေးပွဲဖြေနိုင်ဖို့အတွက် အဖြေပါပြီးသား မေးခွန်းဟောင်းပေါင်း ထောင်နဲ့ချီကို အလွတ်ကျက်မှတ် လေ့လာနေတာနဲ့ တူပါတယ်

---

## Summary

Imagine you are teaching a child to tell the difference between Apples and Oranges.
In the Learning Step, you show them 10 apples and 10 oranges, telling them the name of each fruit as you show it (Supervised Learning).
The child's brain tries to find the "function"—noticing that the red ones are apples and the orange ones are oranges (Finding the Mapping).
Because you provided the names (the Labels), the child can learn the pattern correctly.

---

# Key notes from Tchel Hsu Myat Mo



