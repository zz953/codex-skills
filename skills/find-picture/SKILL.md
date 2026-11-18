---
name: find-picture
description: Search a local photo collection for a reference subject or event participant, recover overlooked photos from group shots and adjacent frames, verify candidates, and copy requested originals. Use for photo folders, reference images, race bib numbers, and follow-up searches after user feedback.
---

# Find Picture

## 1. 建立清单和参考线索

- 识别照片来源、可递归搜索的范围、已确认照片、用户明确排除的例子及整理目录。用相对路径记录照片，避免不同相机或子目录的同名冲突。重跑前检查用户刚添加、移走或确认的照片。
- 从用户确认的照片提取线索。号码布保留队号和前导零，同一参与者的不同日期、场景和装备各自记录。用户圈出的区域是位置标注，参考图中的其他人和背景只作为场景线索。
- 用 EXIF 原始拍摄时间和相机信息建立索引，按相机保留文件序号。遇到时钟偏差、序号跳号或缺少 EXIF，用相邻画面和重复场景核对，记录使用的替代时间。相邻编号和时间用于缩小范围。

## 2. 扫描和补查

- 先抽样运行，确认解码、旋转和号码布识别正常，再覆盖候选范围。可用 [RapidOCR](https://github.com/RapidAI/RapidOCR) 离线识别。保存已处理路径、结果和失败原因，支持分批续跑。第三方工具如 [RunnerBibTagger](https://github.com/chbornman/RunnerBibTagger) 可参考号码布检测，若其流程会写照片元数据，使用只读方案或工作副本。
- 保留 OCR 原文、位置与置信度。双行号码要求两行在同一号码布区域内。容许常见 OCR 混淆用来召回候选，再回看原图核对。不同队伍可以使用相同的个人号码。
- 优先补查已确认照片的前后连拍、同场景的其他相机和相邻拍摄点。以场景切换和时间间隔决定是否扩大范围。有圈注截图时，可用 [OpenCV 特征匹配](https://github.com/opencv/opencv/blob/5.x/doc/tutorials/features/feature_flann_matcher/feature_flann_matcher.markdown) 对齐原片或相近视角，随后在原片核对。位置投影只为定位局部。
- 对合照、远景和号码布遮挡的画面，先看缩略图定位，再在原始分辨率分块放大，保留块间重叠。对照同一时段的背包样式、外套、腿套或独特物件组合，核对人员位置、邻近队友和场景连续性。衣服颜色、同队人员或背景本身只够支持候选。条件合适时可用本地人脸相似度排序，仍需结合可见证据或用户反馈复核。
- 每次收到新确认的照片，把它们加入参考，再查它们带来的新时段、机位或装备线索。把用户明确排除的对象从匹配参考中移除，区分「图中这一位排除了」和「整张照片排除了」。

## 3. 整理并核对覆盖范围

- 给每个结果保留原片路径、可核查的依据及复核状态。按用户要求复制原始文件。遇到同名先比较内容，已有同内容就跳过，内容不同就保留两份并清楚命名。核对副本与源文件内容一致。只在用户要求时移动原片或写入其元数据。
- 按实际清单核对自动扫描、人工复核、此前已确认、处理失败和未检查的覆盖范围。报告新增数量和保存位置，区分已确认结果与仍有遮挡或线索不足的候选。自动覆盖全库不能证明已找齐，只有实际逐张复核过才报告「逐张人工核验」。
