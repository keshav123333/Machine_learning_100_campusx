Bilkul. **Class Weights** ka matlab hai **dataset ko bilkul change nahi karna**. Bas training ke time loss function ko bolna ki **minority class ki galti ki penalty zyada lagao**.

---

# Example

Maan lo dataset hai

```
Class 0 (Normal)     = 1000 images
Class 1 (Jaundice)   = 100 images
```

Normally loss hota hai

```
Normal image wrong  -> Loss = 1
Jaundice image wrong -> Loss = 1
```

Model sochega

> "Normal to waise bhi bahut hain."

Isliye minority ignore ho sakti hai.

---

## Class Weight ke baad

Suppose

```
weight(class0)=1

weight(class1)=10
```

Ab

```
Normal wrong

Loss = 1 × loss
```

lekin

```
Jaundice wrong

Loss = 10 × loss
```

Ab model minority ko ignore nahi karega.

---

# Weight ka formula

Generally

[
Weight_i=\frac{Total\ Samples}{Number\ of\ Classes\times Samples_i}
]
1. Class Weights (Traditional)

Weight formula:

w
i
	​

=
C×n
i
	​

N
	​


Yahan:

N = total samples
C = number of classes
n
i
	​

 = class i ke samples
Example

```
Total = 1100

Classes = 2
```

Normal

```
1100/(2×1000)

=0.55
```

Disease

```
1100/(2×100)

=5.5
```

to

```python
class_weight={
    0:0.55,
    1:5.5
}
```

---

# TensorFlow / Keras

Bas `model.fit()` me pass karna hota hai.

```python
class_weight = {
    0: 0.55,
    1: 5.5
}

model.fit(
    train_dataset,
    epochs=20,
    validation_data=val_dataset,
    class_weight=class_weight
)
```

Aur kuch change nahi karna.

---

# Agar 3 Classes hain

Example

```
Normal      = 500

Bacterial   = 100

Viral       = 50
```

Weights

```
Total = 650

Classes = 3
```

Normal

```
650/(3×500)=0.43
```

Bacterial

```
650/(3×100)=2.16
```

Viral

```
650/(3×50)=4.33
```

```python
class_weight={
    0:0.43,
    1:2.16,
    2:4.33
}
```

---

# Automatically calculate

Suppose labels hain

```python
y_train
```

To

```python
from sklearn.utils.class_weight import compute_class_weight
import numpy as np

classes = np.unique(y_train)

weights = compute_class_weight(
    class_weight="balanced",
    classes=classes,
    y=y_train
)

class_weight = dict(zip(classes, weights))

print(class_weight)
```

Output

```python
{
    0:0.55,
    1:5.5
}
```

---

# PyTorch

Loss function me weight pass karte hain.

```python
import torch
import torch.nn as nn

weights = torch.tensor([0.55, 5.5], dtype=torch.float)

criterion = nn.CrossEntropyLoss(weight=weights)
```

Bas itna hi.

Training loop same rahega.

---

# Ye internally kya karta hai?

Normal `CrossEntropyLoss`:

```
Loss = 0.20
```

Agar minority class ka weight 5.5 hai

```
Final Loss

= 5.5 × 0.20

= 1.10
```

Optimizer ko lagega ki ye error bahut bada hai, isliye model minority class ko sahi predict karne ki zyada koshish karega.

---

## Kab use karna chahiye?

* ✅ Dataset mildly ya moderately imbalanced ho (jaise 70:30, 80:20, 90:10).
* ✅ Tabular data aur image classification dono me use ho sakta hai.
* ✅ Jab tum original data ko modify nahi karna chahte.

Agar imbalance **bahut extreme** ho (jaise 1000:10 ya 10,000:20), to sirf class weights kaafi nahi hote. Aise cases me class weights ko **data augmentation (images)**, **weighted sampling**, ya **focal loss** ke saath combine karna zyada effective hota hai.
