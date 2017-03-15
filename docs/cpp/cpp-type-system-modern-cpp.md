---
title: "C++ 类型系统（现代 C++） | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
caps.latest.revision: 24
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 类型系统（现代 C++）
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

在 C\+\+ 中，类型的概念是非常重要的。  每个变量、函数参数和函数返回值必须具有一个类型以进行编译。  此外，在计算表达式前，编译器会给出每个表达式（包括文本值）的隐式类型。  一些类型示例包括用于存储整数值的 `int`、用于存储浮点值（也叫标量数据类型）的 `double` 或用于存储文本的标准库类 [std::basic\_string](../standard-library/basic-string-class.md)。  可以通过定义 `class` 或 `struct` 创建自己的类型。  该类型指定将分配给变量（或表达式结果）的内存量、可能存储在该变量中的值类型、如何对那些值（作为位模式）进行说明以及可对其执行的操作。  本文包含对 C\+\+ 类型系统的主要功能的非正式概述。  
  
## 术语  
 **变量**：数据量的符号名，该名称可以用于访问定义该代码的范围内所指的数据。  在 C\+\+ 中，“变量”通常用于指标量数据类型的实例，而其他类型的实例通常称为“对象”。  
  
 **对象**：为了简易性和一致性，本文使用术语“对象”指代类或结构的所有实例，用于一般意义时（包括所有类型甚至标量变量），也使用“对象”。  
  
 **POD 类型**（纯旧数据）：C\+\+ 中的此类非正式数据类型类别是指作为标量（参见基础类型部分）的类型或 POD 类。  POD 类没有不是 POD 的静态数据成员，没有用户定义的构造函数、用户定义的析构函数或用户定义的赋值运算符。  此外，POD 类无虚函数、基类、私有的或受保护的非静态数据成员。  POD 类型通常用于外部数据交换，例如与用 C 语言编写的模块（仅具有 POD 类型）进行的数据交换。  
  
## 指定变量和函数类型  
 C\+\+ 是一种“强类型化”语言，也是一种“静态类型化”语言；每个对象都有一个类型，且该类型从不会更改（请不要与静态数据对象混淆）。           
 在代码中**声明变量时**，你必须显式指定其类型或使用 `auto` 关键字指示编译器通过初始值设定项推断类型。           
 在代码中**声明函数时**，你必须指定每个参数的类型及其返回值；如果函数未返回任何值，则指定 `void`。  例外情况是，当使用允许任意类型参数的函数模板时。  
  
 在你首次声明变量后，稍后无法更改其类型。  但是，你可以将变量的值或函数的返回值复制到其他类型的另一个变量中。  此类操作称作“类型转换”，这些操作有时很必要，但也是造成数据丢失或不正确的潜在原因。  
  
 在声明 POD 类型的变量时，强烈建议你将其初始化，也就是为其指定初始值。  在初始化某个变量之前，该变量会有一个“垃圾”值，该值包含之前正好位于该内存位置的位数。  这是需要注意的 C\+\+ 的一个重要方面，尤其是当你使用另一种语言来处理初始化时。  如果声明非 POD 类类型的变量，则构造函数会处理初始化。  
  
 下面的示例演示了一些简单变量声明，并分别对它们进行了说明。  该示例还演示了编译器如何使用类型信息允许或禁止对变量进行某些后续操作。  
  
```  
  
int result = 0;              // Declare and initialize an integer.  
double coefficient = 10.8;   // Declare and initialize a floating   
                             // point value.  
auto name = "Lady G.";       // Declare a variable and let compiler   
                             // deduce the type.  
auto address;                // error. Compiler cannot deduce a type   
                             // without an intializing value.  
age = 12;                    // error. Variable declaration must  
                             // specify a type or use auto!  
result = "Kenny G.";         // error. Can’t assign text to an int.  
string result = "zero";      // error. Can’t redefine a variable with  
                             // new type.  
int maxValue;                // Not recommended! maxValue contains   
                             // garbage bits until it is initialized.  
  
```  
  
## 基本（内置）类型  
 不同于某些语言，C\+\+ 中不存在派生所有其他类型的通用基类型。  该语言的 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 实现包括许多基本类型（也称为“内置类型”）。  这包括数字类型，例如 `int`、`double`、`long`、`bool` 以及分别针对 ASCII 和 UNICODE 字符的 `char` 和 `wchar_t` 类型。  大多数基础类型（`bool`、`double`、`wchar_t` 和相关类型除外）都具有未签名的版本，这些版本修改了变量可存储的值的范围。  例如，`int`（存储了 32 位已签名整数）可表示介于 \-2,147,483,648 和 2,147,483,647 之间的值。  `unsigned int`（也是存储为 32 位）可存储介于 0 和 4,294,967,295 之间的值。  可能的值的总数在每种情况下都相同；仅范围不同。  
  
 基础类型由编译器识别，编译机包含内置规则，这些规则管理可对它们执行的操作以及将它们转换为其他基础类型的方式。  有关内置类型及其大小和数值限制的完整列表，请参见[基本类型](../cpp/fundamental-types-cpp.md)。  
  
 下图显示了内置类型的相对大小：  
  
 ![内置类型大小（以字节为单位）](../cpp/media/built-intypesizes.png "Built\-inTYpeSizes")  
  
 下表列出了最常用的基础类型：  
  
|类型|大小|注释|  
|--------|--------|--------|  
|int|4 个字节|整数值的默认选择。|  
|double|8 个字节|浮点值的默认选择。|  
|bool|1 个字节|表示可为 true 或 false 的值。|  
|char|1 个字节|用于早期 C 样式字符串或 std:: 字符串对象中无需转换为 UNICODE 的 ASCII 字符。|  
|wchar\_t|2 个字节|表示可能以 UNICODE 格式进行编码的“宽”字符值（Windows 上为 UTF\-16，其他操作系统上可能不同）。  这是用于 `std::wstring` 类型字符串的字符类型。|  
|unsigned char|1 个字节|C\+\+ 无内置 `byte` 类型。使用 unsigned char 表示字节值。|  
|unsigned int|4 个字节|位标志的默认选项。|  
|long long|8 个字节|表示非常大的整数值。|  
  
## void 类型  
 `void` 类型是一种特殊类型；你不能声明 `void` 类型的变量，但可声明 `void *` 类型的变量（指向 `void` 的指针），有时当分配原始（非类型化）内存时这么做是很必要的。  但指向 `void` 的指针不是类型安全的指针，强烈建议通常不要在现代 C\+\+ 中使用它们。  在函数声明中，`void` 返回值表示函数不返回值；这是 `void` 的常见和可接受用法。  尽管 C 语言需要含零个参数的函数以在参数列表中声明 `void`（例如 `fou(void)`），但现代 C\+\+ 中不鼓励此做法，而应声明 `fou()`。  有关详细信息，请参阅[类型转换和类型安全](../cpp/type-conversions-and-type-safety-modern-cpp.md)。  
  
## const 类型限定符  
 任何内置或用户定义的类型都可由 const 关键字限定。  此外，成员函数可以受 `const` 限定甚至可以重载 `const`。  `const` 类型的值在初始化后将无法修改。  
  
```  
  
const double PI = 3.1415;  
PI = .75 //Error. Cannot modify const variable.  
  
```  
  
 `const` 限定符在函数和变量声明中使用广泛，并且“const 有效性”是 C\+\+ 中的一个重要概念；它实质上表示使用 `const` 以确保在编译时不会无意中修改值。  有关详细信息，请参阅 [const](../cpp/const-cpp.md)。  
  
 `const` 类型与其非常数版本截然不同；例如，`const int` 是与 `int` 截然不同的类型。  如果发生你必须从变量中移除 *const\-ness* 的这类少数情况，可以使用 C\+\+ `const_cast` 运算符。  有关详细信息，请参阅[类型转换和类型安全](../cpp/type-conversions-and-type-safety-modern-cpp.md)。  
  
## 字符串类型  
 严格来说，C\+\+ 语言没有内置的“字符串”类型；`char` 和 `wchar_t` 存储单个字符 \- 必须声明这些类型的数组以估计字符串，将一个终止 null 值（例如，ASCII `‘\0’`）添加到最后一个有效字符数后的数组元素（也称为“C 样式字符串”）。  C 样式字符串需要编写更多的代码或者需要使用外部字符串实用工具库函数。  但在现代 C\+\+ 中，我们可以使用标准库类型 `std::string`（用于 8 位 `char` 型字符串）或 `std::wstring`（用于 16 位 `wchar_t` 型字符串）。  这些 STL 容器可视为本机字符串类型，因为它们是所有兼容 C\+\+ 生成环境所包括的标准库的一部分。  只需使用 `#include <string>` 指令即可使这些类型在你的程序中可用。（如果使用的是 MFC 或 ATL，还可使用 CString 类，但其不符合 C\+\+ 标准。）强烈建议你不要在现代 C\+\+ 中使用 null 终止字符数组（前面提到的 C 样式字符串）。  
  
## 用户定义的类型  
 在定义 `class`、`struct`、`union` 或 `enum` 时，该构造会以基础类型的形式用在你其余的代码中。  它具有内存的已知大小以及一些有关可以如何在程序生命期内将其用于编译时检查和运行时的规则。  基本内置类型和用户定义的类型之间的主要区别如下：  
  
-   编译器没有用户定义的类型的内置知识。  它在编译过程中首次遇到此定义时就“学习”了此类型。  
  
-   通过定义（通过重载）适当的运算符作为类成员或非成员函数，可以指定可对你的类型执行的操作以及你的类型转换为其他类型的方式。  有关详细信息，请参阅[重载 （c \+ \+）](../misc/overloading-cpp.md)。  
  
-   不必将它们静态类型化（对象类型的规则从不改变）。  通过继承和多态性机制，声明为类的用户定义的类型（称为类的对象实例）的变量在运行时具有的类型不同于在编译时具有的类型。  有关详细信息，请参阅[继承](../cpp/inheritance-cpp.md)。  
  
## 指针类型  
 追溯到 C 语言的最早版本，C\+\+ 继续通过使用特殊声明符 `*`（星号）声明指针类型的变量。  指针类型在存储实际数据值的内存中存储位置地址。  在现代 C\+\+ 中，它们被称为“原始指针”，通过特殊运算符 `*`（星号）或 `->`（带大于号的短划线）在代码中进行访问。  这称为“取消引用”，使用哪一个取决于你想取消对象中指向标量的指针还是指向成员的指针。  使用指针类型很长时间以来都是 C 和 C\+\+ 程序开发的最具挑战性和最难以理解的方面之一。  如果你需要，本节概述了一些有助于使用原始指针的情况和做法，但是由于[智能指针](../cpp/smart-pointers-modern-cpp.md)的发展（在本节最后详细讨论），现代 C\+\+ 不再需要（建议）将原始指针用于对象所有权。  使用原始指针来观察对象仍是有用且安全的，但如果必须将其用于对象所有权，则需要谨慎操作并仔细考虑如何创建和销毁其所有的对象。  
  
 首先你应该知道的是，声明一个原始指针变量只会分配存储了取消指针时需引用的内存地址的内存。  尚未分配数据值本身的内存分配（也称为“后备存储”）。  换言之，通过声明原始指针变量，将创建内存地址变量而非实际数据变量。  在确保指针变量包含指向备份存储的有效地址前取消对其的引用将导致程序发生未定义行为（通常为严重错误）。  下面的示例演示了此种错误：  
  
```  
  
int* pNumber;       // Declare a pointer-to-int variable.  
*pNumber = 10;      // error. Although this may compile, it is  
                    // a serious error. We are dereferencing an  
                    // uninitialized pointer variable with no  
                    // allocated memory to point to.  
  
```  
  
 该示例取消引用指针类型，未分配用于存储实际整数数据的任何内存或向其分配有效内存地址。  下面的代码更正这些错误：  
  
```  
  
    int number = 10;          // Declare and initialize a local integer  
                              // variable for data backing store.  
    int* pNumber = &number;   // Declare and initialize a local integer  
                              // pointer variable to a valid memory  
                              // address to that backing store.  
...  
    *pNumber = 41;            // Dereference and store a new value in   
                              // the memory pointed to by  
                              // pNumber, the integer variable called  
                              // “number”. Note “number” was changed, not  
                              // “pNumber”.  
  
```  
  
 已纠正的代码示例使用本地堆栈内存创建 `pNumber` 指向的后备存储。  我们使用基本类型，以求简单。  实际上，指针的后备存储通常为用户定义的类型，这些类型通过使用 `new` 关键字表达式（在 C 样式编程中，使用以前的 `malloc()` C 运行库函数）在名为“堆”的内存区域中动态分配。  分配后，这些“变量”通常指“对象”，尤其是基于类定义这些变量的情况下。  使用 `new` 分配的内存必须由相应的 `delete` 语句删除（或者，如果使用 `malloc()` 函数进行关联，则使用 C 运行时函数 `free()` 执行删除操作）。  
  
 但是，很容易忘记删除动态分配的对象（特别是在复杂代码中），这会导致名为“内存泄漏”的资源 Bug 产生。  为此，强烈建议你不要在现代 C\+\+ 中使用原始指针。  将原始指针包装到[智能指针](../cpp/smart-pointers-modern-cpp.md)中始终是更好的做法，这将在调用析构函数时自动释放内存（当代码超出智能指针的范围时）；使用智能指针几乎消除了 C\+\+ 程序中的所有 Bug 类。  在下面的示例中，假定 `MyClass` 是具有公共方法 `DoSomeWork();` 的用户定义的类型  
  
```  
  
void someFunction() {  
    unique_ptr<MyClass> pMc(new MyClass);  
    pMc->DoSomeWork();  
}  
  // No memory leak. Out-of-scope automatically calls the destructor  
  // for the unique_ptr, freeing the resource.  
  
```  
  
 有关智能指针的更多信息，请参见[智能指针](../cpp/smart-pointers-modern-cpp.md)。  
  
 有关指针转换的更多信息，请参见[类型转换和类型安全](../cpp/type-conversions-and-type-safety-modern-cpp.md)。  
  
 有关指针的更多信息，请参见[指针](../cpp/pointers-cpp.md)。  
  
## Windows 数据类型  
 在 C 和 C\+\+ 的经典 Win32 编程中，大多数函数使用 Windows 特定的 Typedef 和 \#define 宏（在 `windef.h` 中定义）来指定参数类型和返回值。  这些“Windows 数据类型”通常只是为 C\/C\+\+ 内置类型提供的特殊名称（别名）。  有关这些 typedef 和预处理器定义的完整列表，请参见 [Windows Data Types](http://msdn.microsoft.com/zh-cn/4553cafc-450e-4493-a4d4-cb6e2f274d46)。  这些 typedef 中的一些（例如 HRESULT 和 LCID）有用且具有描述性。  诸如 INT 的其他数据没有特殊含义，并且只是基础 C\+\+ 类型的别名。  其他 Windows 数据类型的名称自 C 编程和 16 位处理器得到保留，并且在现代硬件或操作系统中不具有目的和意义。  还有列为 [Windows Runtime base data types](http://msdn.microsoft.com/zh-cn/b5735851-ec07-48c1-92b4-ca9f768096f6)的与 Windows 运行库相关的特定数据类型。  在现代 C\+\+ 中，一般准则是首选 C\+\+ 基本类型，除非 Windows 类型传达一些有关如何解释值的附加意义。  
  
## 更多信息  
 有关 C\+\+ 类型系统的更多信息，请参见下列主题。  
  
|||  
|-|-|  
|[值类型](../cpp/value-types-modern-cpp.md)|描述值类型以及与其使用相关的问题。|  
|[类型转换和类型安全](../cpp/type-conversions-and-type-safety-modern-cpp.md)|描述常见类型转换问题并说明如何避免这些问题出现。|  
  
## 请参阅  
 [欢迎回到 C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+ 语言参考](../cpp/cpp-language-reference.md)   
 [C\+\+ 标准库](../standard-library/cpp-standard-library-reference.md)