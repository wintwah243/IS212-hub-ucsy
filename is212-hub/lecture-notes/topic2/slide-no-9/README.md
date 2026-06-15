# Frequent Itemset Mining Methods (slide 9 - 15.6.2026)

Finding every frequent group of items in a massive database is a difficult job for a computer. Researchers have developed several different methods to do this efficiently:

ပမာဏ အလွန်ကြီးမားတဲ့ Database ကြီးတစ်ခုထဲကနေ မကြာခဏ တွဲပြီး ဝယ်လေ့/ပါလေ့ရှိတဲ့ ပစ္စည်းအုပ်စုတွေအားလုံးကို လိုက်ရှာဖို့ဆိုတာ ကွန်ပျူတာတစ်လုံးအတွက် တကယ်ကို ခက်ခဲပင်ပန်းတဲ့ အလုပ်တစ်ခု ဖြစ်တယ်။ ဒါကြောင့်မို့ သုတေသီတွေဟာ ဒီအလုပ်ကို ပိုမိုမြန်ဆန်ထိရောက်စွာ (Efficiently) လုပ်ဆောင်နိုင်ဖို့အတွက် မတူညီတဲ့ နည်းလမ်းပေါင်းများစွာကို တီထွင်ဖန်တီးခဲ့ကြတယ်။

---

## 1. Apriori: The "Guess and Test" Method

**The Strategy:** This is a "Candidate Generation-and-Test" approach.

**How it works:** The computer makes a list of "candidates" (items it thinks might be popular) and then checks the database to see if it was right.

ကွန်ပျူတာကနေ "ဒီပစ္စည်းအတွဲတွေကတော့ လူဝယ်များနိုင်တယ်" ဆိုပြီး ဖြစ်နိုင်ခြေရှိတဲ့ ပစ္စည်းအတွဲစာရင်း (Candidates) တွေကို အရင်ဆုံး ခန့်မှန်း လိုက်ပါတယ်။ ပြီးတော့မှ တကယ့် Database ထဲကို သွားပြီး သူ့ခန့်မှန်းချက် မှန်/မမှန် (တကယ်လူဝယ်များရဲ့လားဆိုတာ) လိုက်လံ စစ်ဆေးတာ ဖြစ်တယ်။

**The Process:** It works level-by-level—first finding single popular items, then popular pairs, then groups of three, and so on.

သူက အဆင့်လိုက် (Level-by-level) လုပ်ဆောင်တယ်။ အရင်ဆုံး လူဝယ်အများဆုံး ပစ္စည်း ၁ ခုချင်းစီကို အရင်ရှာတယ်၊ ပြီးမှ လူဝယ်များတဲ့ ၂ ခုတွဲအတွဲတွေ၊ ပြီးမှ ၃ ခုတွဲအတွဲတွေ စသဖြင့် တဖြည်းဖြည်းချင်း အဆင့်တိုးပြီး ရှာဖွေသွားတာ ဖြစ်တယ်။

---

## 2. Improving the Efficiency of Apriori

**The Strategy:** These are "upgrades" to the basic Apriori method to make it run faster.

**How it works:** Because the basic "guess and test" method can be slow on huge databases, we use technical tricks like Hashing (sorting items into buckets) or Partitioning (breaking the data into smaller chunks) to speed things up.

အရှေ့မှာ ပြောခဲ့တဲ့အတိုင်း အခြေခံ "ခန့်မှန်းပြီးမှ စစ်ဆေးခြင်း (Guess and Test)" နည်းလမ်းဟာ database အလွန် ကြီးမားတဲ့အခါမှာ အလွန်နှေးကွေးသွားတတ်ပါတယ်။ ဒါကြောင့် အလုပ်တွေကို ပိုမိုမြန်ဆန်လာစေဖို့အတွက် Hashing ဒါမှမဟုတ် Partitioning (ဒေတာတွေကို အပိုင်းအစလေးတွေ ခွဲပစ်ခြင်း) ကဲ့သို့သော နည်းပညာဆိုင်ရာ လှည့်ကွက် (Technical Tricks) တွေကို အသုံးပြုပြီး အရှိန်မြှင့်တင်တာ ဖြစ်တယ်။

---

## 3. FPGrowth: The "Pattern-Growth" Method

**The Strategy:** A faster "Divide-and-Conquer" approach.

**How it works:** Instead of guessing and testing, this method compresses the entire database into a special map called an FP-Tree.

အရှေ့ကနည်းလမ်းလိုမျိုး itemအတွဲတွေကို လျှောက်ခန့်မှန်းပြီး လိုက်စစ်နေမယ့်အစား ဒီနည်းလမ်းက databaseတစ်ခုလုံးကို FP-Tree လို့ခေါ်တဲ့ ထူးခြားတဲ့ အပင်ပုံစံမြေပုံ (Special Map) တစ်ခုအဖြစ် ကျစ်လျစ်အောင် ချုံ့ပစ်လိုက်တာ ဖြစ်တယ်။

**The Benefit:** Once the data is compressed, the computer can find patterns directly from the tree without having to read the massive original database over and over again.

ဒေတာတွေကို အပင်ပုံစံအဖြစ် ချုံ့သိမ်းပြီးသွားတာနဲ့၊ ကွန်ပျူတာဟာ ပမာဏအလွန်ကြီးမားတဲ့ မူရင်းdatabaseကို အစအဆုံး အခါခါပြန်ပတ်ဖတ်နေစရာ လုံးဝမလိုတော့ဘဲ အဲဒီအပင် (Tree) ပေါ်ကနေတင် Frequent Patterns (လူဝယ်များတဲ့ တွဲဖက်မှုပုံစံတွေ) ကို တိုက်ရိုက် ရှာဖွေနိုင်သွားတာ ဖြစ်တယ်။

---

## 4. Vertical Data Format Mining

**The Strategy:** Flipping the data to look at it differently.

**How it works:** Most databases are "horizontal" (they list a Transaction ID and then the items bought). This method turns the data "vertical" by listing an Item and then every Transaction ID where it appeared.

ပုံမှန်အားဖြင့် databaseအများစုဟာ အလျားလိုက် (Horizontal) ပုံစံ ရှိကြတယ်။ (ဆိုလိုတာက ဝယ်ယူမှု ID တစ်ခုချင်းစီကို ချရေးပြီး၊ အဲဒီ ID အောက်မှာ ဘာပစ္စည်းတွေ ဝယ်သွားလဲဆိုပြီး စာရင်းလုပ်ထားတာပါ)။ ဒါပေမဲ့ ဒီနည်းလမ်းကတော့ အဲဒီဒေတာတွေကို ဒေါင်လိုက် (Vertical) ပုံစံ ဖြစ်သွားအောင် ပြောင်းပြန်လှန်ပစ်လိုက်ပါတယ်။ ပြောရရင် ပစ္စည်း (Item) နာမည်ကို အရင်ချရေးပြီး၊ အဲဒီပစ္စည်း ပါဝင်ခဲ့တဲ့ ဝယ်ယူမှု ID (Transaction ID) တွေအားလုံးကို အနောက်မှာ စာရင်းလိုက်တွဲပေးလိုက်တာ ဖြစ်တယ်။

**The Benefit:** By comparing these vertical lists, the computer can find overlapping patterns much more quickly than by searching through horizontal rows.

အခုလို ပြောင်းလဲလိုက်တဲ့ ဒေါင်လိုက်စာရင်း (Vertical Lists) တွေကို တစ်ခုနဲ့တစ်ခု အပြန်အလှန် နှိုင်းယှဉ်ကြည့်ခြင်းအားဖြင့်၊ ကွန်ပျူတာဟာ အလျားလိုက်တန်းကြီးတွေထဲမှာ တစ်ခုချင်းစီ လိုက်ရှာနေရတာထက် ပစ္စည်းအချင်းချင်း ထပ်တူညီမှုပုံစံ (Overlapping Patterns) တွေကို အများကြီး ပိုမိုမြန်ဆန်စွာ ရှာဖွေတွေ့ရှိနိုင်သွားတာ ဖြစ်တယ်။

---

## Summary

Think of these methods like four different ways to find common words in a library:

Apriori is like searching every book page-by-page.

Improving Apriori is like hiring more librarians to help search faster.

FPGrowth is like creating a detailed index of every word first so you don't have to keep opening the books.

Vertical Data Format is like ignoring the books entirely and just looking at a list of which page numbers contain the word "Data".

---

# Key notes from Tchel Hsu Myat Mo



