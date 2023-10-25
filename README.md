# YOLOv5-Tools

## general_json2yolo.py
COCO格式转YOLOv5格式

## 修改 CrowHuman 格式
注意：使用 *.sh 文件之前，最好 conda activate env 一下。看缺少什么安装包，在环境中安装，重新运行即可。

把原始下载的 CrowHuman 压缩包都放入 raw 中即可。

1、prepare_yolo_data.sh: 将转变为 yolo 数据集格式。

2、prepare_coco_data.sh: 将转变为 coco 数据集格式。其中：
在使用 prepare_coco_data.sh 之前，
+ 新建你要存放 CrowdHuman 的文件夹。包含 CrowdHuman/images/train、CrowdHuman/images/val、CrowdHuman/labels/train、CrowdHuman/labels/val
+ 要修改 gen_coco_stru.py 文件中的下面几行，为你的路径。

```python
# 数据集生成目录
to_train_img_path = '/home/adr/datasets/CrowdHuman/images/train/' 
to_val_img_path = '/home/adr/datasets/CrowdHuman/images/val/'
to_train_label_path = '/home/adr/datasets/CrowdHuman/labels/train/'
to_val_label_path = '/home/adr/datasets/CrowdHuman/labels/val/'
```

训练使用的 CrowHuman 的 yaml 文件可以对照着 coco 数据集的 yaml 写，或者 crowdhuman.yaml 文件里面的内容写都是可以的。

## check_yolov5_label_format.py
在各种格式转到YOLOv5格式之后，防止转换错误，最后检查一下，可视化一下标注结果。

## look_up_anchor.py
查看anchor的数值是多少

## voc2yolo.py
VOC格式转YOLOv5格式

## 混淆矩阵
根据检测框和GT boxes输出混淆矩阵（TP，FN，FP，TN）据此可以计算模型指标
实现文件general.py
使用方法confusion_matrix_test.py


## widerface2yolo.py
widerface人脸数据集转yolov5格式
