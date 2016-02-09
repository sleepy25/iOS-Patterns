# iOS-Patterns

## Adapter

#### What is it ?

Its a wrapper around class giving it a new interface.

#### When use it ?

+  Converting interface of a class into another interface that clients expect without modifying their source code.

> You have to change the library in the project. Moving from google maps to apple maps.

+  Class you attend to use have very old interface. Example "dispatch_after" coded below.

```objc
@interface Timer : NSObject
+(void)dispatchAfter:(double)seconds block:(void (^)())block;
@end

@implementation Timer
+(void)dispatchAfter:(double)seconds block:(void (^)())block {
    dispatch_after(dispatch_time(DISPATCH_TIME_NOW, seconds * NSEC_PER_SEC), dispatch_get_main_queue(), task);
}
@end
```

```objc
[Timer dispatchAfter:10 block:^{
    NSLog(@"Print");
}];
    
              VS
    
dispatch_after(dispatch_time(DISPATCH_TIME_NOW, 10 * NSEC_PER_SEC), dispatch_get_main_queue(), ^{
    NSLog(@"Print");
});
```

#### More info :
<https://sourcemaking.com/design_patterns/adapter>

<http://www.tutorialspoint.com/design_pattern/adapter_pattern.htm>

<http://www.oodesign.com/adapter-pattern.html>

<https://en.wikipedia.org/wiki/Adapter_pattern>

## Decorator

#### What is it ?


#### When use it ?

```objc
[Timer new];
```
#### More info :
