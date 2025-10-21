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

      df["merged_text"]=df["merged_text"].apply(clean_text)
      # this helps in like clean_Text ek function banya jo text as input 
      leta and so apply se laga sakte hai 


# How to download image text from web using request 
          import requests

                    url = "https://storage.googleapis.com/kagglesdsdata/datasets/829469/1417158/skull-icon.png?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=databundle-worker-v2%40kaggle-161607.iam.gserviceaccount.com%2F20251021%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20251021T131303Z&X-Goog-Expires=345600&X-Goog-SignedHeaders=host&X-Goog-Signature=680624734852b1133a91f5fe073e183caad9700da0d93bd89568ad73bfea4410d542f9b845349bd307968ea67b7a53c2eae83cb1c8e9dcf96ec020c4fbb26ba034233ebb50b54129b97d8e174ae44c2ca1843bee75d7af8432238da681745deebb8a813d9b0bc30943d60c16554c51d32e77536a83e3e2be628a06ea3f66c8f8e932b81cc48222f2d5d8a39c8ae86344d4a38dc3602d116186c6331837e30f24b60017b663b1a0ef70ae036016d7dde9f44408c106a64344fa76be3791d0e8e4004b67061eabcc2ad5912504f217ac7331d511b2550573a61f45d440d108b2a04de73ff2a32eca3d64a47ded26254bd515d6a66eaa2a512c2f23e2a668445641"

            r = requests.get(url)
            with open("skull-icon.png", "wb") as f:
                f.write(r.content)
      
