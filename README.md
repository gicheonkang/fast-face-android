# Fast Face for Android !

Fast Face is an android application which detects facial landmark . <br />
It detects 68 landmarks of human face, chin to eyebrow in real-time. <br />

It is an upgraded version of [dlib-android](https://github.com/tzutalin/dlib-android), Not only revising the code but additional task for optimizing dlib library was needed. <br />
As a result, Fast Face speeds up 2x or more from the original. Higher resoluton, Higher speed.<br />

I think it is not the best one, there are some issues that can be more speedy one. <br />
So, if you guys already improved or want to improve this code, feel free to contact me. Test and Enjoy it :) <br />
<br />

### Environments
* DEVICE : SAMSUNG-A8 2015
* API    : 25 (Android 7.1)
* TIME   : 60ms ~ 70ms
<br />

### Demo
![](demo/demo.png)

### Features

* Support HOG detector
* HOG Face detection
* Facial Landmark/Expression
<br />

### Sample code

Facial landmark detection
```java
FaceDet faceDet = new FaceDet(Constants.getFaceShapeModelPath());
Bitmap bitmap = BitmapFactory.decodeFile("Image Path");
List<VisionDetRet> results = faceDet.detect(bitmap);
for (final VisionDetRet ret : results) {
    String label = ret.getLabel();
    int rectLeft = ret.getLeft();
    int rectTop = ret.getTop();
    int rectRight = ret.getRight();
    int rectBottom = ret.getBottom();
    // Get 68 landmark points
    ArrayList<Point> landmarks = ret.getFaceLandmarks();
    for (Point point : landmarks) {
        int pointX = point.x;
        int pointY = point.y;
    }
}
```

### License
[License](LICENSE.md)
