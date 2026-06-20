# Project Motivation 

This project aims to explore deep learning techniques for fine-grained image classification using a 100-class butterfly and moth dataset. Discrete nuances between species present a unique challenge suited for machine learning methods to address. The focus was to evaluate a transformer-based model against established convolutional neural networks to assess their effectiveness in handling complex, real-world variability that challenges model generalisation.

A ViT was employed in this investigation for its ability to capture long-range dependencies by representing each instance as a sequence of patches, processed through a transformer architecture that excels at handling sequential data. While several experimental approaches explored custom ViT architectures, the final model leveraged transfer learning using the vit-b16-fe model from TensorFlow Hub, selected for its proven state-of-the-art performance in classification tasks and its ability to outperform traditional CNNs when trained on large datasets.

The architecture consists of an input layer defined to accept images of 224x224x3. The backbone consists of a vision transformer feature extractor. This allows the model to exploit the pre-trained weights obtained from training the **vit-b16-fe** model on the ImageNet-1k dataset and reduce computational requirements during training. The model's core is followed by a dropout layer with a dropout rate of 0.2, attempting to prevent excessive overfitting by setting various input units to zero during training. The output layer is a fully connected dense layer of 100 units with a softmax activation function corresponding to the number of classes present in the dataset. This approach provides a solid foundation to apply transfer learning to classify butterfly and moth species and investigates increasingly progressive and state-of-the-art vision transformer image classification techniques that have not been explored on the **Butterfly & Moths Image Classification 100 species** dataset.

## Key Results

- **ViT Accuracy:** 96.6%
- **ViT F1 Score:** 96.5%  
- **Accuracy Improvement:** +12.8% through manual correction of mislabeled images. This process directly improved model performance and highlighted how **data quality intervention** can impact model accuracy.

Evaluation on the test set demonstrated that the Vision Transformer outperformed several established convolutional neural network (CNN) architectures trained on the same dataset, achieving a classification accuracy of 96.6%, 1% higher than models such as the Squeeze-and-Excitation + Spatial Attention + Dilated Residual Network model outlined in Xin, Chen and Li's 2020 paper **[here.](https://www.mdpi.com/2076-3417/10/5/1681)**

By effectively implementing the model, I aim demonstrate the ability to apply deep learning techniques to challenging, high-variance problems, showcasing a strong foundation in adapting advanced architectures to diverse tasks.
