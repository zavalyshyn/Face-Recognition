# ImageProcessing

Image Processing using OpenCV: 
- face detection&amp;recognition
- TODO: motion detection
- etc.


## Face Detection and Recognition

Done entirely with [OpenCV] (https://github.com/opencv/opencv) with additional Face module from [OpenCV-contrib] (https://github.com/opencv/opencv_contrib) repository.

I've reused some [code] (https://github.com/opencv-java) and followed the [tutorials] (http://opencv-java-tutorials.readthedocs.io/en/latest/index.html) provided by [Luigi De Russis] (https://github.com/luigidr). Other relevant sources are mentioned below.

The main problem of all the face recognition tutorials or code samples I've found is that they were all based on OpenCV version 2.4 or used external libraries like [JavaCV] (https://github.com/bytedeco/javacv). My code is based on the latest version of OpenCV 3.1.0. In this version some of the methods are different from the previous versions, for instance method MatVector is not available anymore (and most of the code samples I've found depended on it). I also didn't want to use external libraries to keep it clean and neat. 

###### Usage

Application requires a training set of images to train the face recognition. The model is trained automatically every time the application is started. If it's a first start and no training set is available comment the `trainModel();` line in init method of FXController's code. After that run the application, select the Classifier, select 'New User' checkbox, enter your name and click Submit button. Then click the Start Camera button. Application will take 50 pictures of your face and put them in the training set directory. After few seconds you may close the application, uncomment the `trainModel();` line and start the application again. The model will be re-trained and now your face should be recognized.

###### Possible issues
Face recognition is sensitive to lightning in the room so it's recommended to use the training set of images taken not from one point. For example, just by holding your laptop in your hand and turning around with it while collecting the training set gives pretty good results. 

###### Related info
- [Introduction to Java Development with OpenCV] (http://docs.opencv.org/2.4/doc/tutorials/introduction/desktop_java/java_dev_intro.html)
- [Face Recognition in Videos with OpenCV] (http://docs.opencv.org/2.4/modules/contrib/doc/facerec/tutorial/facerec_video_recognition.html)
- [JavaCV samples] (https://github.com/bytedeco/javacv/tree/master/samples)
