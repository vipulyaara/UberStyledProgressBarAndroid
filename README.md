# UberStyledProgressBarAndroid

![uber_11](https://cloud.githubusercontent.com/assets/6247940/21677083/8cbe5be4-d35e-11e6-9118-97247567f6f9.gif)


A very simple Progress bar done with the almighty <a href="https://developer.android.com/reference/android/graphics/drawable/AnimatedVectorDrawable.html">Animated Vector Drawable</a>.</br><br>

You need only three properties to make the animation work:


trimPathOffset is used to make path translate from 0 to 1</br>
trimPathStart means cut the line from start</br>
trimPathEnd means cut the line from end</br>
</br>
Practically you only need files vd_line.xml and avd_line.xml in drawables to make it work. Set avd_line as background to any view and boom! You have your progress bar. 


</br>
</br>
**Repeating the animation infinitely**
</br>
To repeat the animation infinitely after Lollipop (v21)

```
        final AnimatedVectorDrawable avd = (AnimatedVectorDrawable) ivNoTrip.getDrawable();
        avd.registerAnimationCallback(new Animatable2.AnimationCallback() {
            @Override
            public void onAnimationEnd(Drawable drawable) {
                avd.start();
            }
        });
```


But this approach does not work with AnimatedVectorDrawableCompat. So for backward compatibility, use this workaround

```
Runnable action = new Runnable() {
        @Override
        public void run() {
            repeatAnimation();
        }
    };

    private void initializeAvd() {
        avdProgress = AnimatedVectorDrawableCompat.create(context, R.drawable.avd_line);
        repeatAnimation();
    }

    private void repeatAnimation() {
        avdProgress.start();
        ivProgress.postDelayed(action, 1000); // Will repeat animation in every 1 second
    }
```

</br>
</br>
</br>

# **License**
```
Copyright 2017 Vipul Kumar

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





