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
 **Download Image**
          import requests

                    url = "https://storage.googleapis.com/kagglesdsdata/datasets/829469/1417158/skull-icon.png?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=databundle-worker-v2%40kaggle-161607.iam.gserviceaccount.com%2F20251021%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20251021T131303Z&X-Goog-Expires=345600&X-Goog-SignedHeaders=host&X-Goog-Signature=680624734852b1133a91f5fe073e183caad9700da0d93bd89568ad73bfea4410d542f9b845349bd307968ea67b7a53c2eae83cb1c8e9dcf96ec020c4fbb26ba034233ebb50b54129b97d8e174ae44c2ca1843bee75d7af8432238da681745deebb8a813d9b0bc30943d60c16554c51d32e77536a83e3e2be628a06ea3f66c8f8e932b81cc48222f2d5d8a39c8ae86344d4a38dc3602d116186c6331837e30f24b60017b663b1a0ef70ae036016d7dde9f44408c106a64344fa76be3791d0e8e4004b67061eabcc2ad5912504f217ac7331d511b2550573a61f45d440d108b2a04de73ff2a32eca3d64a47ded26254bd515d6a66eaa2a512c2f23e2a668445641"

            r = requests.get(url)
            with open("skull-icon.png", "wb") as f:
                f.write(r.content)



**Download text **

          re="https://raw.githubusercontent.com/kuemit/txt_book/refs/heads/master/examples/alice_in_wonderland.txt"
        with open("alice_in_wonderland.txt","w") as f:
          f.write(requests.get(re).text)


**Download text but in direct format**

    line=[]
    o=requests.get("https://raw.githubusercontent.com/kuemit/txt_book/refs/heads/master/examples/alice_in_wonderland.txt")
    line.append(o.text)


# np.where 
 np.where(condition, value_if_true, value_if_false)
 
    df1["cgpa"] = np.where(
        df1["cgpa"] > upper_limit, upper_limit,
        np.where(df1["cgpa"] < lower_limit, lower_limit, df1["cgpa"])
    )
4️⃣ df1["cgpa"] = ... ka matlab

np.where ek naya NumPy array return karta hai

Fir wo pandas column cgpa ko update kar deta hai

Matlab original df1["cgpa"] overwrite ho jata hai → ab ye capped values contain karega



# loc ka use 
1.        df['ismarried']=0;
          df.loc[
            df['Name'].str.contains(r'\b(Mr\.|Mister|Master|Mrs\.)\b',                        case=False, na=False),
            'ismarried'] = 1
          df.loc[df['Name'].str.contains("Mrs."), 'ismarried'] = 1

    
# Logistic regression
playlist ke video dekh le for better 


#boosting mein aur 

lgbm catboost xgboost bhi hote hai 


#important df

        kn=KMeans(n_clusters=4)
        kn.fit(df)
        pred=kn.predict(df)
        
        df[ypred==0].iloc[:,0] 

yaha pe pred m kuch ek array jo 0 1 2 contin maine pre==0 vaha ka index lya and then df ka vo index le lye yaha pe pred naam ka koi col ni hai df m b twork kar raha hai kmean cluster wala repo dekh as [] ye index based hota hai and df[ypred==0].iloc[:,0] humne jo df aaya usme se first col utha liya 



#3d plot

px.scatter_3d(x=,y=,z=, colour)

aur padh iske baare mein


# index


you can use like 45 kaunse index in array list so list.index(45) aise kar sakte hai tu 

euclidain dist short cut
            
            np.sqrt(np.dot(b-a,b-a))


#np.all()
so yaha pe if ek bhi false so false 

       if np.all([1,2,3,4]==[1,2,3,4]):
      print("true")

# isinstance 
    blanks=[]
    for index,text in df["merged_text"].items():
      if isinstance(text, str) and text.isspace():
        blanks.append(index)
    
    blanks

# stopwords 
    list1=nlp.Defaults.stop_words
    list2=stopwords.words("english")
    Stopwords=set((set(list1)|set(list2)))
    print(len(Stopwords))


# random created example ke liye 

    x=np.random.randint(0,100,size=(50,3))
    x=pd.DataFrame(df,columns=['f1','f2','f3'])

    uniform_data = np.random.randint(0, 100, size=(50, 3))

    # 2) Normal distribution (mean = 0, std = 1)
    normal_data = np.random.normal(loc=0, scale=1, size=(50, 3))
    
    # 3) Random numbers between 0 and 1
    zero_to_one_data = np.random.rand(50, 3)



# flatten 
chagpt kar .flatten .view ka use 
.ravel bhi falt withput copying 


#bincount 

💡 Example 1 (सबसे आसान)
import torch

x = torch.tensor([2, 2, 3, 0, 3])
torch.bincount(x)


Step-by-step:

नंबर 0 कितनी बार आया? → 1 बार

नंबर 1 कितनी बार आया? → 0 बार

नंबर 2 कितनी बार आया? → 2 बार

नंबर 3 कितनी बार आया? → 2 बार

Output:

tensor([1, 0, 2, 2])


बस यही है bincount.



#groupby and map ka use 

        artist_pop = df.groupby('artist_name')['popularity'].mean()
        df['artist_avg_pop'] = df['artist_name'].map(artist_pop)
        

  2️⃣ Same kaam transform() se (🔥 MOST IMPORTANT)

        df['artist_avg_pop'] = (
            df.groupby('artist_name')['popularity']
              .transform('mean')
        )

🔎 Difference?

map = 2 step

transform = 1 step

Index mismatch ka tension nahi

📌 Interview + Kaggle favorite
📌 Recommended approach


           artist_stats = df.groupby('artist_name')['popularity'].agg(
            avg_pop='mean',
            max_pop='max',
            min_pop='min'
        )
        
        df['artist_avg_pop'] = df['artist_name'].map(artist_stats['avg_pop'])
        df['artist_max_pop'] = df['artist_name'].map(artist_stats['max_pop'])

#Map with dict 
        
        balanced_df=balanced_df["label"].map({"spam":1,"ham":0})




# Transform 

        # df["is_hit"] = (
    #     (df["track_popularity"] >= f) &
    #     (df["artist_followers"] >= follw) &
    #     (df["artist_popularity"] >= artistpop)
    # ).astype(int)

#use loc and index 

                  df.loc[(df["explicit"]==True) & (df["track_number"]==6),                                              ["artist_followers","track_number","explicit"]]
              df[(df["explicit"]==True) & (df["track_number"]==6)][["explicit"]]
