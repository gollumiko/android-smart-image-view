Smart Image View for Android
==============================

SmartImageView is a drop-in replacement for Android’s standard ImageView which additionally allows images to be loaded from URLs or the user’s contact address book. Images are cached to memory and to disk for super fast loading.

TouchSmartImageView adds the ability to drag and zoom the SmartImageView.

Features
--------
- Drop-in replacement for ImageView
- Load images from a URL
- Load images from the phone’s contact address book
- Asynchronous loading of images, loading happens outside the UI thread
- Images are cached to memory and to disk for super fast loading
- SmartImage class is easily extendable to load from other sources
- TouchSmartImageView class is the result of merging TouchImageView of Mike Ortiz (<https://github.com/MikeOrtiz/TouchImageView>) and SmartImageView of loopj (<http://loopj.com/android-smart-image-view/>)

Usage of TouchSmartImageView
------------------------------
In the layout XML (the scaleType must be **matrix**): 
```
<com.loopj.android.image.TouchSmartImageView
	android:id="@+id/imageView1"
	android:layout_width="fill_parent"
	android:layout_height="wrap_content"
	android:scaleType="matrix" /> 
```
In the code
```
TouchSmartImageView imageView = (TouchSmartImageView) findViewById(R.id.imageView1);

// Load an image into the view from a URL 
imageView.setImageUrl("http://www.awesomeimages.com/myawesomeimage.jpg");
```

TouchImage API:
```
// Get the current zoom. This is the zoom relative to the initial
// scale, not the original resource.
float getCurrentZoom();

// For a given point on the view (ie, a touch event), returns the
// point relative to the original drawable's coordinate system.
PointF getDrawablePointFromTouchPoint(float x, float y);

// For a given point on the view (ie, a touch event), returns the
// point relative to the original drawable's coordinate system.
PointF getDrawablePointFromTouchPoint(PointF p);

// Get the max zoom multiplier.
float getMaxZoom();

// Get the min zoom multiplier.
float getMinZoom();

// After setting image, a value of true means the new image should maintain
// the zoom of the previous image. False means the image should be resized 
// within the view. Default value is true.
void maintainZoomAfterSetImage(boolean maintainZoom); 

// Set the max zoom multiplier. Default value: 3.
void setMaxZoom(float max);

// Set the min zoom multiplier. Default value: 1.
void setMinZoom(float min);
```


Documentation, Features and Examples
------------------------------------
Full details and documentation about Smart Image View can be found on the project page here:

<http://loopj.com/android-smart-image-view/>