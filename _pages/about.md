---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

大家好！我是 **黄静**，目前是本科三年级，就读于[武汉大学国家网络安全学院](https://cse.whu.edu.cn/)信息安全专业。

我对人工智能充满热情，自入学以来，积极参与各类科研项目和学术竞赛，曾获得国家励志奖学金和多项校内外奖项。在科研方面，我参与并主导了多个项目，包括但不限于**时序点过程**、**计算机视觉**、**人工智能安全**、**序列建模**等领域。

# 🎓 Education Background

- **成绩均分：** GPA：3.91/4.0、加权平均分：92.11/100  
- **排名：** GPA排名：**10/146 (6.8%)**    
- **语言能力：** 以良好成绩通过 CET4、CET6(其中CET6-552)；具备良好的英语文献阅读和写作能力  
- **核心课程：** 高等数学 (96,90)、线性代数 (90)、概率论与数理统计 (95)、数据结构 (92,92)、离散数学 (92)、信息安全数学基础 (94)、计算机网络 (95)、密码学 (97,94)、软件安全 (95)、安全创客实践 (96)  
- **编程能力：** 编程常用语言为 C++、Python，熟悉算法与数据结构，代码风格良好；熟练掌握 PyTorch、Numpy、Pandas、OpenCV，熟悉各类深度学习模型及其编程实现；具备优秀的编程、建模能力，多次获数学建模/数据挖掘(kaggle)类比赛奖项  
- **开发工具：** VS Code，PyCharm，Jupyter Notebook，LaTeX (Overleaf)，Git  
- **在校荣誉：** 曾获国家励志奖学金、武汉大学甲等奖学金(5%)、武汉大学三好学生(10%)、武汉大学优秀学生干部、武汉大学优秀共青团员及多项竞赛奖金，在校累计获奖逾30000元  

# 🔥 News

# 📈 Research Experience-Temporal Point Process

## **💡 BregmanADMM-用于时序点过程中事件分支推断的即插即用模块**  

- **时间：** 2024.2 - 2024.8  
- **领域：** **时序点过程**，**最优传输**  
- **角色：** 第三作者  
- **研究背景：**  
  1. **时序点过程 (TPPs)** 是对连续时间域上离散事件点进行建模的强大工具，已被广泛用于地震预测、金融分析、推荐系统等多个领域。
  2. 对于事件序列，通常存在一个分支过程来捕获隐藏在序列中的事件级触发模式，这个分支过程提供了对事件之间因果关系的洞察，帮助我们识别触发后续事件级联的关键事件，这对于揭示事件产生和信息扩散的潜在机制至关重要。
  3. 推断事件分支有着重要意义，但其同样十分具有挑战性，因为事件分支是在实践中无法观察到的潜在变量。
  4. 现有方法如经典TPP（例如Hawkes Process）的EM框架或神经TPP中的注意力图，往往存在过平滑问题，导致非结构化的事件分支。
  5. 目前亟需一种简单但有效的解决方案来准确推断各种TPP模型的结构增强事件分支。
- **我们的方法：**  
  1. **引入一个新的即插即用模块：** 基于Bregman交替方向乘子法(BADMM)的模块，用于在TPPs的最大似然估计框架中推断与事件序列相关的事件分支。
  2. **BADMM模块的关键特性：** 在行归一化的下三角矩阵上施加低秩和稀疏结构，使得在经典TPP的EM算法中能得出结构化的责任矩阵，同时也有助于神经TPP的注意力图生成。
  3. **事件分支的有效表征：** 结构化的责任矩阵和注意力图可以有效表征事件分支，提供关于事件产生和信息扩散机制的有价值见解。
- **项目成果：**  
  * 在合成数据和现实数据上的实验表明，将我们的BADMM模块插入到现有的TPP模型和学习范式中可以稳定提高模型的性能，并产出可解释的事件分支。
  * 论文已投稿至**AAAI 2025**(第三作者，第一本科生作者)&nbsp;<span style="font-size: 16px;">
      <a href="https://insistentyy.github.io/docs/AAAIhuangjing.png">[OpenReview]</a>

## **💡 使用可扩展非参数正则化学习结构增强时序点过程** 

- **时间：** 2023.11 - 2024.8  
- **领域：** **时序点过程**，**最优传输**，**可解释性**  
- **角色：** 第五作者（第二本科生作者）  
- **研究背景：**  
  1. 时序点过程(TPPs)作为一种强大的统计工具，通常被用于连续时间域的事件序列建模，捕获事件的生成机制并据此预测未来事件。近年来，递归神经网络(RNN)和Transformer等被应用于设计TPPs，催生了诸如RMTPP、THP、SAHP等方法。这些方法虽然有效，但往往忽视了事件序列中的潜在聚类结构。
  2. 在现实世界中，不同的事件序列因不同的生成机制属于不同的聚类，如不同疾病患者的入院行为、劳动者的职业发展轨迹等。忽略这些聚类结构可能导致模型错配，影响模型的可解释性和预测精度。
  3. 现有TPP混合模型尽管通过学习多个TPP来捕获聚类事件序列，但存在可伸缩性问题，模型复杂度与聚类数量呈线性关系。非参数方法虽然测量事件序列间的距离来进行聚类，但在扩展到新事件序列时表现不佳，且未对时间动态进行建模，难以应用于事件预测任务。
- **我们的方法：**  
  1. 我们提出了一种基于可扩展非参数聚类正则化器的结构增强TPP。该方法通过学习单个参数TPP并为其施加非参数聚类正则化来优化事件序列的嵌入结构。
  2. 为解决大规模应用的可行性问题，我们使用事件序列的子集构造小核矩阵，并通过Gromov-Wasserstein差异项对TPP进行正则化，实现计算复杂度与聚类数量无关。
  3. 我们的方法将参数与非参数TPP模型的优势结合，既能扩展到新出现的事件序列中，又能显著提高模型的预测精度和可解释性。
- **项目成果：**  
  * 我们的方法通过广泛的合成和实际数据集测试，展示了优于现有SOTA方法的性能。
  * 相关论文已完成，先前投稿于KDD 2024，Decision为Resubmit；现已完善并投稿(resubmit，录用率远高于常规track)于 KDD 2025(第五作者，第二本科生作者)&nbsp;<span style="font-size: 16px;"><a href="https://insistentyy.github.io/docs/KDDlongyujie.png">[OpenReview]</a></span>

---

## **💡 使用Granger因果一致性正则化学习多元时序点过程**

- **时间：** 2024.1 - 2024.5  
- **领域：** **时序点过程**，**Granger因果**，**可解释性**  
- **角色：** 共同第一作者  
- **研究背景：**  
  1. Granger因果关系被设计用于捕捉多元时间序列中的时间相关性，判断一个时间序列是否有助于预测另一个序列。它对多元时序点过程(MTPPs)中的实体间关系建模有重要作用。
  2. 在神经MTPPs中，虽然数据拟合和预测效果良好，但缺少Granger因果建模，导致模型的可解释性不足。例如在社交网络用户行为建模中，传统Hawkes过程可以推断用户之间的Granger因果关系，而神经MTPPs则不能明确捕捉这种关系，影响复杂分析任务的效果。
  3. 现有对神经MTPPs的Granger因果推断方法通常依赖积分或采样，计算复杂且对模型架构有限制。
- **我们的方法：**  
  1. 我们为MTPP设计了一种Granger因果一致性(GCC)正则化器，使其能推断实体之间的Granger因果关系图，并在不同事件序列上保持一致。
  2. GCC正则化器通过两种方式实现：两两均方误差(MSE)和Group-Lasso Loss，分别惩罚不同Granger因果图之间的差异，促使其具有稀疏一致的拓扑结构。
  3. 我们的方法兼容统计和神经MTPPs，且计算复杂度较低，能够显著提升模型性能和可解释性。
- **项目成果：**  
  * 论文已完成基本实验&nbsp;<span style="font-size: 16px;"><a href="https://insistentyy.github.io/docs/WWWoverleaf.png">[Overleaf截图和实验结果]</a></span>,正在完善实验和写作，预计投稿于 WWW 2025(共同一作)



# 🔍 Research Experience-Computer Vision and Security

## **💡 HaMonitorSentry - 高层建筑智能监测系统** <sub> &nbsp;&nbsp;[[项目主页]](https://mumuyeye.github.io/HaMonitorSentry/README.html) | [[项目代码]](https://github.com/mumuyeye/HaMonitorSentry)</sub>

- **时间：** 2023.1 - 2024.5  
- **领域：** **计算机视觉(目标检测)**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 当前高层危险监测系统存在[准确性差]、[鲁棒性弱]、[实时性不足]、[未针对复杂高层场景优化]等问题。相关算法（如复杂场景下的运动目标检测、小目标快速检测等）尚未成熟，亟需改进。此外，现有系统主要聚焦于高空抛物，缺乏对更多实际场景的适应。
- **我们的方法：**  
  1. **高空抛/坠物检测：** 提出类间距离知识蒸馏，并构建轻量化语义分割网络，精准识别建筑背景，定位潜在抛物区域。同时，在FairMOT网络中引入基于前景运动信息的Mask-Attention模块，提升检测效率，降低误检率。
  2. **高层危险行为识别：** 使用2D与3D网络结合的双流结构，通过双头自注意力机制融合时空信息，提高时空定位和高层动作识别精度，支持高帧率视频处理，实现实时警报。
- **项目成果：**  
  * 作为主力队员参加第17届中国大学生计算机设计大赛(中南地区赛)，以人工智能应用组第一名(1/314)的成绩进入全国总决赛&nbsp;<span style="font-size: 16px;">
      <a href="https://mumuyeye.github.io/docs/2024jishe.pdf">[中南地区赛第一名-证明]</a>
  </span>，并获得全国总决赛二等奖第一名&nbsp;<span style="font-size: 16px;">
      <a href="https://insistentyy.github.io/docs/AWARDjisheguoer.jpg">[获奖证明]</a>
  </span>

---

## **💡 FaceShield - 基于可逆神经网络的DeepFake溯源追踪系统**

- **时间：** 2023.11 - 2024.6  
- **领域：** **人工智能安全**，**计算机视觉(DeepFake)**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 随着人工智能时代的到来，DeepFake技术的快速发展导致虚假人脸生成和视频篡改的案例激增，严重威胁信息安全。当今的DeepFake检测技术尽管不断迭代，但仍存在鲁棒性差、难以溯源追踪的核心问题。
- **我们的方法：**  
  1. 利用可逆神经网络(INN)进行视频隐写与提取，提出了基于INN的DeepFake溯源追踪系统。我们将人脸信息隐写于视频的非人脸区域，受到攻击时可从该区域提取出人脸信息进行追踪。在流程中，我们首先通过人脸掩码信息对INN进行条件输入，限制隐写信息分布，并引入关系模块增强载体视频与秘密视频的关联。最终通过可逆Haar小波变换进行降采样，并将INN输出压缩至与载体视频同通道数量。
- **项目成果：**  
  * 作为主力队员参加2024年武汉大学信息安全竞赛暨第十七届全国信息安全竞赛，获得二等奖&nbsp;<span style="font-size: 16px;">
      <a href="https://cse.whu.edu.cn/info/2601/28351.htm">[获奖证明]</a>
  </span>


# 🧠 Research Experience-Other

## **💡 Google-American Sign Language Fingerspelling Recognition** <sub> &nbsp;&nbsp;[[比赛介绍]](https://www.kaggle.com/competitions/asl-fingerspelling)</sub>

- **时间：** 2023.5 - 2023.8  
- **领域：** **序列建模**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 全球有7000多万聋哑人士以及15亿听障患者，他们无法使用语音识别等AI技术。本次比赛旨在帮助聋哑人通过手指拼写替代键盘，使其能够与非手语人士更快交流。
- **我们的方法：**  
  1. **模型架构：** 使用改进版的Squeezeformer作为encoder，处理mediapipe信号而非语音信号；decoder为双层transformer。
  2. **置信度分数：** 用于识别损坏示例并进行后处理。
  3. **数据增强：** 使用CutMix、FingerDropout、TimeStretch等正则化模型。
- **项目成果：**  
  * 取得了0.662的Final Score，获得铜牌（118/1315）。  
  * &nbsp;<span style="font-size: 16px;">
      <a href="https://insistentyy.github.io/docs/AWARDGoogleASLlyj.png">[获奖证明]</a>
    </span>

---

## **💡 数据解读乡村发展** <sub> &nbsp;&nbsp;[[比赛论文]](https://insistentyy.github.io/docs/lunwenjishe.pdf)</sub>

- **时间：** 2024.3 - 2024.4  
- **领域：** **数据分析、数据挖掘**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 通过数据分析揭示人口、粮食等对乡村发展的影响，并为全球及中国乡村振兴提出建议。
- **我们的方法：**  
  1. **面板回归分析：** 研究各种农作物产量对粮食安全的影响。
  2. **文本挖掘：** 探讨农民工现状及问题，提出解决策略。
  3. **聚类可视化分析：** 研究饮食结构变化，保持农村饮食文化。
- **项目成果：**  
  * 作为主力队员参加第17届中国大学生计算机设计大赛并获中南地区赛二等奖。  
  * &nbsp;<span style="font-size: 16px;">
      <a href="https://insistentyy.github.io/docs/AWARDjisheshenger.jpg">[获奖证明]</a>
    </span>

---

## **💡 基于LSTM神经网络模型的空气质量预测研究** <sub> &nbsp;&nbsp;[[比赛论文]](https://insistentyy.github.io/docs/lunwenjishe.pdf)</sub>

- **时间：** 2024.3 - 2024.4  
- **领域：** **数学建模**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 通过分析PM2.5浓度和AQI指数变化，使用LSTM神经网络预测未来12天的空气质量。
- **我们的方法：**  
  1. **多步预测模型：** 使用交叉验证与RMSE评估模型效果，预测PM2.5浓度和AQI指数。
- **项目成果：**  
  * 作为主力队员参加第十五届“华中杯”大学生数学建模挑战赛并获二等奖。  
  * &nbsp;<span style="font-size: 16px;">
      <a href="https://insistentyy.github.io/docs/AWARDhuazhongbei.pdf">[获奖证明]</a>
    </span>

---

## **💡 从“堆盒子”到动态规划** <sub> &nbsp;&nbsp;[[项目主页]](https://www.bilibili.com/video/BV1ojKvehEuq) | [[项目代码]](https://github.com/mumuyeye/From-Stacking-Boxes-to-Dynamic-Programming)</sub>

- **时间：** 2022.1 - 2022.5  
- **领域：** **算法教学、算法可视化**  
- **角色：** 团队（主力成员）  
- **研究背景：**  
  1. 算法的抽象性阻碍了许多同学的学习，而通过算法可视化可以有效化抽象为具象，帮助理解。
- **我们的方法：**  
  1. 使用Python的数学动画引擎Manim制作算法可视化作品，编写3000余行代码，结合后期AI处理与剪辑，制作完成高质量可视化作品。
- **项目成果：**  
  * 作品在Manim社群及高校中推广，收获了良好反馈。


# 🏆 Competition Awards

- **中国大学生计算机设计大赛：全国二等奖** *国家级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDjisheguoer.jpg)   
- **Kaggle-American Sign Language Fingerspelling Recognition：铜牌** *国家级* 2023 &nbsp;&nbsp;[[证明]](..\docs\AWARDGoogleASLhj.png)
- **全国大学生数学竞赛：一等奖** *国家级* 2023 &nbsp;&nbsp;[[证明]](..\docs\AWARDshuxuejingsai.pdf)   
- **中国大学生计算机设计大赛 (中南地区赛)：赛区第一名** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDjisheshengyi.jpg)  
- **中国大学生计算机设计大赛 (中南地区赛)：二等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDjisheshenger.jpg)  
- **湖北省大学生数学竞赛：一等奖** *省部级* 2023 &nbsp;&nbsp;[[证明]](..\docs\AWARDshuxuejingsai.pdf)  
- **“华中杯” 大学生数学建模挑战赛：二等奖** *省部级* 2023 &nbsp;&nbsp;[[证明]](..\docs\AWARDhuazhongbei.pdf)  
- **“蓝桥杯”软件赛道 C++ 程序设计赛 (湖北赛区)：三等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDlanqiaobeiC.pdf)
- **“蓝桥杯”软件赛道 Web 应用开发赛 (湖北赛区)：三等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDlanqiaobeiWeb.pdf)       
- **中国高校计算机大赛-网络技术挑战赛(全国选拔赛)：三等奖** *省部级* 2024 &nbsp;&nbsp;[[证明]](..\docs\AWARDcccc.jpg)

# 🥇 Scholarships and Honors

- *2023.10* **国家励志奖学金** *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\guojia.jpg)  
- *2023.10* **武汉大学甲等奖学金** (获奖率：全校5%) *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\jiadeng.jpg)  
- *2023.10* **武汉大学三好学生** (获奖率：全校10%) *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\sanhaoxuesheng.jpg)  
- *2023.10* **武汉大学优秀学生干部** *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\youxiuxueshengganbu.jpg)  
- *2023.10* **武汉大学优秀共青团员** *武汉大学* &nbsp;&nbsp;[[证明]](..\docs\gongqingtuan.jpg)

# 📖 Educations

- **2021.9 - 至今**，本科生，武汉大学国家网络安全学院，专业：信息安全
