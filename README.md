

# Android-Complete-VideoView Based On [MKVideoPlayer](https://github.com/khizar1556/MKVideoPlayer).
Android Adavanced Complete VideoView - library is a VideoView have Advanced  features that need to develop an video Streaming application in android studio..(Java)
<!---MK video player--->
<!---MK video player--->
<!---MK video player--->
<!---MK video player--->
# features
1. gestures for volume control
2. gestures for brightness control
3. gestures for forward or backward
4. fullscreen by manual or sensor
5. lock screen feature
6. AspectRatio feature.
<!---MK video player--->
# How to add Library into Your project
<!---MK video player--->
The easiest way to get started using MKVideoPlayer(MK video player) is to add it as a gradle
dependency. You need to make sure you have the maven { url 'https://jitpack.io' } repositories
included in the `build.gradle` file in the root of your project:
<!---MK video player--->
```gradle
allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
```
<!---MK video player---><!---MK video player--->
Next add a gradle compile dependency to the `build.gradle` file of your app
module. The following will add a dependency to the full library:
<!---MK video player--->
```gradle
dependencies {
	         compile 'com.github.khizar1556.MKVideoPlayer:mkvideoplayer:0.1.5'
	}
```
# How to use 
## case 1: only want to play a video fullscreen
just call`MKPlayerActivity.configPlayer(activity).play(url)`.
<!---MK video player--->
## case 2: Add a MKplayer in layout
### step 1: include video layout in your layout xml file
``` xml

<include
        layout="@layout/mk_player"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />


```
### step 2: How to play a Video using MKPlayer
``` java

  MKPlayer mkplayer = new MKPlayer(this);
        String url =  "Your_Video_Url";
        mkplayer.play(url);
```
# For https links Use(only MP4 support)
``` java
 
 MKPlayer mkplayer = new MKPlayer(this);
        Uri url =  Uri.parse("Your_Video_Url");
        mkplayer.play(String.valueOf(url));
```

### step 3: How to handle setPlayerCallBacks
<!---MK video player--->
``` java
 player.setPlayerCallbacks(new MKPlayer.playerCallbacks() {
            @Override
            public void onNextClick() {
            //It is the method for next song.It is called when you pressed the next icon
            //Do according to your requirement
            }
            @Override
            public void onPreviousClick() {
            //It is the method for previous song.It is called when you pressed the previous icon
            //Do according to your requirement
            }
        });
```
<!---MK video player--->

### step 4: How to Hide Status and Navigation Bar on FullScreen Landscape

<!---MK video player--->
``` java
@Override
    public void onWindowFocusChanged(boolean hasFocus) {
        super.onWindowFocusChanged(hasFocus);
        if (hasFocus) {
            hideSystemUI();
        }
    }

    private void hideSystemUI() {
        // Enables regular immersive mode.
        // For "lean back" mode, remove SYSTEM_UI_FLAG_IMMERSIVE.
        // Or for "sticky immersive," replace it with SYSTEM_UI_FLAG_IMMERSIVE_STICKY
        View decorView = getWindow().getDecorView();
        decorView.setSystemUiVisibility(
                View.SYSTEM_UI_FLAG_IMMERSIVE_STICKY
                        // Set the content to appear under the system bars so that the
                        // content doesn't resize when the system bars hide and show.
                        | View.SYSTEM_UI_FLAG_LAYOUT_STABLE
                        | View.SYSTEM_UI_FLAG_LAYOUT_HIDE_NAVIGATION
                        | View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN
                        // Hide the nav bar and status bar
                        | View.SYSTEM_UI_FLAG_HIDE_NAVIGATION
                        | View.SYSTEM_UI_FLAG_FULLSCREEN);
    }

```
<!---MK video player--->

### step 5: How to Add Internet Permission and Config Screen Rotation
<!---MK video player--->
``` java
 <activity
        android:name=".Your_Activity_Name"
        android:configChanges="keyboardHidden|orientation|screenSize"
        android:screenOrientation="sensor" >
	</activity>
```
<!---MK video player--->

---------


# API:
* `play(url)` //play video
* `stop()`//stop video
* `pause()`//pause video
* `start()` //start  video
* `forward()` // forward or back video,example: forward(0.1f) forward(-0.1f)
* `getCurrentPosition()` 
* `setScaleType(MKPlayer.SCALETYPE_FITPARENT)` //set video scale type
* `toggleAspectRatio()` // toggle video scale type
* `seekTo(...)` //seek to specify position
* `getDuration()` //get video duration
* `onInfo(...)` //callback when have some information
* `onError(...)`  //callback when an error occurred
* `onComplete(...)` //callback when the play is over
* `onControlPanelVisibilityChange(...)` //callback when control panel visibility change
* `setPlayerCallbacks()` //Callback to control next and previous methods
<!---MK video player--->
# Screenshots:
<!---MK video player--->
![](https://raw.githubusercontent.com/khizar1556/MKVideoPlayer/master/screenshots/Screenshot_2017-10-06-18-27-04.png)
![](https://github.com/khizar1556/MKVideoPlayer/blob/master/screenshots/Screenshot_2017-10-06-18-28-12.png)
![](https://github.com/khizar1556/MKVideoPlayer/blob/master/screenshots/Screenshot_2017-10-06-18-32-34.png) 
<!---MK video player--->
