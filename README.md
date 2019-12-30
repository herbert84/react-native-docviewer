
# react-native-docviewer


A React Native bridge module: Document Viewer for files (pdf, png, jpg, xls, doc, ppt, xlsx, docx, pptx etc.)


Changelog:

```
1.4.0
        - Android Doc Viewer Implementation 

```


## Getting started

`$ npm install react-native-docviewer --save`

### Automatic installation

`$ react-native link react-native-docviewer`


### Manual installation


#### iOS

1. In XCode, in the project navigator, right click `Libraries` ➜ `Add Files to [your project's name]`
2. Go to `node_modules` ➜ `react-native-docviewer` and add `RNReactNativeDocViewer.xcodeproj`
3. In XCode, in the project navigator, select your project. Add `libRNReactNativeDocViewer.a` to your project's `Build Phases` ➜ `Link Binary With Libraries`
4. Linked Frameworks and Libraries must have this 2 Libraries (AssetsLibrary.framework & QuickLock.framework). When not you have to add them.

5.  When you Show http Links don't forget to set APP Transport Security Settings ->
    Allow Arbitrary Loads to YES

6. Run your project (`Cmd+R`)<

#### Android

1. Open up `android/app/src/main/java/[...]/MainApplication.java`
  - Add `import com.reactlibrary.RNReactNativeDocViewerPackage;` to the imports at the top of the file
  - Add `new RNReactNativeDocViewerPackage()` to the list returned by the `getPackages()` method
2. Append the following lines to `android/settings.gradle`:
  	```
  	include ':react-native-docviewer'
  	project(':react-native-docviewer').projectDir = new File(rootProject.projectDir, 	'../node_modules/react-native-docviewer/android')
  	```
3. Insert the following lines inside the dependencies block in `android/app/build.gradle`:
  	```
      compile project(':react-native-docviewer')
  	```

## Usage
```javascript
import OpenFile from 'react-native-docviewer';

  //Handle Function Internet
  handlePress = () => {
   OpenFile.openDoc([{
     url:"http://www.snee.com/xml/xslt/sample.doc",
     fileName:"sample"
   }], (error, url) => {
      if (error) {
        console.error(error);
      } else {
        console.log(url)
      }
    })
  }
  
  //Handle Function Local File
  handlePress = () => {
    OpenFile.openDoc([{
     url:"{Path/to/the/document}",
     fileName:"sample"
   }], (error, url) => {
      if (error) {
        console.error(error);
      } else {
        console.log(url)
      }
    })
  }
  
  
   <Button
          onPress={this.handlePress.bind(this)}
          title="Press Me"
          accessibilityLabel="Open the Doc"
        />
```

  
