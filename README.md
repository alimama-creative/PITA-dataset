# PITA-dataset
Dataset for paper: T-Stars-Poster: A Framework of Product-Centric Advertising Image Design (CIKM2025)

The dataset can be download [here]("https://tianchi.aliyun.com/dataset/209898")

## Description
The PITA dataset is about product-centric advertising image design, and it contains 38,017 records. The PITA dataset is provided by Alibaba.

## Documents

### Overview/Background

PITA can be used for the automated design of e-commerce advertising images.

### Dataset Description

PITA contains 38,017 pieces of data collected from e-commerce platforms and the CGL dataset, with 1,000 pieces used for testing. During the collection process, images with messy backgrounds, solid colors without shadows, unappealing stickers, close-ups, poorly presented taglines,or cluttered elements were excluded. Each image is annotated with prompts (foreground and background captions), a product mask, and a layout of graphic and nongraphic elements. product mask, and a layout of graphic and nongraphic elements. Each element is represented with a type and a bounding box (bbox). Graphic elements contain "Logo", "Tagline", and "Underlay". Initial annotations are generated using automatic methods such as DAMO Academy's matting API for foreground extraction, GPT-4o for image captioning, an internal detection model and Grounding-DINO for element detection, and an internal OCR model for tagline extraction.

#### Format

- PITA/
    - ori_imgs/
        - train
        - test
    - masks/
        - train
        - test
    - train_data.jsonl
    - test_data.jsonl


Each piece of data in the jsonl file includes the following annotation information:
--img_path (original image path),
--mask_path (path of the product mask image),
--img_wh (width and height of image),
--foreground prompt (foreground caption),
--background prompt (background caption),
--nongraphic_layout (layout of nongraphic elements),
--graphic_layout (layout of graphic elements),
--allow_occlude (whether the product is allowed to be occluded, for example, products with models are allowed to be occluded). 
Among them, the bbox in the layout is in the form of [left, top, right, bottom] coordinates normalized to the range of 0-1.




## 描述 
数据集PITA适用于以商品为中心的电商广告图片设计任务，它包含38,017条记录，由阿里巴巴集团提供。

## 文档

### 概述
PITA可用于自动化电商广告图片设计

### 数据集介绍
PITA包含从电商平台和CGL数据集搜集而来的38,017条数据，其中一千条用于测试。在收集过程中，排除了背景杂乱、纯色且无阴影、贴纸不吸引人、特写镜头、标语展示不佳或元素杂乱的图像。每张图像都标注有提示（前景和背景描述）、产品掩码以及图形和非图形元素的布局。每个元素都用类型和边界框（bbox）表示。图形元素包含“Logo”、“标语”和“衬底”。初始标注是通过一些自动方法生成的，例如达摩院的抠图API用于前景提取、GPT-4o用于图像描述、内部检测模型和Grounding-DINO用于元素检测，以及内部OCR模型用于标语提取。然后人工对标注进行审核和校正以确保准确性。

#### 格式

- PITA/
    - ori_imgs/
        - train
        - test
    - masks/
        - train
        - test
    - train_data.jsonl
    - test_data.jsonl

jsonl文件中的每条数据包括以下标注信息：
--img_path（原图路径）、
--mask_path（商品mask图片路径）、
--img_wh（图像宽高）、
--foreground prompt（图像前景描述）、
--background prompt（图像背景描述）、
--nongraphic_layout（非图形元素布局）、
--graphic_layout（图形元素布局）、
--allow_occlude（商品是否允许被遮挡，例如有模特的允许被遮挡）

其中布局中的bbox是归一化到0-1之间的[left,top,right,bottom]形式坐标。
