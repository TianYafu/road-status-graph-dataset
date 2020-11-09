# Road-Scene-Graph-dataset

Road Scene Graph Dataset is an intelligent-vehicle-oriented scene graph dataset. This dataset was built for detecting the "relationship" between objects in driving scenes. For example: a vehicle is "waiting for" a walker.

Also, we hope these data could benefit other tasks like risk detection, scene capting and model interpretability.

This dataset is based on the [Nuscenes dataset](https://www.nuscenes.org/) and [CARLA](https://carla.org/)

----------------

## Overview

- What is Road Scene Graph
- When will this dataset become available?
- Overview of Road Scene Graph Dataset
    - Dataset
    - Annotator
    - Toolkits
- Basic Evaluation of Road Scene Graph
- Roadmap

----------------

## What is Road Scene Graph

Road scene graph is a special scene-graph for intelligent vehicles. Different to classical data representation, this graph provided not only object proposals but also their pair-wise relationships. As subFigure A illustrates, in scene graph objects are encoded as nodes; their relationships, such as "following" and "waiting", represented as edges. 
 
By organizing them in a topological graph, these data are user-friendly, explainable, and could be easily processed by GCNs (Graph convolutional network). Here we initially apply scene graph on roads, brought out Road Scene Graph dataset

![intro.png](/imgs/intro.png)

And subfigure B shows the relationship between road scene graph and other environment recognition methods. Road scene graph combines bounding box regression and behavior/relationship prediction, so it also benefits from the rapid development of object detection methods and behavior prediction models. 


![sample.png](/imgs/sample.png)




## When will this dataset become available?

Coming soon, maybe after the review process of ICRA21.

----------------

## Overview of Road Scene Graph Dataset

Here we list some of our contribution:

### Dataset:

Currently (Road scene graph V1), this dataset includes the following objects and relationships:

![sample.png](/imgs/data_types.png)


### Annotator:

And here are a screen capture of our GUI data annotator. This annotator will also be published, along with the dataset itself.


![DataAnnotatorImage.jpg](/imgs/DataAnnotatorImage.jpg)

Camera images (front, back) and 6D bounding box are on the left, and on the middle there are top-down view of the corresponding scene. By clicking the highlight object on this panel, user can easily create scene graph within a minute. And when it moves to the next frame, this program will predict which relationship could be ”broadcasted” into this frame. So user doesn’t need to label this frame from a blank panel.

### Toolkits

Our dataset was set up based on Nuscenes and CARLA. For both datasets, we provide a similar data interface. Were we use geometry information from Nuscenes, and using instance token to maintain object consistency.

![data_structure.png](/imgs/data_structure.png)

-----------------



## Roadmap

![roadmap.png](/imgs/roadmap.png)


Tasklist:

- [x] Data annotator
- [x] Basic dataset construction
- [x] Basic development kit
- [x] Graph refinement model
- [x] Simple graph prediction model.
- [ ] [2021] Graph prediction from object proposal
- [ ] [2021] Scene captioning model
- [ ] [2022] Real-time scene graph construction

## Reference

We would be very happy if this dataset could benefit your research. And it would be nice to cite my paper:

    TODO: need endorced by supervisor

Also, as our dataset was based on nuScenes dataset and CARLA, please also reference their papers:

nuScenes:
```
@inproceedings{caesar2020nuscenes,
  title={nuscenes: A multimodal dataset for autonomous driving},
  author={Caesar, Holger and Bankiti, Varun and Lang, Alex H and Vora, Sourabh and Liong, Venice Erin and Xu, Qiang and Krishnan, Anush and Pan, Yu and Baldan, Giancarlo and Beijbom, Oscar},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={11621--11631},
  year={2020}
}

```

CARLA: 

```
@inproceedings{Dosovitskiy17,
  title = { {CARLA}: {An} Open Urban Driving Simulator},
  author = {Alexey Dosovitskiy and German Ros and Felipe Codevilla and Antonio Lopez and Vladlen Koltun},
  booktitle = {Proceedings of the 1st Annual Conference on Robot Learning},
  pages = {1--16},
  year = {2017}
}
```

And these are some scene-graph related paper which could be interesting:

- Scene graph generation by iterative message passing
- Visual genome: Connecting language and vision using crowdsourced dense image annotations
- Visual Semantic Navigation using Scene Priors
- Neural motifs: Scene graph parsing with global context
- Scene graph generation from objects, phrases and region captions
- Graphvae: Towards generation of small graphs using variational autoencoders