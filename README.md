![Simulator Screen Shot - iPhone 8 - 2021-02-05 at 15.58.50.png](https://upload-images.jianshu.io/upload_images/532541-fdba3d585999cf2a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
- (void)changeColor
{
    UIColor *color0 = [[UIColor blueColor] colorWithAlphaComponent:0.0];
    UIColor *color1 = [[UIColor blueColor] colorWithAlphaComponent:0.6];
    [self colorGradientFrom:color0 toColor:color1 startP:CGPointMake(0, 0) EndP:CGPointMake(0, 1) SubView:self.xxView];
}
- (void)changeColor2
{
    UIColor *color0 = [[UIColor redColor] colorWithAlphaComponent:0.6];
    UIColor *color1 = [[UIColor redColor] colorWithAlphaComponent:0.0];
    [self colorGradientFrom:color0 toColor:color1 startP:CGPointMake(0, 0) EndP:CGPointMake(0, 1) SubView:self.yyView];
}
/// 渐变色
- (void)colorGradientFrom:(UIColor*)color0 toColor:(UIColor*)color1 startP:(CGPoint)point0 EndP:(CGPoint)point1 SubView:(UIView*)subView
{
    //渐变设置
    CAGradientLayer *gradient = [CAGradientLayer layer];
    NSArray *colors = [NSArray arrayWithObjects:(id)color0.CGColor, (id)color1.CGColor, nil];
    //设置开始和结束位置(通过开始和结束位置来控制渐变的方向)
    gradient.startPoint = point0;
    gradient.endPoint = point1;
    gradient.colors = colors;
    gradient.locations = @[@(0.0),@(1.0f)];
    gradient.frame = CGRectMake(0, 0, subView.bounds.size.width, subView.bounds.size.height);
    [subView.layer insertSublayer:gradient atIndex:0];
}
```
