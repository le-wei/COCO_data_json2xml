# COCO_data_json2xml
把COCO数据集的josn标注转变成VOC数据集xml格式的标注；json数据标注转xml数据标注；把coco数据集json格式转变单张图片对应的xml格式
主要是以目标检测为列进行的
### COCO数据集json格式样本
```
{"info": {"description": "COCO 2017 Dataset","url": "http://cocodataset.org","version": "1.0","year": 2017,"contributor": "COCO Consortium","date_created": "2017/09/01"},"licenses": [{"url": "http://creativecommons.org/licenses/by-nc-sa/2.0/","id": 1,"name": "Attribution-NonCommercial-ShareAlike License"}],
"images": [{"license": 4,"file_name": "000000397133.jpg","coco_url": "http://images.cocodataset.org/val2017/000000397133.jpg","height": 427,"width": 640,"date_captured": "2013-11-14 17:02:52","flickr_url": "http://farm7.staticflickr.com/6116/6255196340_da26cf2c9e_z.jpg","id": 397133},{"license": 1,"file_name": "000000037777.jpg","coco_url": "http://images.cocodataset.org/val2017/000000037777.jpg","height": 230,"width": 352,"date_captured": "2013-11-14 20:55:31","flickr_url": "http://farm9.staticflickr.com/8429/7839199426_f6d48aa585_z.jpg","id": 37777}],
"annotations": [{"segmentation":[[510.66,423.01,511.72,420.03,510.45,416.0,510.34,413.02,510.77,410.26,510.77,407.5,510.34,405.16,511.51,402.83,511.41,400.49,510.24,398.16,509.39,397.31,504.61,399.22,502.17,399.64,500.89,401.66,500.47,402.08,499.09,401.87,495.79,401.98,490.59,401.77,488.79,401.77,485.39,398.58,483.9,397.31,481.56,396.35,478.48,395.93,476.68,396.03,475.4,396.77,473.92,398.79,473.28,399.96,473.49,401.87,474.56,403.47,473.07,405.59,473.39,407.71,476.68,409.41,479.23,409.73,481.56,410.69,480.4,411.85,481.35,414.93,479.86,418.65,477.32,420.03,476.04,422.58,479.02,422.58,480.29,423.01,483.79,419.93,486.66,416.21,490.06,415.57,492.18,416.85,491.65,420.24,492.82,422.9,493.56,424.39,496.43,424.6,498.02,423.01,498.13,421.31,497.07,420.03,497.07,415.15,496.33,414.51,501.1,411.96,502.06,411.32,503.02,415.04,503.33,418.12,501.1,420.24,498.98,421.63,500.47,424.39,505.03,423.32,506.2,421.31,507.69,419.5,506.31,423.32,510.03,423.01,510.45,423.01]],"area": 702.1057499999998,"iscrowd": 0,"image_id": 289343,"bbox": [473.07,395.93,38.65,28.67],"category_id": 18,"id": 1768}],

"categories": [{"supercategory": "person","id": 1,"name": "person"},{"supercategory": "vehicle","id": 2,"name": "bicycle"},{"supercategory": "vehicle","id": 3,"name": "car"},{"supercategory": "vehicle","id": 4,"name": "motorcycle"},{"supercategory": "vehicle","id": 5,"name": "airplane"},{"supercategory": "vehicle","id": 6,"name": "bus"},{"supercategory": "vehicle","id": 7,"name": "train"},{"supercategory": "vehicle","id": 8,"name": "truck"},{"supercategory": "vehicle","id": 9,"name": "boat"},{"supercategory": "outdoor","id": 10,"name": "traffic light"},{"supercategory": "outdoor","id": 11,"name": "fire hydrant"},{"supercategory": "outdoor","id": 13,"name": "stop sign"},{"supercategory": "outdoor","id": 14,"name": "parking meter"},{"supercategory": "outdoor","id": 15,"name": "bench"},{"supercategory": "animal","id": 16,"name": "bird"},{"supercategory": "animal","id": 17,"name": "cat"},{"supercategory": "animal","id": 18,"name": "dog"},{"supercategory": "animal","id": 19,"name": "horse"},{"supercategory": "animal","id": 20,"name": "sheep"},{"supercategory": "animal","id": 21,"name": "cow"},{"supercategory": "animal","id": 22,"name": "elephant"},{"supercategory": "animal","id": 23,"name": "bear"},{"supercategory": "animal","id": 24,"name": "zebra"},{"supercategory": "animal","id": 25,"name": "giraffe"},{"supercategory": "accessory","id": 27,"name": "backpack"},{"supercategory": "accessory","id": 28,"name": "umbrella"},{"supercategory": "accessory","id": 31,"name": "handbag"},{"supercategory": "accessory","id": 32,"name": "tie"},{"supercategory": "accessory","id": 33,"name": "suitcase"},{"supercategory": "sports","id": 34,"name": "frisbee"},{"supercategory": "sports","id": 35,"name": "skis"},{"supercategory": "sports","id": 36,"name": "snowboard"},{"supercategory": "sports","id": 37,"name": "sports ball"},{"supercategory": "sports","id": 38,"name": "kite"},{"supercategory": "sports","id": 39,"name": "baseball bat"},{"supercategory": "sports","id": 40,"name": "baseball glove"},{"supercategory": "sports","id": 41,"name": "skateboard"},{"supercategory": "sports","id": 42,"name": "surfboard"},{"supercategory": "sports","id": 43,"name": "tennis racket"},{"supercategory": "kitchen","id": 44,"name": "bottle"},{"supercategory": "kitchen","id": 46,"name": "wine glass"},{"supercategory": "kitchen","id": 47,"name": "cup"},{"supercategory": "kitchen","id": 48,"name": "fork"},{"supercategory": "kitchen","id": 49,"name": "knife"},{"supercategory": "kitchen","id": 50,"name": "spoon"},{"supercategory": "kitchen","id": 51,"name": "bowl"},{"supercategory": "food","id": 52,"name": "banana"},{"supercategory": "food","id": 53,"name": "apple"},{"supercategory": "food","id": 54,"name": "sandwich"},{"supercategory": "food","id": 55,"name": "orange"},{"supercategory": "food","id": 56,"name": "broccoli"},{"supercategory": "food","id": 57,"name": "carrot"},{"supercategory": "food","id": 58,"name": "hot dog"},{"supercategory": "food","id": 59,"name": "pizza"},{"supercategory": "food","id": 60,"name": "donut"},{"supercategory": "food","id": 61,"name": "cake"},{"supercategory": "furniture","id": 62,"name": "chair"},{"supercategory": "furniture","id": 63,"name": "couch"},{"supercategory": "furniture","id": 64,"name": "potted plant"},{"supercategory": "furniture","id": 65,"name": "bed"},{"supercategory": "furniture","id": 67,"name": "dining table"},{"supercategory": "furniture","id": 70,"name": "toilet"},{"supercategory": "electronic","id": 72,"name": "tv"},{"supercategory": "electronic","id": 73,"name": "laptop"},{"supercategory": "electronic","id": 74,"name": "mouse"},{"supercategory": "electronic","id": 75,"name": "remote"},{"supercategory": "electronic","id": 76,"name": "keyboard"},{"supercategory": "electronic","id": 77,"name": "cell phone"},{"supercategory": "appliance","id": 78,"name": "microwave"},{"supercategory": "appliance","id": 79,"name": "oven"},{"supercategory": "appliance","id": 80,"name": "toaster"},{"supercategory": "appliance","id": 81,"name": "sink"},{"supercategory": "appliance","id": 82,"name": "refrigerator"},{"supercategory": "indoor","id": 84,"name": "book"},{"supercategory": "indoor","id": 85,"name": "clock"},{"supercategory": "indoor","id": 86,"name": "vase"},{"supercategory": "indoor","id": 87,"name": "scissors"},{"supercategory": "indoor","id": 88,"name": "teddy bear"},{"supercategory": "indoor","id": 89,"name": "hair drier"},{"supercategory": "indoor","id": 90,"name": "toothbrush"}]}
```
其中
info:可以不关注
images：主要包含一张图片的公共信息，如宽高，图片名，图片id
> file_name:图片名称
> height：高
> width：宽
> id：图片的id。在images中是唯一的
> 
annotations：主要包含图像中每一个对象的信息，如标出的对象的边框box，标出对象的类别如人，狗，猫对应的id
> image_id:图片id对应上面images中的id，但是这个不是唯一的。因为一张图中可能会标出多个对象。
> bbox：是标注对象的边框信息[xmin,ymin,width,height]
> category_id:对象类别id，如person对应的id为1

categories：主要的对象类别的信息，如类别名称，类别id(COCO数据集有90个类别)，我们只关注id、和name就行
>id:类别id，唯一
>name:类别名称

### VOC数据集的xml格式样本
```
<?xml version='1.0' encoding='utf-8'?>
<annotation>
	<folder>JPEGImages</folder>
	<filename>PartA_00000.jpg</filename>
	<path>/home/robot11/py-faster-rcnn/data/VOCdevkit2007/VOC2007/JPEGImages/00000.jpg</path>
	<source>
		<database>Unknown</database>
	</source>
	<size>
		<width>1070</width>
		<height>594</height>
		<depth>3</depth>
	</size>
	<segmented>0</segmented>
	<object>
		<name>head</name>
		<pose>Unspecified</pose>
		<truncated>0</truncated>
		<difficult>0</difficult>
		<bndbox>
			<xmin>64</xmin>
			<ymin>222</ymin>
			<xmax>107</xmax>
			<ymax>271</ymax>
		</bndbox>
	</object>
</annotation>
```
