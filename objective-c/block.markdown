对于block外的变量引用，block默认是将其复制到其数据结构中来实现访问的.
对于用__block修饰的外部变量引用，block是复制其引用地址来实现访问的.

```objective-c
int a = 1;
void (^block)() = ^() {
  NSLog(@"in block, a = %d", a);
};
a = 2;
block();
NSLog(@"out block, a = %d", a);
```
in block, a = 2
out block, a = 2

```objective-c
__block int a = 1;
void (^block)() = ^() {
  NSLog(@"in block, a = %d", a);
};
a = 2;
block();
NSLog(@"out block, a = %d", a);
```
in block, a = 1
out block, a = 2
