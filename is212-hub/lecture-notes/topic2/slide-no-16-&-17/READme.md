# Improving Efficiency: Hash-Based Technique (slide 16 and 17 - 28.6.2026)

Even though the basic Apriori algorithm is smart, it can still generate a massive number of "candidate" pairs to check. The Hash-based technique is used to shrink that list of candidates before the computer even starts counting them.

---

## How it Works:

**Look Ahead:** While the computer is scanning the database to count single items (finding L1), it performs an extra task: it looks at every transaction and creates all possible pairs (2-itemsets) from that transaction.

**The "Bucket" System (Hashing):** Instead of keeping a giant list, the computer "hashes" (maps) these pairs into different buckets in a hash table.
The Filter: Each time a pair is hashed into a bucket, the "bucket count" goes up.

**The Pruning Rule:** If a bucket's total count is lower than the minimum support threshold, the computer knows that none of the pairs inside that bucket can possibly be frequent.

**The Result:** By using this technique, the computer can ignore entire groups of pairs at once. This substantially reduces the number of candidate 2-itemsets (C2) that the computer has to examine in the next step.

---

## Slide 17: The Hash-Based Technique (Visual Example)

This slide provides a mathematical example of a Hash Table (H2) used for candidate 2-itemsets.

**The Hash Function:** The computer uses a specific formula to decide which bucket a pair belongs to. In this example, the formula is:
h(x,y)=((order of x)×10+(order of y))(mod7).

**The Table Structure:**

**Bucket Address:** The slots in the table (numbered 0 to 6).

**Bucket Contents:** The specific pairs (like {I1,I2} or {I2,I3}) that were assigned to that slot by the formula.

**Bucket Count:** How many times pairs landed in that specific slot.

**Decision Making:** If your threshold (minsup) was, for example, 3, the computer would look at Bucket 0 (which only has a count of 2) and immediately throw away the pairs {I1,I4} and {I3,I5} without even checking the main database for them.

---

## Summary

Think of the Hash-based technique like sorting mail into cubby holes. Instead of the computer reading every single envelope one-by-one, it throws all the envelopes into 7 different boxes. If a box is nearly empty, the computer knows there aren't enough "popular" letters inside to bother opening them. This lets the computer focus only on the "heavy" boxes that actually have a chance of containing frequent patterns.


---

# Key notes from Tchel Hsu Myat Mo



