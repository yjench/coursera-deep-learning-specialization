## Week 2 quiz - Detection algorithms

1. You are building a 3-class object classification and localization algorithm. The classes are: pedestrian (c=1), car (c=2), motorcycle (c=3). What would be the label for the following image? Recall y = [p_c, b_x, b_y, b_h, b_w, c_1, c_2, c_3]

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/a9MQRr0QEee3NhLzohKsog_5db51fdc3a8e995bb9fbf1addd9fa35b_Screen-Shot-2017-10-29-at-6.18.43-PM.png?expiry=1604016000000&hmac=Zmjb9hFfluNovbGeGMbLNmJ-fBYNg3dhdhs7bFasCXY)

  - [x] y = [1, 0.3, 0.7, 0.3, 0.3, 0, 1, 0]
  - [ ] y = [1, 0.7, 0.5, 0.3, 0.3, 0, 1, 0]
  - [ ] y = [1, 0.3, 0.7, 0.5, 0.5, 0, 1, 0]
  - [ ] y = [1, 0.3, 0.7, 0.5, 0.5, 1, 0, 0]
  - [ ] y = [1, 0.2, 0.4, 0.5, 0.5, 0, 1, 0]

  

2. Continuing from the previous problem, what should y be for the image below? Remember that “?” means “don’t care”, which means that the neural network loss function won’t care what the neural network gives for that component of the output. As before, y=[p_c, b_x, b_y, b_h, b_w, c_1, c_2, c_3]

  - [x] y = [0, ?, ?, ?, ?, ?, ?, ?]
  - [ ] y = [1, ?, ?, ?, ?, 0, 0, 0]
  - [ ] y = [?, ?, ?, ?, ?, ?, ?, ?]
  - [ ] y = [1, ?, ?, ?, ?, ?, ?, ?]
  - [ ] y = [0, ?, ?, ?, ?, 0, 0, 0]

  

3. You are working on a factory automation task. Your system will see a can of soft-drink coming down a conveyor belt, and you want it to take a picture and decide whether (i) there is a soft-drink can in the image, and if so (ii) its bounding box. Since the soft-drink can is round, the bounding box is always square, and the soft drink can always appears as the same size in the image. There is at most one soft drink can in each image. Here’re some typical images in your training set: What is the most appropriate set of output units for your neural network?

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/5IOuE70UEee3NhLzohKsog_e4bbe0bca31f61cc6e421dba23cc8fa7_Screen-Shot-2017-10-29-at-6.24.18-PM.png?expiry=1604016000000&hmac=SeywAqT_OY0v2FM_9hyJu9yAvVqewhVybDZ4tvLPm14)

  - [ ] Logistic unit (for classifying if there is a soft-drink can in the image)
  - [x] Logistic unit, b_x and b_y
  - [ ] Logistic unit,  b_x, b_y, b_h (since b_w = b_h)
  - [ ] Logistic unit, b_x, b_y, b_h, b_w

  

4. If you build a neural network that inputs a picture of a person’s face and outputs N landmarks on the face (assume the input image always contains exactly one face), how many output units will the network have?

  - [ ] N
  - [x] 2N
  - [ ] 3N
  - [ ] N^2

  

5. When training one of the object detection systems described in lecture, you need a training set that contains many pictures of the object(s) you wish to detect. However, bounding boxes do not need to be provided in the training set, since the algorithm can learn to detect the objects by itself.

  - [ ] True
  - [x] False

  

6. Suppose you are applying a sliding windows classifier (non-convolutional implementation). Increasing the stride would tend to increase accuracy, but decrease computational cost.

  - [ ] True
  - [x] False

  

7. In the YOLO algorithm, at training time, only one cell ---the one containing the center/midpoint of an object--- is responsible for detecting this object.

  - [x] True
  - [ ] False

  

8. What is the IoU between these two boxes? The upper-left box is 2x2, and the lower-right box is 2x3. The overlapping region is 1x1.

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/X0eDs70TEee3NhLzohKsog_cb787b3a6787db3b1aaea9a80a4eeb3f_Screen-Shot-2017-10-29-at-6.39.59-PM.png?expiry=1604016000000&hmac=NGrEItW5g2hIAoxNAz7zqWzTBN99onb64sfWKWtyohY)

  - [ ] 1/6
  - [x] 1/9
  - [ ] 1/10
  - [ ] None of the above

  

9. Suppose you run non-max suppression on the predicted boxes above. The parameters you use for non-max suppression are that boxes with probability ≤ 0.4 are discarded, and the IoU threshold for deciding if two boxes overlap is 0.5. How many boxes will remain after non-max suppression?

  ![img](https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/ZtLcab0UEee3NhLzohKsog_c80f2488a14bf72c02c10035a7dc386f_Screen-Shot-2017-10-29-at-4.23.28-PM-copy.png?expiry=1604016000000&hmac=Etcy3NMGx8z4uYbFUdqk9uPHYCDPO94vq8qqH-f9Ezc)

  - [ ] 3
  - [ ] 4
  - [x] 5
  - [ ] 6
  - [ ] 7

  

10. Suppose you are using YOLO on a 19x19 grid, on a detection problem with 20 classes, and with 5 anchor boxes. During training, for each image you will need to construct an output volume y as the target value for the neural network; this corresponds to the last layer of the neural network. (y may include some “?”, or “don’t cares”). What is the dimension of this output volume?

  - [ ]  19x19x(25x20)
  - [ ] 19x19x(5x20)
  - [ ] 19x19x(20x25)
  - [x] 19x19x(5x25)