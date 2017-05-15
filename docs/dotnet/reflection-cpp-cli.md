---
title: "反射 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], 反射"
  - "数据类型 [C++], 反射"
  - "GetType 方法"
  - "元数据, 反射"
  - "反射 [C++]"
  - "反射 [C++], 关于反射"
  - "typeid 关键字 [C++]"
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 反射 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

反射允许在运行时检查已知数据类型。  例如，反射允许使用给定程序集中的数据类型的枚举，并且可以发现给定类或值类型中的成员。  无论类型是否已知或者在编译时被引用，都是如此。  这使反射成为开发和代码管理工具的一项有用功能。  
  
 请注意，所提供的程序集名称是强名称（请参见[具有强名称的程序集](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)），其中包括程序集版本、区域性和签名信息。  另请注意，可以检索在其中定义数据类型的命名空间的名称以及基类的名称。  
  
 若要访问反射功能，最常见的方式是通过 <xref:System.Object.GetType%2A> 方法。  此方法由 [System::Object](https://msdn.microsoft.com/en-us/library/system.object.aspx) 提供，所有垃圾回收类都从其派生。  
  
 如果 .exe 是用 **\/clr:pure** 或 **\/clr:safe** 编译器选项生成的，允许使用用 Visual C\+\+ 编译器生成的 .exe 上的反射。  有关更多信息，请参见[\/clr（公共语言运行时编译）](../build/reference/clr-common-language-runtime-compilation.md)。  
  
 本节中的主题：  
  
-   [如何：使用反射实现插件组件体系结构](../dotnet/how-to-implement-a-plug-in-component-architecture-using-reflection-cpp-cli.md)  
  
-   [如何：使用反射枚举程序集中的数据类型](../dotnet/how-to-enumerate-data-types-in-assemblies-using-reflection-cpp-cli.md)  
  
 有关更多信息，请参见 [System.Reflection 命名空间](https://msdn.microsoft.com/en-us/library/system.reflection.aspx)  
  
## 示例  
 `GetType` 方法返回指向 <xref:System.Type> 类对象的指针，该类对象描述对象所基于的类型。（**“Type”**对象不包含任何实例特定信息。）类型的全名就是这样的对象，它可能显示如下：  
  
 请注意，类型名称包括整个类型定义范围（包括命名空间），并且以 .NET 语法显示（以点号作为范围解析运算符）。  
  
```  
// vcpp_reflection.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String ^ s = "sample string";  
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());  
}  
```  
  
  **样本字符串完整的类型名称是 'System.String'。**   
## 示例  
 值类型也可以与 `GetType` 函数一起使用，但它们必须首先装箱。  
  
```  
// vcpp_reflection_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Int32 i = 100;   
   Object ^ o = i;  
   Console::WriteLine("type of i = '{0}'", o->GetType());  
}  
```  
  
  **我的类型 \= 'System.Int32'**   
## 示例  
 与 `GetType` 方法一样，[typeid](../windows/typeid-cpp-component-extensions.md) 运算符将返回一个指向**“Type”**对象的指针，所以此代码指示类型名 **System.Int32**。  反射的最基本功能是显示类型名，但是可能更有用的技术是检查或发现枚举类型的有效值。  这可以通过使用静态 **Enum::GetNames** 函数来实现，该函数返回一个字符串数组，每个字符串包含文本形式的枚举值。下面的示例检索一个字符串数组，它描述**“Options”**\(CLR\) 枚举的值枚举值并在一个循环中显示这些值。  
  
 如果向**“Options”**枚举添加第四个选项，此代码将在不重新编译的情况下报告新的选项（即使该枚举是在单独的程序集中定义的）。  
  
```  
// vcpp_reflection_3.cpp  
// compile with: /clr  
using namespace System;  
  
enum class Options {   // not a native enum  
   Option1, Option2, Option3  
};  
  
int main() {  
   array<String^>^ names = Enum::GetNames(Options::typeid);  
  
   Console::WriteLine("there are {0} options in enum '{1}'",   
               names->Length, Options::typeid);  
  
   for (int i = 0 ; i < names->Length ; i++)  
      Console::WriteLine("{0}: {1}", i, names[i]);  
  
   Options o = Options::Option2;  
   Console::WriteLine("value of 'o' is {0}", o);  
}  
```  
  
  **枚举“Options”中有 3 个选项**  
**0: Option1**  
**1: Option2**  
**2: Option3**  
**“o”的值为 Option2**   
## 示例  
 `GetType` 对象支持大量可用来检查类型的成员和属性。  此代码检索并显示此信息中的一部分：  
  
```  
// vcpp_reflection_4.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Console::WriteLine("type information for 'String':");  
   Type ^ t = String::typeid;  
  
   String ^ assemblyName = t->Assembly->FullName;  
   Console::WriteLine("assembly name: {0}", assemblyName);  
  
   String ^ nameSpace = t->Namespace;  
   Console::WriteLine("namespace: {0}", nameSpace);  
  
   String ^ baseType = t->BaseType->FullName;  
   Console::WriteLine("base type: {0}", baseType);  
  
   bool isArray = t->IsArray;  
   Console::WriteLine("is array: {0}", isArray);  
  
   bool isClass = t->IsClass;  
   Console::WriteLine("is class: {0}", isClass);  
}  
```  
  
  **字符串的类型信息：**  
**程序集名称：mscorlib，版本\=1.0.5000.0，区域性\=neutral**  
**PublicKeyToken\=b77a5c561934e089**  
**命名空间： System**   
**基类型：System.Object**  
**为数组：False**  
**为类：True**   
## 示例  
 反射还允许枚举程序集内的类型和类中的成员。  为了说明此功能，请定义一个简单类：  
  
```  
// vcpp_reflection_5.cpp  
// compile with: /clr /LD  
using namespace System;  
public ref class TestClass {  
   int m_i;  
public:  
   TestClass() {}  
   void SimpleTestMember1() {}  
   String ^ SimpleMember2(String ^ s) { return s; }   
   int TestMember(int i) { return i; }  
   property int Member {  
      int get() { return m_i; }  
      void set(int i) { m_i = i; }  
   }  
};  
```  
  
## 示例  
 如果已将上面的代码编译到称为 vcpp\_reflection\_6.dll 的 DLL 中，则您可以使用反射检查此程序集的内容。  这包括使用静态反射 API 函数 [Assembly::Load](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.load.aspx) 来加载程序集。  此函数返回 **Assembly** 对象的地址，然后它可以在该对象中查询关于模块和类型的信息。  
  
 反射系统一旦成功加载程序集，即会用 [Assembly::GetTypes](https://msdn.microsoft.com/en-us/library/system.reflection.assembly.gettypes.aspx) 函数检索**“Type”**对象的数组。  每个数组元素都包含关于不同类型的信息（虽然本例中只定义了一个类）。  通过循环，将使用 **Type::GetMembers** 函数对此数组中的每个**“Type”**查询关于类型成员的信息。  此函数返回一个 **MethodInfo** 对象的数组，每个对象都包含关于类型中成员函数、数据成员或属性的信息。  
  
 请注意，方法列表包含在 **TestClass** 中显式定义的函数以及从 **System::Object** 类隐式继承的函数。  在用 .NET（而不是用 Visual C\+\+ 语法）进行描述时，属性将显示为由 get\/set 函数访问的基础数据成员。  get\/set 函数在此列表中显示为规则方法。  整个公共语言运行时都支持反射，但 Visual C\+\+ 编译器不支持反射。  
  
 虽然您使用此代码来检查已定义的程序集，但也可以使用此代码来检查 .NET 程序集。  例如，如果将 TestAssembly 更改为 mscorlib，则将看到在 mscorlib.dll 中定义的每个类型和方法的列表。  
  
```  
// vcpp_reflection_6.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
using namespace System::Reflection;  
int main() {  
   Assembly ^ a = nullptr;  
   try {  
      // load assembly -- do not use file extension  
      // will look for .dll extension first  
      // then .exe with the filename  
      a = Assembly::Load("vcpp_reflection_5");  
   }  
   catch (FileNotFoundException ^ e) {  
      Console::WriteLine(e->Message);  
      return -1;  
   }  
  
   Console::WriteLine("assembly info:");  
   Console::WriteLine(a->FullName);  
   array<Type^>^ typeArray = a->GetTypes();  
  
   Console::WriteLine("type info ({0} types):", typeArray->Length);  
  
   int totalTypes = 0;  
   int totalMembers = 0;  
   for (int i = 0 ; i < typeArray->Length ; i++) {  
      // retrieve array of member descriptions  
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();  
  
      Console::WriteLine("  members of {0} ({1} members):",   
      typeArray[i]->FullName, member->Length);  
      for (int j = 0 ; j < member->Length ; j++) {  
         Console::Write("       ({0})",   
         member[j]->MemberType.ToString() );  
         Console::Write("{0}  ", member[j]);  
         Console::WriteLine("");  
         totalMembers++;  
      }  
      totalTypes++;  
   }  
   Console::WriteLine("{0} total types, {1} total members",  
   totalTypes, totalMembers);  
}  
```  
  
## 请参阅  
 [使用 C\+\+\/CLI 进行 .NET 编程](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)