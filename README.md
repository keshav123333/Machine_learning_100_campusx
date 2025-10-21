# Machine_learning_100_campusx

to open in github github.com replace by colab.research.google.com/github

    1. np.where(condition, value_if_true, value_if_false)
    2. df['cabin_num'] = df['Cabin'].str.extract('(\d+)') use in notebook /Feature_Engineering/Columnhv_num_alphabets__both_Important_useofapplylabmda
    3. and lambda ka use bhi on df ke liye https://github.com/keshav123333/Machine_learning_100_campusx/tree/main/Feature_Engineering/Columnhv_num_alphabets__both_Important_useofapplylabmda


# if else for use ka rule 

---

### 🧩 Rule:

| Type            | Allowed position | Meaning                                                |
| --------------- | ---------------- | ------------------------------------------------------ |
| ✅ `if`          | after `for`      | filtering (include only if condition true)             |
| ✅ `if ... else` | before `for`     | conditional expression (decide value for each element) |
| ❌ `if ... else` | after `for`      | ❌ Syntax error hota hai                                |

---

### 🧠 Example 1 – `if` after `for` (✅ allowed)

```python
nums = [1, 2, 3, 4, 5]
even = [x for x in nums if x % 2 == 0]
print(even)
```

**Output:**

```
[2, 4]
```

➡️ Yahaan `if` filtering kar raha hai — bas wahi elements rakhe jaha condition true hai.

---

### 🧠 Example 2 – `if ... else` before `for` (✅ allowed)

```python
nums = [1, 2, 3, 4, 5]
modified = [x if x % 2 == 0 else 0 for x in nums]
print(modified)
```

**Output:**

```
[0, 2, 0, 4, 0]
```

➡️ Yahaan `if...else` har element ke liye check karta hai aur naya value decide karta hai.

---

### ❌ Example 3 – `if ... else` after `for` (❌ invalid)

```python
nums = [1, 2, 3, 4, 5]
[x for x in nums if x % 2 == 0 else 0]  # ❌ error
```

➡️ Ye syntax error dega:

```
SyntaxError: invalid syntax
```

---

### ✅ Summary (yaad rakhne ka shortcut):

| Pattern                             | Meaning     | Valid? |
| ----------------------------------- | ----------- | ------ |
| `[x for x in items if cond]`        | Filter      | ✅      |
| `[x if cond else y for x in items]` | Conditional | ✅      |
| `[x for x in items if cond else y]` | ❌ Invalid   | ❌      |

---

So bhai seedha rule yaad rakh:

> 🔥 “`if` → baad me lagta hai filter karne ke liye,
> `if-else` → pehle lagta hai value choose karne ke liye.”

Chaahe mai ek diagram bana du (timeline-style) jisse ye structure visually samajh aa jaye?


# Search in dataframe
df[(df["age"] == 32) & (df["family"] == 1)]
df[df["joker"]=="op"]["parents"] aise bhi use kar sakte 


# Iterate through df 

blanks=[]
for index,text in df["merged_text"].items():
  if isinstance(text, str) and text.isspace():
    blanks.append(index)
        
blanks     
