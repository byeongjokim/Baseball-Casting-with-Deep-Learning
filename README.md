# UnderConstruction
# Make Annotation in KBO
Classify the scene in KBO game(video), and make an annotation.

[what is kbo?](https://www.koreabaseball.com "Korea Baseball League")

## Model
### Model of Making Annotation
![Flow_chart](/PNG/flow_chart.png)

### Scene Classify
![Flow_chart](/PNG/scene_classify.png)

![Flow_chart](/PNG/field_classify.png)

## Train and Test

### Requirements
- Python3
- Tensorflow
- Opencv3

### Preparation for Training:
- Make Image Data
  ````
  python train_test.py -m --videos path/to/video path/to/another/video
  ````
  - `-m or --make` Flag, when you want to make train_data images.
  - `--videos` Videos, which you tend to train
  -	you can find images in **_data/video_name** folder

- Make Labeling

  make **video_name.csv** in **_data/video_name**. In **video_name.csv** you should write start image number, end image number, label of **_data/video_name** images.
[Scene Label](/PNG/field_classify.png)

|start | end | label|
|------|-----|------|
|0|35|10|
|36|40|3|
|41|52|1|
|...|...|...|


- Train
  ````
  python train_test.py -t --videos _data/video_name _data/video_name
  ````
  - `-t or --train` Flag, when you want to training.
  - `--videos` Videos, which you tend to train.
  
### preparation for Testing(Image):
- Test
  ````
  python train_test.py -T --image _data/image_name --threshold 0.7
  ````
  - `-T or --test` Flag, when you want to testing.
  - `--image` Image, which you tend to test.
  - `--threshold` Threshold, when you predict label.
  
### preparation for Testing(Video):
- Test
  ````
  python main.py -v path/to/video
  ````
  - `-v or --video` input video