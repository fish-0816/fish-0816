## Hi there 👋

<!--
**fish-0816/fish-0816** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
我把“科研搜集列表”理解为 **fish-0816 公开 Star 中与科研数据集、无线感知及相关代码有关的仓库**。你的个人仓库 README 本身没有列出这份清单；以下是从公开 Star 仓库中筛出的相关项目。Star 数是查询时 GitHub 返回的仓库 Star 总数，不是你给它们的个人评分；数据下载链接和访问条件可能变化。

## 一览

| 仓库（Star 数） | 类型 | 研究主题 | 数据或代码开放情况 |
|---|---|---|---|
| [WiMANS](https://github.com/huangshk/WiMANS)（96） | 数据集 + 代码 | WiFi 多人活动感知 | 数据经 Kaggle 获取；代码在仓库中 |
| [WiFi-CSI-Sensing-Benchmark / SenseFi](https://github.com/xyanchen/WiFi-CSI-Sensing-Benchmark)（645） | 基准数据 + 代码 | WiFi CSI 人体感知 | 处理后数据和预训练权重提供外部下载；代码公开 |
| [XRF55](https://github.com/airslab2020/XRF55-repo)（78） | 多模态数据集 + 代码 | 室内动作分析 | 多种数据分批公开，部分数据暂不可用或仍在处理中 |
| [mmHSense](https://github.com/nisarnabeel/Multi-Modal-and-Distributed-mmWave-ISAC-Datasets-for-Human-Sensing)（22） | 数据集 + 代码 | mmWave ISAC 人体感知 | 数据通过 IEEE DataPort 获取；代码公开 |
| [mmAlert](https://github.com/lasso-sustech/mmAlert)（3） | 数据集 + 数据读取示例 | 60 GHz 被动目标跟踪与定位 | 数据通过 README 外部下载链接获取；有 Python 读取示例 |
| [RSSI Dataset](https://github.com/pspachos/RSSI-Dataset-for-Indoor-Localization-Fingerprinting)（84） | 数据集 | Zigbee、BLE、WiFi 室内定位 | 数据按 README 所述存放于仓库/项目目录；附实验说明 |
| [MILD](https://github.com/Intelligent-Perception-Lab/MILD)（7） | 数据集 | 多手机 WiFi 室内定位 | 需签署数据集协议后申请下载，并非免申请直接下载 |
| [HeteroGDL-Indoor-Localization](https://github.com/xdrl1/HeteroGDL-Indoor-Localization)（23） | 代码 + 数据集实验流程 | 异构图深度学习室内定位 | 代码公开；使用 SoLoc 和 Petros 两个数据集 |
| [MasterThesis_mmWavePI](https://github.com/MaksimKarnaukh/MasterThesis_mmWavePI)（1） | 代码与实验流程 | 5 GHz 与 60 GHz WiFi CSI 步态身份识别 | 仓库说明为自采数据研究；README 未显示可直接下载的数据包 |
| [Wi-Fi / SWS-Net](https://github.com/Coralinehh/Wi-Fi)（5） | 代码 | 脉冲神经网络 WiFi 感知 | 代码公开；实验数据需按 README 指引另行获取 |
| [SCAE-SNN-HAR](https://github.com/ele-ciccia/SCAE-SNN-HAR)（2） | 代码 + 数据处理流程 | 雷达 CIR 人体活动识别与 SNN | 使用外部 DISC 数据集；代码公开 |
| [WIFI-SCI-Indoor-Positioning](https://github.com/zhangleino1/WIFI-SCI-Indoor-Positioning)（154） | 代码项目 | WiFi CSI 室内定位 | 仓库描述提到 CSI 幅度、相位等；本次可见信息不足以确认其数据下载和许可证详情 |
| [Awesome-WiFi-CSI-Sensing](https://github.com/NTUMARS/Awesome-WiFi-CSI-Sensing)（1,147） | 论文、数据集、代码索引 | WiFi CSI 感知 | 资源汇编，不是单一数据集或算法实现 |

---

## 逐项介绍

### 1. WiMANS：WiFi 多人活动感知基准

**仓库：** [huangshk/WiMANS](https://github.com/huangshk/WiMANS)

这是一个同时包含 WiFi CSI 与同步视频的数据集和基准代码项目，适合研究多人场景下的**活动识别、位置识别和身份识别**。仓库 README 说明数据包含 **11,286 个样本**，并提供标注文件、原始 CSI、CSI 振幅和视频：

- `annotation.csv`：用户身份、位置、活动等标签。
- `wifi_csi/mat`：原始 CSI 样本。
- `wifi_csi/amp`：预处理后的 CSI 振幅。
- `video`：对应视频样本。

数据通过 [Kaggle 上的 WiMANS 数据集](https://www.kaggle.com/datasets/shuokanghuang/wimans)下载。代码提供 WiFi CSI 和视频两类基准实验，包括 MLP、CNN、LSTM、Transformer 等模型，任务包括 identity、location、activity。

**适合用途：** 多人 WiFi 感知、多模态对照实验，以及 CSI 与视频互补性研究。数据中含视频，使用和再发布时应特别留意数据集条款与参与者隐私。

### 2. SenseFi：WiFi CSI 感知基准和模型库

**仓库：** [xyanchen/WiFi-CSI-Sensing-Benchmark](https://github.com/xyanchen/WiFi-CSI-Sensing-Benchmark)

这是以 PyTorch 实现的 WiFi CSI 人体感知基准库，涵盖多种模型和多个常用数据集。README 列出的主要数据包括：

- **UT-HAR**：7 类活动，包含躺下、跌倒、行走、拾取、跑步、坐下、站立等。
- **NTU-Fi HAR**：6 类活动。
- **NTU-Fi HumanID**：14 名受试者的步态身份识别。
- **Widar**：22 类手势。

仓库还提供 MLP、CNN、ResNet、RNN、GRU、LSTM、CNN+GRU、ViT 等模型，支持监督学习和跨数据集的自监督实验。处理后数据和预训练权重通过 README 中的 Google Drive 链接提供；代码可直接在 GitHub 仓库查看。

**适合用途：** 对比不同神经网络架构、复现实验基线、快速熟悉 WiFi CSI 感知任务。使用时应按 README 中的数据划分与数据集说明复核实验设置。

### 3. XRF55：多无线信号室内动作数据集

**仓库：** [airslab2020/XRF55-repo](https://github.com/airslab2020/XRF55-repo)

XRF55 面向室内人体动作分析，数据涉及 **mmWave、WiFi、RFID**，并包括多种视频或人体表示。项目提供 **55 个动作类别**，范围涵盖日常动作、运动、交互动作及手势，例如行走、跑步、坐下、挥手、击掌、推拉和上下左右滑动等。

README 列出的数据资源包括：

- mmWave、WiFi、RFID 数据；
- mmWave 的 RA、RD、AD 图，以及部分点云；
- RGB、Depth、IR 视频；
- 训练代码、硬件教程和数据预处理说明。

数据分布在项目页、SDP 和 Kaggle 等外部平台。其中，README 标注部分 mmWave 原始数据链接已失效或暂不可用；2D/3D pose 与人体 mesh 当时仍在处理中。因此，**项目代码公开不代表所有模态数据当前都能完整下载**。项目主页为 [XRF55](https://aiotgroup.github.io/XRF55/)。

**适合用途：** 多模态动作识别、无线信号与视觉对比、不同无线传感模态融合。

### 4. mmHSense：多模态、分布式 mmWave ISAC 感知数据集

**仓库：** [nisarnabeel/Multi-Modal-and-Distributed-mmWave-ISAC-Datasets-for-Human-Sensing](https://github.com/nisarnabeel/Multi-Modal-and-Distributed-mmWave-ISAC-Datasets-for-Human-Sensing)

仓库提供面向 mmWave ISAC 人体感知任务的数据集框架和 PyTorch 代码，覆盖六项任务：

- `mmWGesture`：mmWave 手势识别；
- `5GmmGesture`：5G mmWave 手势识别；
- `mmWPose`：骨架姿态估计；
- `DISAC-mmVRPose`：VR 场景下的 mmWave 姿态估计；
- `mmW-Loc`：mmWave 定位；
- `mmW-GaitID`：步态身份识别。

数据由 IEEE DataPort 发布，README 给出了各任务数据文件的大致目录组织。代码支持分类和回归，使用 ResNet18 主干网络；定位和步态任务还可选择使用背景相减处理。README 标注数据集采用 **CC BY 4.0**，使用时仍应阅读数据页和论文中的完整引用要求。

**适合用途：** mmWave 感知多任务研究、分类与回归基线复现，以及背景相减对定位或步态识别的影响分析。

### 5. mmAlert：60 GHz 被动目标轨迹数据

**仓库：** [lasso-sustech/mmAlert](https://github.com/lasso-sustech/mmAlert)

mmAlert 的主题是通过协作被动感知，同时进行设备定位与目标跟踪。数据包含 **150 条轨迹记录**，覆盖三个场景；README 描述了使用两路 60 GHz 信号，记录被动移动目标运动，并提供：

- `.dat`：接收信号数据；
- `.tum`：Turtlebot 的真实轨迹。

实验设备包括 NI USRP-2954R SDR 与 Sivers 60 GHz 相控阵。README 提供用 NumPy 读取 `.dat` 信号和加载轨迹文件的示例，并声明数据采用 **CC BY 4.0**。由于数据体积较大，下载链接位于 README 的外部文件托管服务中；访问是否仍有效需以当前页面为准。

**适合用途：** mmWave 轨迹重建、被动目标跟踪、信号与轨迹真值对齐研究。

### 6. RSSI Dataset：Zigbee、BLE 和 WiFi 室内指纹定位

**仓库：** [pspachos/RSSI-Dataset-for-Indoor-Localization-Fingerprinting](https://github.com/pspachos/RSSI-Dataset-for-Indoor-Localization-Fingerprinting)

这是一个以 RSSI 为核心的室内定位数据集，覆盖三种无线技术：

- Zigbee（IEEE 802.15.4）；
- Bluetooth Low Energy；
- 2.4 GHz WiFi（IEEE 802.11n）。

数据来自三个不同房间，包括干扰较低、干扰较高及空间较大的实验场景。项目说明了 fingerprint、test point 和 path-loss 数据目录；每个点的数据记录信号发送端标识和 RSSI 值，坐标可由相应的 `.xlsx` 文件查阅。README 还介绍了三边测量、KNN 指纹定位和 Naive Bayes 等对比方法。

**适合用途：** 多无线制式 RSSI 指纹定位、环境干扰对定位的影响分析，以及传统定位方法对照。

### 7. MILD：多手机室内定位数据集

**仓库：** [Intelligent-Perception-Lab/MILD](https://github.com/Intelligent-Perception-Lab/MILD)

MILD 是一个使用真实商用手机采集的 WiFi 室内定位数据集。README 列出：

- **22 部手机，21 种设备类型**；
- **15 名志愿者**；
- RSSI、CSI、时间戳、信道和中心频率等信息；
- 由 UWB 提供的坐标，可作为定位真值。

它的特点是覆盖不同手机硬件与实际部署的 AP，旨在研究设备差异、真实通信包和接入点配置对定位的影响。需要注意：数据**不是公开页面上一键下载**。README 要求填写数据发布协议；中国研究者需加盖单位公章，其他地区研究者需由负责人签署，再向项目方提交申请。

**适合用途：** 跨设备泛化、真实商用终端 CSI/RSSI 定位、多手机与多人场景研究。引用时应遵守申请协议和数据集团队的要求。

### 8. HeteroGDL：基于图深度学习的室内定位代码

**仓库：** [xdrl1/HeteroGDL-Indoor-Localization](https://github.com/xdrl1/HeteroGDL-Indoor-Localization)

这是与 IPIN 2022 论文 *A Geometric Deep Learning Framework for Accurate Indoor Localization* 对应的公开代码。它不是单独的新数据集，而是提供数据读取、预处理和模型实验流程，README 中列出两个实验数据来源：

- **SoLoc**：README 链接到 University of Twente 的数据下载文件。
- **Petros**：指向上文的 RSSI 指纹数据集；此实现说明只使用其中的 Scenario 1 和 Scenario 3。

实现支持 WiFi、Bluetooth 以及多无线技术组合，预处理可生成图像、同构图或异构图，并比较 wkNN、SVM、MLP、CNN、GraphSAGE 等模型。

**适合用途：** 学习无线定位数据如何表达为图结构、对照传统机器学习与图神经网络，以及复现异构图室内定位实验。

### 9. MasterThesis_mmWavePI：5 GHz 与 mmWave 步态身份识别

**仓库：** [MaksimKarnaukh/MasterThesis_mmWavePI](https://github.com/MaksimKarnaukh/MasterThesis_mmWavePI)

该项目配套一项硕士论文研究，比较 **5 GHz WiFi CSI** 与 **60 GHz mmWave CSI** 对步态身份识别的适用性。README 描述使用商用设备同步采集两频段 CSI，并报告论文实验中 20 人识别任务的结果；项目也提供实验代码和数据处理流程。

README 所述的重点包括：60 GHz 数据使用 MikroTik wAP 60G 设备，5 GHz 数据使用 ASUS 路由器和 Nexmon CSI 工具；两组数据均使用 CSI 振幅信息。**本次查看到的 README 未提供可直接下载的数据集链接**，因此不能据此认定数据本身已公开提供。

**适合用途：** 研究频段、采样率、背景相减与步态身份识别性能的关系；若需要数据，应先检查仓库其他文件或向作者确认授权与下载条件。

### 10. SWS-Net：脉冲神经网络 WiFi 感知代码

**仓库：** [Coralinehh/Wi-Fi](https://github.com/Coralinehh/Wi-Fi)

该项目是论文 *Spiking-Aided Neural Architecture for Efficient and Robust WiFi Sensing* 的实现。它采用 ANN 与 SNN 混合架构，面向活动识别、身份识别和手势识别，输入包括 CSI 与 BVP。仓库还提供 CNN、LSTM、Transformer 等对照模型，并包含脉冲阈值和时间步数消融实验入口。

README 指向的实验数据包括：

- NTU-Fi HAR；
- NTU-Fi HumanID；
- Widar 3.0；
- 预处理后的 BVP 22 手势数据。

NTU-Fi 数据通过 Google Drive 获取，Widar 3.0 指向项目官网。数据文件被排除在 Git 版本控制之外，因此这是**公开代码仓库，不代表数据已包含在仓库内**。

**适合用途：** 比较 SNN 与常规神经网络在 WiFi 感知中的表现，特别是时间步、脉冲阈值与效率的影响。

### 11. SCAE-SNN-HAR：毫米波雷达 CIR 活动识别

**仓库：** [ele-ciccia/SCAE-SNN-HAR](https://github.com/ele-ciccia/SCAE-SNN-HAR)

这是用于复现论文 *Sparse Spike Encoding of Channel Responses for Energy Efficient Human Activity Recognition* 的代码。项目使用 DISC 数据集中的毫米波 **Channel Impulse Response（CIR）** 序列，README 描述数据约包含 40 分钟记录、7 名受试者和 4 类活动。

数据需要从 [IEEE DataPort 的 DISC 页面](https://ieee-dataport.org/documents/disc-dataset-integrated-sensing-and-communication-mmwave-systems)另行下载；随后由仓库中的 `dataset.py` 处理原始 CIR，训练代码和网络结构放在 `src` 中。也就是说，数据和代码分别托管，需按项目说明准备本地数据目录。

**适合用途：** 雷达 CIR 活动识别、稀疏脉冲编码与能耗效率研究。运行前需核对论文版本、数据集访问条件和项目依赖。

### 12. WIFI-SCI-Indoor-Positioning：WiFi CSI 室内定位代码项目

**仓库：** [zhangleino1/WIFI-SCI-Indoor-Positioning](https://github.com/zhangleino1/WIFI-SCI-Indoor-Positioning)

GitHub 仓库描述将其定位为基于深度学习的 WiFi CSI 室内定位项目，提到利用 CSI 的幅度、相位和环境信息提升定位精度。本次获得的仓库信息足以确认其研究方向和 Python 实现，但未读取到可核实的 README 详情，因此**数据集来源、具体算法、实验配置、许可证与数据下载方式均不在此作推断**。建议优先查看该仓库当前 README、LICENSE 和数据目录说明。

**适合用途：** 作为 WiFi CSI 定位项目的候选参考；在复现或将数据用于其他研究前，先确认数据来源与授权。

### 13. Awesome WiFi CSI Sensing：论文、数据集与代码索引

**仓库：** [NTUMARS/Awesome-WiFi-CSI-Sensing](https://github.com/NTUMARS/Awesome-WiFi-CSI-Sensing)

这不是单个数据集或算法，而是按研究任务整理的 WiFi CSI 感知资源清单，包含论文、数据集、代码库和 CSI 采集工具。主题覆盖活动识别、身份识别、手势、跌倒检测、生命体征、姿态估计、室内定位及多模态感知等。

其数据集部分列出 MM-Fi、NTU-Fi、Widar 3.0、WiAR、UT-HAR、SignFi 等；代码部分列出 SenseFi、EfficientFi、CSI-Net、SignFi 等项目。它适合作为**进一步找数据和基线代码的导航入口**，但清单中链接的可用性、许可证和版本需要逐个到原项目确认。

## 按研究方向快速选择

- **WiFi CSI 活动识别基准：** WiMANS、SenseFi、Wi-Fi/SWS-Net。
- **多人感知或多模态：** WiMANS、XRF55、mmHSense。
- **mmWave 雷达/ISAC：** mmHSense、mmAlert、SCAE-SNN-HAR。
- **室内定位：** RSSI Dataset、MILD、HeteroGDL、WIFI-SCI-Indoor-Positioning。
- **步态身份识别：** SenseFi 的 NTU-Fi HumanID、MasterThesis_mmWavePI、mmHSense 的 mmW-GaitID。
- **找更多 WiFi CSI 论文、数据和代码：** Awesome-WiFi-CSI-Sensing。

**开放程度上最需要留意的三类情况：** MILD 需签协议申请；MasterThesis_mmWavePI 的 README 未确认可直接下载数据；XRF55 的部分数据模态在 README 中标注为暂不可用或尚未发布。
