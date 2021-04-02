# QR-Scanner-App[JAVA]
It will generate QR code for given data .Scanning QR code and generate data . 
***
![Click here](https://github.com/KishorKokate/QR-Scanner-App/blob/master/app/src/main/res/drawable-v24/QRApp.jpeg?raw=true)

### Gradle:
```xml
implementation 'com.karumi:dexter:6.2.2'
implementation 'com.budiyev.android:code-scanner:2.1.0'
implementation 'androidmads.library.qrgenearator:QRGenearator:1.0.4'
   ```
### Permission:
Add This Permission for saving your generated code
```xml
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
```
### How to use this Library:
After importing this library, use the following lines to use this library.
The following lines are used to generated the QR Code
```java
// Initializing the QR Encoder with your value to be encoded, type you required and Dimension
QRGEncoder qrgEncoder = new QRGEncoder(inputValue, null, QRGContents.Type.TEXT, smallerDimension);
qrgEncoder.setColorBlack(Color.RED);
qrgEncoder.setColorWhite(Color.BLUE);
try {
  // Getting QR-Code as Bitmap
  bitmap = qrgEncoder.getBitmap();
  // Setting Bitmap to ImageView
  qrImage.setImageBitmap(bitmap);
} catch (WriterException e) {
  Log.v(TAG, e.toString());
}
```
Save QR Code as Image 
```java
// Save with location, value, bitmap returned and type of Image(JPG/PNG).
QRGSaver qrgSaver = new QRGSaver();
qrgSaver.save(savePath, edtValue.getText().toString().trim(), bitmap, QRGContents.ImageType.IMAGE_JPEG);
```
For more Details [Click Here](https://github.com/KishorKokate/QR-Scanner-App/blob/master/app/src/main/java/com/example/qrscanner/QRGenerator.java)
