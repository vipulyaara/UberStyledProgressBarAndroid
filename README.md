# UberStyledProgressBarAndroid

![uber_11](https://cloud.githubusercontent.com/assets/6247940/21677083/8cbe5be4-d35e-11e6-9118-97247567f6f9.gif)


A very simple Progress bar done with the almighty <a href="https://developer.android.com/reference/android/graphics/drawable/AnimatedVectorDrawable.html">Animated Vector Drawable</a>.</br><br>

You need only three properties to make the animation work:


trimPathOffset is used to make path translate from 0 to 1</br>
trimPathStart means cut the line from start</br>
trimPathEnd means cut the line from end</br>
</br>
Practically you only need files vd_line.xml and avd_line.xml in drawables to make it work. Set avd_line as background to any view and boom! You have your progress bar. 
