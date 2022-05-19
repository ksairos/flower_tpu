# First computer vision project using Kaggle and TPUs

## Some personal notes regarding the project

- Make sure to create different TFRecord formats for training (labeled) and test (unlabeled) datasets.

- When loading dataset better make test data ordered (idk why but otherwise I had random shuffled results). Making training set "ignore_order.experimental_deterministic = False" can increase computations.

- When creating data pipelines we are using two separate functions to work with the training dataset: the first one is used it the training itself, and the second one is used in the evaulation and visualization. The main difference -> the second one doesn't use repeat() not to make the dataset infinite and doesn't use augmentation.

- Check class distribution (may use visuals)

- [Transfer Learning using Keras](https://keras.io/guides/transfer_learning/#the-typical-transferlearning-workflow) using Functional API

- Use warm-up training with few (3) epochs with pre-trained model frozen and decrease the learning rate for the actual learning.

- Set STEPS_PER_EPOCH = NUM_TRAINING_EXAMPLES // BATCH_SIZE

- sklearn.metrics.classification_report for f1, presicion and recall
