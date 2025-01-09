# HFADN
Implementation of **HFADN**, from the following paper:

Hierarchical Feature Alignment Network towards Effective and Robust Real Image Deraining

Zhuo Su, Xin Li, Zhe Huang, Yuxin Feng, and Fan Zhou 

<img src=".\image\Method Framework_00.png" alt="Method Framework_00" style="zoom: 50%;" />



#### Datasets

------

Based on our proposed "rain image imaging model", as shown in following picture, we synthesis a large-scale rain dateset, named **MIRain**. You can download  the dataset from the [Link](https://drive.google.com/drive/folders/1vv1qCYrmO-tVnJzUM8XZ4jMjFP92iqtM?usp=drive_link).

<img src=".\image\2.PNG" alt="2" style="zoom:67%;" />



#### Training/Evaluating for teacher/student network

------

1. Set training parameters in `settings_rainset.py/settings_rainset_real.py`;

2. Make sure that your dataset arranged in the following format, corresponding images in **Rain** and **GT** folder have the same names:

   `——dataset_path:`

   ​		`——Rain`

   ​				`——1.png`

   ​		`——GT`

   ​				`——1.png`

3. **Training**:

   When training for the real data, you should set the `real_dir=yourreal data path` in `settings_rainset_real.py`

   ```python
   python train_rainset.py # traing the teacher network
   python train_rainset_real.py # training the student network
   ```

4. **Evaluate**:

   When evaluating for the real data, you should change the parameter`pic_is_pair=False` and set the `data_dir` in `settings_rainset.py/settings_rainset_real.py`

   ```python
   python eval_rainset.py # traing the teacher network
   python eval_rainset_real.py # training the student network
   ```

#### Other

------

- [Trained models](https://drive.google.com/drive/folders/1D9N39T5aOSapGdb6TjApm5i2ZbOGtTZb?usp=drive_link)
- [Testing  results](https://drive.google.com/drive/folders/1P1A6YImnrgQVlhbmru01hr09mwxzOhsD?usp=drive_link)



