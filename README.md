Treehouse Android Utilities
===========================

This repository holds helpful utility files for Treehouse Android projects. Included are a couple of helper classes that can be used to work with files in Android, like detecting a shake, resizing images, and converting to byte arrays. 

Just download the files and add them to your own projects. `FileHelper.java` requires IOUtils from [Apache Commons](https://commons.apache.org/proper/commons-io/index.html), which you can include with Gradle like this:

```
dependencies {
    compile 'commons-io:commons-io:2.5'
}
```

*Alternatively, [download the required JAR here](http://commons.apache.org/proper/commons-io/download_io.cgi). Choose the latest zip file under "Binaries".
 
### FileHelper.java

- `getByteArrayFromFile(Context context, Uri uri)`: This method converts a file from a URI to a byte array. It accepts regular URIs as well as content URIs.
- `reduceImageForUpload(byte[] imageData)`: This method is used to reduce a byte array for an image file to a smaller PNG.
- `getFileName(Context context, Uri uri, String fileType)`: This method creates a file name using file type or the MIME type for both regular URIs and content URIs.

### ImageResizer.java

- `resizeImage(byte[] imageData, int targetWidth, int targetHeight)`: This resizes an image to a specified width and height.
- `resizeImageMaintainAspectRatio(byte[] imageData, int shorterSideTarget)`: This version resizes an image based on a size for the shorter side of the images (it maintains the aspect ratio).
- `getDimensions(byte[] imageData)`: This is a helper method to get the dimensions of an image.
- `calculateInSampleSize(BitmapFactory.Options options, int reqWidth, int reqHeight)`: This is a helper method to calculate the appropriate sample size to use for resizing an image.

### ShakeDetector.java

- Create a ShakeDetector object and implement the `onShake()` method from the `OnShakeListener` interface.
