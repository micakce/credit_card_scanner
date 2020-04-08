## Credit Card Scanner

The goal of this project is to build an app that can detect a credict card either
from a picture or camera feed, crop it, and detect relevant info as it is card number,
card holder name and expire date.


### First approach:

- Credit Card Recognition: It is done through image segmentation, training a model
to gives us a mask and crop the image based on the obtained mask. The model used
is the `efficientnetb3`

- Text detection: It is done through the OpenCV's EAST text detector deep learning
model.

- Text recognition: We use Opencv+Tesseract, also a deep learning model.

### Requirements:

- Tensorflow 2.2.0-rc2
- Keras 2.3.0-tf
- OpenCV 4.1.2
- Tesseract 4
- Numpy 1.18
- Matplotlib 3.2.1


This is by no means a finished product, it is the first attemp of building a
credit card scanner and sets a baseline for the work that needs to done in order
to get a production ready app.

All the neccesary resources and step by step are included in the [Colab](https://colab.research.google.com/drive/1xZS6Tl0XaWLk4_f_PCc7PAsummjUZ0c8)
implementation. Have fun!


## Conclusions

Given the little data there is to train, the model did a good job predicting
the masks, it shouldn't be hard to train it further on more data and get much
better results. On the other hand, even though a natural scenes text detection
approch was used, the results weren't any good, that is given the complexity
of text we can find in real life objects, and it makes sense credict cards are
not taken that much into account when building this kind of models. A lot of work
to do on the text detection and recognition part.

## References

- Segmentation: Is based on the CamVid example in the respository
[qubvel/segmentation_models](https://github.com/qubvel/segmentation_models)
- OCR: Is a Colab adaptation from Adrian Rosebrock implementations, more on
these two posts: [opencv-text-detection-east-text-detector](https://www.pyimagesearch.com/2018/08/20/opencv-text-detection-east-text-detector/) and [opencv-ocr-and-text-recognition-with-tesseract](https://www.pyimagesearch.com/2018/09/17/opencv-ocr-and-text-recognition-with-tesseract/).
