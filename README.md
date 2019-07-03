![GradCam Viz](./cam_viz.gif)

# Intro
Recently Google AI Research published a paper titled “EfficientNet: Rethinking Model Scaling for Convolutional Neural Networks”. In this paper the authors propose a new architecture which achieves state of the art classification accuracy on ImageNet while being 8.4x smaller and 6.1x faster on inference than the best existing CNN.
It achieves high level of acacuracy on many other datasets like CIFAR-100, Flowers and Cars. Good results on multiple dataset shows that the architecture can be used for transfer learning. 

In this notebook, I try to compare the proposed efficient models with other popular architectures like densenet and resnet. I use  [GradCam](https://arxiv.org/abs/1610.02391) to highlight what different models are looking at.

You can find a very nice implementation of GradCam [here](https://github.com/FrancescoSaverioZuppichini/A-journey-into-Convolutional-Neural-Network-visualization-). I use the pretrained model weights provided [here](https://github.com/lukemelas/EfficientNet-PyTorch#loading-pretrained-models) for visualization.

# About EfficientNet


A naive way to increase the performance of neural networks is to increase make CNN deeper. A great example, would be resnet which has several variations ranging from 18 to 202. Making the CNN deeper or wider may increase the performance but it comes at great computational cost. So we need some way to balance our ever increasing quest for performance with compuatational cost. In the paper, the authors propose a new model scaling method that uses a simple compound coefficient to scale up CNNs in a more structured manner. This method helps them to decide when to increase the depth or width of the network.

The authors wanted to optimize for accuracy and efficieny. So, they performed a neural architecture search. This search yielded th Efficient-B0 archictecture which looks pretty simple and straightforward to implement.

![EfficientNet-B0 Architecture](https://1.bp.blogspot.com/-DjZT_TLYZok/XO3BYqpxCJI/AAAAAAAAEKM/BvV53klXaTUuQHCkOXZZGywRMdU9v9T_wCLcBGAs/s640/image2.png)

As you can see from the performance graph, EfficientNet uses fewer parameters and achieves very high accuracy. For more details please [refer](https://arxiv.org/abs/1905.11946)

![Efficient Performance](https://1.bp.blogspot.com/-oNSfIOzO8ko/XO3BtHnUx0I/AAAAAAAAEKk/rJ2tHovGkzsyZnCbwVad-Q3ZBnwQmCFsgCEwYBhgL/s640/image3.png)