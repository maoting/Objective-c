###数据类型-数据类型
Objective-C数据类型可以分为：基本数据类型、对象类型（指针类型）和构造类型。

 1. 基本数据类型有：int、float、double和char类型。Obejctive-C中数据类型可以在int、float、double和char类型前面加上限定词，限定词有：long、long long、short、unsigned和signed，这些限定词从而增强了基本类型。
 2. 对象类型：就是类或协议所声明的指针类型
   例如：NSAutoreleasePool * pool，其中NSAutoreleasePool是一个类，NSAutoreleasePool *是它指针类型。

PS: id类型可以表示任何类型，一般只是表示对象类型，不表示基本数据类型。

![数据类型](http://dl2.iteye.com/upload/attachment/0114/2079/dfccd838-222f-350a-94e9-98f855e96538.jpg)

###数据类型-NS数据类型
 - NSNumber是Objective-c的数字对象。需求考虑内存释放问题。
 - NSString和NSMutableString
   NSString是不可变字符串(NSContantString)，其变量和其本类型一样不需要手动释放（它的retainCount为-1）。
   NSMutableString是可变字符串，若用 “[[NSMutableString alloc] init...]”方法初始化，需要考虑手动释放。
 - NSArray和NSMutableArray
    NSArray是不可变数组，一般用于保存固定数据。和NSString不同的是，NSArray有retainCount，所以释放问题。
    NSMubleArray是变数组，可以直接对其值进行操作。也可考虑释放问题。
 - NSSet和NSMutableSet
    NSSet和NSMutableSet分别是不可变集合和可变集合。集合是一组单值的操作。NSSet和NSMutableSet都需要考虑释放问题。
 - NSDictionary和NSMutableDictionary
    dictionary是由键-对象对组成的数据集合。NSDictionay和NSMutableDicionary都需要考虑内存释放问题。

###运算符
 - 算术运算符：+、-、*、/
 - 关系运算符：==、!=、>、<、>=、<=
 - 逻辑运算符：！、&&、||

###接口
 - 定义：
 - 类定义从@interface开始，它表示了类的接口声明，冒号后指定了该类的父类，@end;表示类定义结束。Objective-c的类定义中类的变量定义与方法定义是分开的，花括号内写变量的定义，花括号外写类的方法定义。

 - 具体格式如下：

   >       \-        （void)        setName                :               (NSString)     input;
方法类型   返回类型     方法名称      方法接受参数        参数类型     参数名
    
 - 通用格式如下：
    +/- (返回类型) 名子1:(类型1) 参数1 名子2:(类型2) 参数2 ... 
    前面带有减号(-) 的方法为实例方法，必须使用类的实例才可以调用的。
    对应的有+号， 代表是类的静态方法，不需要实例化即可调用。一个参数的方法定义：- (void) setName: (NSString*) input;
二个参数的方法定义：- (void) setName: (NSString*) input  andSecondName:(NSString*) input1;

###属性@property
```
//Car.h
#import<Foundation/Foundation.h>
@interface NSObject
{
    //实例变量
    *carName;
    *carType;
}
@property(nonatomic,strong) NSString *carName;
@property(nonatomic,strong) NSString *carType;
@end
// Car.m
#import "Car.h"
@implementation Car
@synthesize carName;
@synthesize carType;
@end
```