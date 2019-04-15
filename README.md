# RatingBar
RatingBar是基于SeekBar（拖动条）和ProgressBar（状态条）的扩展，用星形来显示等级评定！
使用RatingBar的默认大小时，用户可以触摸/拖动或使用键来设置评分，它有两种样式(小风格用ratingBarStyleSmall，大风格用ratingBarStyleIndicator)，其中大的只适合指示，不适合于用户交互。

只有当布局的宽被设置为wrap content时，设置的星星数量（通过函数setNumStars(int)或者在XML的布局文件中定义）将显示出来（如果设置为另一种布局宽的话，后果无法预知）。次级进度一般不应该被修改，因为他仅仅是被当作星型部分内部的填充背景。

xml属性：
```
android:isIndicator ：RatingBar是否是一个指示器（用户无法进行更改）

android:numStars： 显示的星型数量，必须是一个整形值，像“100”。

android:rating： 默认的评分，必须是浮点类型，像“1.2”。

android:stepSize：评分的步长，必须是浮点类型，像“1.2”。
```

公共方法
```
public int getNumStars () ：返回显示的星型数量

public RatingBar.OnRatingBarChangeListener getOnRatingBarChangeListener ()：返回值->监听器（可能为空）监听评分改变事件

public float getRating ():获取当前的评分（填充的星型的数量）

public float getStepSize ():获取评分条的步长

public boolean isIndicator ():返回值->判断当前的评分条是否仅仅是一个指示器（注：即能否被修改）

public void setIsIndicator (boolean isIndicator):设置当前的评分条是否仅仅是一个指示器（这样用户就不能进行修改操作了）
参数:isIndicator -> Bool值，是否是一个指示器

public synchronized void setMax (int max):设置评分等级的范围，从0到max
参数:max ->评分条最大范围。

public void setNumStars (int numStars):设置显示的星型的数量。`为了能够正常显示它们，建议将当前widget的布局宽度设置为 wrap content`
参数:numStars ->星型的数量

public void setOnRatingBarChangeListener (RatingBar.OnRatingBarChangeListener listener):设置当评分等级发生改变时回调的监听器
 
public void setRating (float rating):设置分数（星型的数量）
参数:rating->设置的分数

public void setStepSize (float stepSize):设置当前评分条的步长（step size）
参数:stepSize->评分条的步进。例如：如果想要半个星星，它的值为0.5。
```





