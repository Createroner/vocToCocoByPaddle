# vocToCocoByPaddle
这个项目主要用来利用百度飞浆库将VOC格式的数据转换成COCO数据集的格式。

这是我第一次用这个readme文件

首先第一步数据集的准备，数据集的格式如下

  1、Annotations 文件夹，主要用于存放图片文件标注的.xml文件
  
  2、ImageSets/Main 里面主要包含了各种训练、验证、测试图片名称的txt文件
  
  3、JPEGImages存放了所有训练照片


1、首先将所有的照片放在JPEGImages文件里面，将所有标注的XML文件放在Annotations的位置里面

2、现在目的是要生成ImageSets/Main里面的各种训练、验证、测试的txt文档，此时运行xml_to_voc.py
    
    
public static void main(String[]args){} //python
