import torch
import torch.nn as nn

samples_per_class = torch.tensor(
    [5000,1200,300,40],
    dtype=torch.float
)

beta = 0.9999

weights = (1-beta)/(1-torch.pow(beta,samples_per_class))

weights = weights / weights.sum() * len(samples_per_class)

weights = weights.cuda()

criterion = nn.CrossEntropyLoss(weight=weights)



<img width="614" height="157" alt="image" src="https://github.com/user-attachments/assets/3fdb04f7-ffa1-44c8-ae4d-349e6705435b" />
 aur bhi tarike ke  imbalance handling tecnique hoti hai 


 <img width="731" height="242" alt="image" src="https://github.com/user-attachments/assets/c9de1e58-baa0-4590-bea9-b7150fce8a67" />
