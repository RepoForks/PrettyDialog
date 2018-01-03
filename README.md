[ProjectGithubUrl]:     https://github.com/mjn1369/prettydialog
[PlatformBadge]:  https://img.shields.io/badge/Platform-Android-blue.svg
[ApiBadge]:       https://img.shields.io/badge/API-10%2B-blue.svg
[ProjectLicenceUrl]:    http://www.apache.org/licenses/LICENSE-2.0
[LicenseBadge]:   https://img.shields.io/badge/License-Apache_v2.0-blue.svg
# PrettyDialog
[![Platform][PlatformBadge]][ProjectGithubUrl]
[![Api][ApiBadge]][ProjectGithubUrl]
[![License][LicenseBadge]][ProjectLicenceUrl]
[![](https://jitpack.io/v/rey5137/material.svg)](https://jitpack.io/#rey5137/material) [![Download](https://api.bintray.com/packages/rey5137/maven/material/images/download.svg)]

PrettyDialog is an Android Dialog library which is the customizable equivalent of SCLAlertView in iOS.

Example is available in app module.
## Download
### Gradle:
Add the following to your project level build.gradle:

```
allprojects {
 repositories {
  ...
  maven { url "https://jitpack.io" }
 }
}
```
Add this to your app build.gradle:

```
dependencies {
 compile 'com.github.mjn1369:prettydialog:1.0.0'
}
```
## Usage
PrettyDialog extends Dialog class, so feel free to use its inherited functions.

**Note:** Default dialog has no title, message or any buttons. Just a close icon on top which you can dismiss the dialog by clicking on it.
### Simple Dialog, No Customization:
```
new PrettyDialog(this)
	.setTitle("PrettyDialog Title")
	.setMessage("PrettyDialog Message")
	.show();
```
##### Output:
![alt text](https://github.com/mjn1369/PrettyDialog/blob/master/Screenshots/1.png "Simple Dialog, No Customization")
### Change Icon:
- You can set the dialog icon resource:
```
...
.setIcon(R.drawable.pdlg_icon_info)
...
```
- And set a color tint for it:
```
...
.setIconTint(R.color.pdlg_color_green)
...
```
- Ultimately, define an OnClick callback:
```
...
.setIconCallback(new PrettyDialogCallback() {
	    @Override
	    public void onClick() {
		// Do what you gotta do
	    }
	})
...
```
- Put them all together:
```
...
.setIcon(
	R.drawable.pdlg_icon_info,     // icon resource
	R.color.pdlg_color_green,      // icon tint
	new PrettyDialogCallback() {   // icon OnClick listener
	    @Override
	    public void onClick() {
		// Do what you gotta do
	    }
	})
...
```
##### Output:
![alt text](https://github.com/mjn1369/PrettyDialog/blob/master/Screenshots/2.png "Customize icon")

### Add Buttons:
- You can add unlimited customized buttons to dialog: 
```
...
// OK button
.addButton(
		"OK",					// button text
		R.color.pdlg_color_white,		// button text color
		R.color.pdlg_color_green,		// button background color
		new PrettyDialogCallback() {		// button OnClick listener
		    @Override
		    public void onClick() {
			// Do what you gotta do
		    }
		}
	)
	
// Cancel button
.addButton(
		"Cancel",
		R.color.pdlg_color_white,
		R.color.pdlg_color_red,
		new PrettyDialogCallback() {
		    @Override
		    public void onClick() {
			// Dismiss
		    }
		}
	)
	
// 3rd button
.addButton(
		"Option 3",
		R.color.pdlg_color_black,
		R.color.pdlg_color_gray,
		null
	);
...
```
##### Output:
![alt text](https://github.com/mjn1369/PrettyDialog/blob/master/Screenshots/3.png "Added custom buttons")
### Custom Title, Message and Typeface:

**Note:** Typeface applies to all texts inside the dialog.
```
...
.setTitle("Do you agree?")
.setTitleColor(R.color.pdlg_color_blue)
.setMessage("By agreeing to our terms and conditions, you agree to our terms and conditions.")
.setMessageColor(R.color.pdlg_color_gray)
.setTypeface(Typeface.createFromAsset(getResources().getAssets(),"myfont.otf"))
...
```
##### Output:
![alt text](https://github.com/mjn1369/PrettyDialog/blob/master/Screenshots/4.png "Custom Title, Message and Typeface")
- Enable/Disable dialog animation:
```
...
.setAnimationEnabled(true)
...

```

## Functions

 |            Functions            |            Description            |            Default            |
 | ------------------------------- | -------------------------------   | --------------------------    |
 | setTitle                      | sets a title for dialog           |  ""                           |
 | setTitleColor                | sets title's color                |  #212121 (kinda black)        |
 | setMessage               | sets a message for dialog         |  ""                           |
 | setMessageColor               | sets message's color              |  #212121 (kinda black)        |
 | setIcon                      | sets the dialog's icon            |  "close (X)" icon             |
 | setIconTint                 | sets tint for dialog's icon       |  #1976D2 (kinda blue)         |
 | setIconCallback              | sets dialog's icon callback       |  dismiss dialog               |
 | setIcon                 | sets icon,icon tint,icon callback |                               |
 | addButton                   | adds button with text,text color,background color and callback|   |
 | setTypeface                  | sets typeface for all texts       |                               |
 | setAnimationEnabled       | enables or disables dialog animation| Enabled                     |

cheers :beers:

## License
 
 ```
Copyright 2017 mjn1369

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
 
```  
