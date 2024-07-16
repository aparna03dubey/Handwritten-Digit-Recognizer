# Python-Custom-Digit-Recognition

I created this Python script to apply simple OCR on my handwritten digits. Using OpenCV, I pre-process the image and extract the digits. I trained the model with my own handwritten dataset and included the freely [available](http://yann.lecun.com/exdb/mnist/) MNIST dataset for experimentation.

## Analysis  
After researching feature extraction methods for OCR, I discovered [HOG](https://en.wikipedia.org/wiki/Histogram_of_oriented_gradients) (Histogram of Oriented Gradients), which captures shape information by analyzing intensity changes across pixels.

![pic-explain](https://gilscvblog.files.wordpress.com/2013/08/figure5.jpg "pic")

HOG works by dividing the image into small cells (usually 8x8 pixels) and blocks of 4x4 cells. Each cell has gradient orientation bins, where each pixel votes for a gradient orientation bin based on the gradient magnitude. This method drastically improved the prediction accuracy. Currently, I use KNN from OpenCV as my model. I also tried SVM, but KNN provided better accuracy. The best accuracy I achieved on a sample image of about 100 digits is 80%. In the future, I might add more features, possibly exploring SIFT, SURF, or improving accuracy with pixel data alone.

