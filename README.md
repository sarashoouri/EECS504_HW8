# EECS504_HW8
Representation Learning
We’ll start by implementing a simple self-supervised learning method: an autoencoder. The
autoencoder is composed of an encoder and a decoder. The encoder often compresses the
original data with a funnel-like architecture, i.e., it throws away redundant information by
reducing the layer sizes gradually. The final output size of the encoder is a bottleneck that is
much smaller than the size of the original data. The decoder will use this limited amount of
information to reconstruct the original data. If the reconstruction is successful, the encoder
has arguably captured a useful, concise representation of the original data.
Such representations could help with downstream tasks such as object recognition, semantic
segmentation, etc. Here, to test the usefulness of the representation, we’ll train the encoders
on the STL-10 dataset, which is designed to evaluate unsupervised learning algorithms. This
dataset contains 100,000 unlabeled images, 5,000 labeled training images, and 8,000 labeled test
images. To keep training time short, we’ll use 10,000 unlabeled images to learn representations.
Then, given this learned representations, we’ll train a linear classifier on the 5,000 training
images. The accuracy is then measured on the test set. If the learned representations are
useful, we should obtain a performance improvement over only using the small, labeled training
set.
