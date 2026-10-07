# AI/ML

How does ChatGPT understand your assignment? How does Gemini put a photo of you in a Bugatti? Why is Stockfish unbeatable? The answer to all of this is Artificial Intelligence.

This domain is built for beginners — we only expect you to know a little Python. Start with the basics below, then pick the resources that match where you want to go.

---

## PS0 – ML as You Need It

PS0 has two parts. Do the reading in **Start here** (below) alongside it.

### Part A – The question set ([PS0_ML_as_you_need_it.pdf](./PS0_ML_as_you_need_it.pdf))
Eight pen-and-paper problems on the foundations: **neural networks**, **gradient descent**, **loss functions** and **basic ML ideas** (classification vs regression, parameters vs hyperparameters).  
Attempt it seriously guys,it builds the intuition everything else depends on. But it is **not compulsory**.

### Part B – Hyperparameter tuning ([cifar100_hyperparameter_tuning.ipynb](./cifar100_hyperparameter_tuning.ipynb))
A ready-made CNN that classifies the 100 object classes of CIFAR-100. The model code is given; **your job is to improve its validation accuracy by tuning hyperparameters.**

1. Open the notebook in [Google Colab](https://colab.research.google.com/) and switch to a GPU (**Runtime → Change runtime type → T4 GPU**).
2. Run Steps 0–4 once to get the **baseline** accuracy — the number to beat.
3. In Step 5, change **one hyperparameter at a time** (learning rate, dropout, augmentation, model size…) and write a short note on what you changed and why. Every run is logged automatically.
4. Use the results table and learning curves (Step 6) to spot what helps and what hurts.
5. When you're done, evaluate your best model on the test set **once** (Step 7).

Download your experiment log (`experiment_log.csv`) before the Colab session ends , Colab deletes files when it disconnects.

---

## Resources

### Start here
- [Basics of Python](https://youtu.be/rfscVS0vtbw?si=Kv6q34ubbendIE1f) – a complete beginner course; skip it if you're already comfortable with Python.  
- [Basics of ML](https://youtube.com/playlist?list=PLblh5JKOoLUICTaGLRoHQDuF_7q2GfuJF&si=ps_8ycqF-QAkyDgz) – **do this before getting into coding**; builds intuition for how ML actually works.  
- [Kaggle Learn](https://www.kaggle.com/learn) – short, hands-on courses. Slow but steady.  
- [3Blue1Brown – Neural Networks](https://www.youtube.com/watch?v=aircAruvnKk&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) – beautifully visual; the first 4 videos are enough.

### Frameworks & tools
- [Patrick Loeber – PyTorch](https://youtu.be/c36lUUr864M) – the researcher's favourite framework.  
- [Aladdin Persson – TensorFlow](https://www.youtube.com/playlist?list=PLhhyoLH6IjfxVOdVC1P1L5z5azs0XjMsb) – Google's own framework.  
- [Murtaza's Workshop – OpenCV](https://youtu.be/WQeoO7MI0Bs) – behind half the fancy computer-vision projects you see online.

### Go deeper
- [Stanford CS229 – Machine Learning](https://youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU) – the classic ML course.  
- [Stanford CS230 – Deep Learning](https://youtube.com/playlist?list=PLoROMvodv4rOABXSygHTsbvUz4G_YQhOb) – deep learning with a practical slant.  
- [Stanford CS231n – Computer Vision](https://youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv) – CNNs and vision, in depth.  
- [CampusX – 100 Days of Machine Learning](https://youtube.com/playlist?list=PLKnIA16_Rmvbr7zKYQuBfsVkjoLcJgxHH) – classical ML; optional but handy.  
- [CampusX – 100 Days of Deep Learning](https://www.youtube.com/playlist?list=PLKnIA16_RmvYuZauWaPlRTC54KxSNLtNn) – highly detailed but long; optional.  
- [DataTrek roadmap](https://www.linkedin.com/posts/mungoliabhishek81_datatrek-datascience-machinelearning-activity-7249659363592658944-92CR) – a broader data science roadmap to explore.

---

*More problem statements coming soon.*
