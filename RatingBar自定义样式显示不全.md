#RatingBar 自定义样式显示不全
解决方法：
```
<item name="android:minHeight">15dp</item>
<item name="android:maxHeight">15dp</item>
```

定义根据图片自定一个RatingBar的背景条，和图片放到同一个目录下面     
five_rating_bar.xml
```
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">
    <item  android:id="@android:id/background"
               android:drawable="@drawable/star_border_hide"/>
    <item  android:id="@android:id/secondaryProgress"
                android:drawable="@drawable/star_border_hide"/>
     <item android:id="@android:id/progress"
                android:drawable="@drawable/star_border_show"/>
</layer-list>
```
```
backgroud：是用来填充背景图片的，和进度条非常类似，当我们设置最高评分时（android:numStars），
系统就会根据我们的设置，来画出以星星为单位的背景（假如android:numStars="5"，就会画出5颗灰色的星星）
progress：是用来在背景图片基础上进行填充的指示属性（和进度条类似，第一进度位置）
secondaryProgress：同progress一样属于第二进度位置（如果不定义这个，进度条拖动，每次就画出一整颗星星（亮），
第二进度（暗）没有覆盖掉第一进度之后的位置，从左往右是拖不出来N.5颗星星的，这样评分效果就不完整） 
```
style.xml
```
<style   name="fiveRatingBar"parent="@android:style/Widget.RatingBar">
       <item   name="android:progressDrawable">@drawable/five_rating_bar</item>
       <item   name="android:minHeight">20dp</item>
       <item   name="android:maxHeight">20dp</item>
</style>
```

