# vocToCocoByPaddle
这个项目主要用来利用百度飞浆库将VOC格式的数据转换成COCO数据集的格式。

这是我第一次用这个readme文件

首先第一步数据集的准备，数据集的格式如下

  * 1、Annotations 文件夹，主要用于存放图片文件标注的.xml文件
  
  * 2、ImageSets/Main 里面主要包含了各种训练、验证、测试图片名称的txt文件
  
  * 3、JPEGImages存放了所有训练照片


1、首先将所有的照片放在JPEGImages文件里面，将所有标注的XML文件放在Annotations的位置里面

2、现在目的是要生成ImageSets/Main里面的各种训练、验证、测试的txt文档，此时运行xml_to_voc.py

  * 1、将xmlfilepath填写成Annotations的绝对路径
  
  * 2、txtsavepath填写成ImageSets/Main的绝对路径
  
  * 最终将生成ImageSets/Main里面的各种txt文件，至此已经完成了所有VOC格式数据的准备

3、准备百度飞浆所需要的VOC数据集

  * 这一部分主要参考[数据集准备](https://github.com/PaddlePaddle/PaddleDetection/blob/release/0.4/docs/tutorials/PrepareDataSet.md "悬停显示")
  * 注意这一步一定要增加一个label_list.txt，里面主要包含了每个类别的名称

4、利用paddle进行格式的转换

```pyhton

  python tools/x2coco.py --dataset_type voc \
        --voc_anno_dir path/to/VOCdevkit/VOC2007/Annotations/ \
        --voc_anno_list path/to/VOCdevkit/VOC2007/ImageSets/Main/trainval.txt \
        --voc_label_list dataset/voc/label_list.txt \
        --voc_out_name voc_train.json     
```
