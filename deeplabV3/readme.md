 DeepLabV3 is a semantic segmentation model that effectively identifies object regions
 within an image. However, it lacks the capability for instance segmentation, making it
 less ideal for distinguishing individual objects within the bin.
 The DeepLabV3 model used in this evaluation is based on a ResNet-50 backbone. It
 is specifically designed for semantic segmentation, where each pixel is classified into a
 category. This approach is useful for identifying regions of objects but does not allow for
 the separation of individual instances of the same object type.

![image](https://github.com/user-attachments/assets/0d0ea21f-1fad-4ab0-a34c-3f43238bc53f)

 #### Performance
 DeepLabv3 did not perform well in our case, as it generally requires training on thousands
 of labeled bin-picking scenes to achieve good results. The model uses a deep backbone
 (such as ResNet-101) and a complex architecture with millions of parameters, making
 it prone to overfitting when trained on small datasets. Without enough diverse training images—varying in object types, lighting, and bin configurations—it tends to memorize
 the training data rather than generalize. As a result, its real-world performance suffers
 unless it’s pretrained on large datasets and fine-tuned with effective data augmentation
 or synthetic data

 ![output](https://github.com/user-attachments/assets/4e9c60ff-c01a-43f9-b68f-1bde70efd8ed)
