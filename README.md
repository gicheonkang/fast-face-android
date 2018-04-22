# Android App for Real-time Face Landmark Detection

Fast Face is an android application which detects facial landmark . It detects 68 landmarks of human face <br />
chin to eyebrow in real-time. Also, it can detect people up to 3 if you guys show your frontal faces. <br /> 

It is an upgraded version of [dlib-android](https://github.com/tzutalin/dlib-android), Not only revising the code but additional task for optimizing dlib library was needed. 
As a result, Fast Face speeds up 2x or more from the original. Higher resoluton, Higher speed.<br />

I think it is not the best one, there are some issues that can be more speedy one. <br />
So, if you guys already improved or want to improve this code, feel free to contact me. Test and Enjoy it :) <br />
<br />

## Screenshot
<img src="demo/demo.png" width="300">
<br />

## Environments
* DEVICE : SAMSUNG-A8 2015(@cortex-a53 core)
* API    : 23 (Android 6.0.1)
* TIME   : 50ms ~ 70ms
<br />

## Features

* Support HOG detector
* HOG Face detection
* Facial Landmark/Expression
<br />

## Sample code

Facial landmark detection
```java

// detecs every 3 frames
if(mframeNum % 3 == 0){
    synchronized (OnGetImageListener.this) {
        results = mFaceDet.detect(mResizedBitmap);
    }
}

// Draw on bitmap
if (results.size() != 0) {
    for (final VisionDetRet ret : results) {
        float resizeRatio = 4.5f;
        Canvas canvas = new Canvas(mInversedBipmap);

        // Draw landmark
        ArrayList<Point> landmarks = ret.getFaceLandmarks();
        for (Point point : landmarks) {
            int pointX = (int) (point.x * resizeRatio);
            int pointY = (int) (point.y * resizeRatio);
            canvas.drawCircle(pointX, pointY, 4, mFaceLandmardkPaint);
        }
     }
}
```
<br />

## License
[License](LICENSE.md)
