

|논문명 | DeepPano: Deep Panoramic Representation for 3-D Shape Recognition |
| --- | --- |
| 저자\(소속\) | Baoguang Shi \(\) |
| 학회/년도 | 2015, [논문](http://ieeexplore.ieee.org/document/7273863/) |
| 키워드 |  |
| 데이터셋/모델 | ModelNet-10, ModelNet-40 |
| 참고 |  |
| 코드 |[Matlab](https://github.com/bgshih/deeppano) |

# DeepPano

제안 : A robust representation of 3-D shapes learned with deep CNN

절차 
1. 파노라마뷰로 변경 `Firstly, each 3-D shape is converted into a panoramic view`
2. 제안된 CNN을 통해 학습 `Then, a variant of CNN is specifically designed for learning the deep representations directly from such views. `

기존 CNN과 다른점은 **row-wise맥스 풀링층**을 추가 하여 invariant에 대처 하도록 함 `Different from typical CNN, a row-wise max-pooling layer is inserted between the convolution and fully-connected layers, making the learned representations invariant to the rotation around a principle axis`

## 1. INTRODUCTION

- Representation에 위해서 성능이 좌우됨 `The performance of many tasks, including shape classification and shape retrieval, heavily depend on the quality of the representation`

본 논문은 DeepPano을 제안, 
- Directly learned from the panoramic views of 3-D models
- The panoramic view is a **cylinder projection** of a 3-D model around its principle axis.
- Therefore, the panoramic views are in the **form of 2-D images**,

Row-Wise Max-Pooling (RWMP) layer  제안
- To make the learned deep features invariant to the rotation around the principle axis
- between the convolution layers and the fully-connected layers. 
- This layer takes the maximum value of each row in the convolutional feature maps. 
- Consequently, the output feature vector is not affected by the shift of the panoramic view, caused by the rotation of 3-D shape.

### 1.1 관련 연구 

기존 연구 동향 분류 : The previous methods on 3-D shape analysis can be coarsely categorized into **model-based** and **view-based** methods. 

#### A. Model based methods 
- Model based methods calculate a set of features directly from the 3-D shape **mesh** or its rendered **voxels**. 

- 예 : Such methods include the Shape Histogram descriptor [2] and the Spin Images [3]. 

#### B. View based methods 
- View based methods represent 3-D shapes by a set of views [4]–[10].

- The views can be 2-D projections of the shape or the panoramic view. 


- 위 방법과 제안의 차이는 **hand-crafted**가 아니라 **CNN**을 이용한다. `However, different from most of the methods mentioned above that use hand-crafted features, we learn the representation from data with a variant of CNN. `


- 비슷한 기존 연구로 **3-D ShapeNets**가 있다. 이와 다른

Different from [14] which performs 3-D convolutionson the voxels, we extract the representation of a 3-D shapefrom 2-D images. 

Compared with [14], our method achievesbetter performances on both classification and retrieval tasks(refer to Section III), and is simpler to implement using any opensource framework.


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI0ODg5MzM2XX0=
-->