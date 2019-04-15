#RatingBar 显示整数个星星时出现半个或星星显示一点的问题
RatingBar 设置 stepSize= 1.0 ，numStars=6，rating=3，这种情况下出现 第四个星星最左边的星星一角也显示了或者第四星星显示了少半个，
解决方法：
RatingBar.setMax(numStars),设置数目和numStars一样就可以；
