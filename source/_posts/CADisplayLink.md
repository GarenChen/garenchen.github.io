title: CADisplayLink简介
toc: true
category: 软件开发
tag: [iOS, CoreAnimation]

---

CADisplayLink是与屏幕刷新频率相同的一个定时器,通常用来绘图,使自定义绘图的刷新频率和屏幕的刷新频率相同(60帧的刷新频率)

<!--more-->

## 接口和属性

#### 1.接口

```
+ (CADisplayLink *)displayLinkWithTarget:(id)target selector:(SEL)sel;
```
生成一个display link 实例,制定target和调用方法,方法签名为`'(void)selector:(CADisplayLink *)sender'`

```
- (void)addToRunLoop:(NSRunLoop *)runloop forMode:(NSRunLoopMode)mode;
```
将display link 实例注册到一个runloop中

```
- (void)invalidate;
```
将display link从所有的runloop中移除,并释放

#### 2.属性
```
@property(readonly, nonatomic) CFTimeInterval duration;
```
两次刷新之间的时间间隔

```
@property(readonly, nonatomic) CFTimeInterval timestamp
```
当前帧的时间

```
@property(readonly, nonatomic) CFTimeInterval targetTimestamp
```
下一帧渲染的时间

```
@property(nonatomic) NSInteger preferredFramesPerSecond
```
首选每秒帧数,默认为0,会按照设备的每秒最大帧数刷新(60帧每秒),当需要比较慢的频率刷新时可以设置该属性

```
@property(getter=isPaused, nonatomic) BOOL paused;
```
为true时,当前实例禁止触发,默认为false

## 注意
`duration`属性返回的时间间隔是根据`maximumFramesPerSecond`属性得来的,如果要计算实际的时间间隔,用`timestamp - targetTimestamp `得出    

当程序暂时不需要相应display link实例的事件回调时,可以通过将`pause`设置为false或true来暂停和启用display link实例        

CADisplayLink不应该被子类化





