---
title: 如何： 确定映像是本机模式或 CLR |Microsoft Docs
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common language runtime, image testing
- images [C++], CLR verification
- /clr compiler option [C++], detecting use in compilation
- common language runtime, /clr compiler option
ms.assetid: 5a854822-6172-4b22-b236-320165412568
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5fb16fc3dfce2423b1d5d5b3b0e6249ac4824e7d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393004"
---
# <a name="how-to-determine-if-an-image-is-native-or-clr"></a>如何：确定映像为本机映像还是 CLR 映像

一种方法来确定某个映像是否已生成公共语言运行时是使用**dumpbin**[/CLRHEADER](../build/reference/clrheader.md)。

以编程方式还可以检查是否为公共语言运行时生成的映像。 有关详细信息，请参阅[如何： 检测 /clr 编译](../dotnet/how-to-detect-clr-compilation.md)。

## <a name="example"></a>示例

下面的示例确定是否生成的映像以在公共语言运行时上运行。

```
// detect_image_type.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

enum class CompilationMode {Invalid, Native, CLR };

static CompilationMode IsManaged(String^ filename) {
   try {
      array<Byte>^ data = gcnew array<Byte>(4096);
      FileInfo^ file = gcnew FileInfo(filename);
      Stream^ fin = file->Open(FileMode::Open, FileAccess::Read);
      Int32 iRead = fin->Read(data, 0, 4096);
      fin->Close();

      // Verify this is a executable/dll
      if ((data[1] << 8 | data[0]) != 0x5a4d)
         return CompilationMode::Invalid;

      // This will get the address for the WinNT header
      Int32 iWinNTHdr = data[63]<<24 | data[62]<<16 | data[61] << 8 | data[60];

      // Verify this is an NT address
      if ((data[iWinNTHdr+3] << 24 | data[iWinNTHdr+2] << 16 | data[iWinNTHdr+1] << 8 | data[iWinNTHdr]) != 0x00004550)
         return CompilationMode::Invalid;

      Int32 iLightningAddr = iWinNTHdr + 24 + 208;
      Int32 iSum = 0;
      Int32 iTop = iLightningAddr + 8;

      for (int i = iLightningAddr; i < iTop; ++i)
         iSum |= data[i];

      if (iSum == 0)
         return CompilationMode::Native;
      else
         return CompilationMode::CLR;
   }
   catch(Exception ^e) {
      throw(e);
   }
}

int main() {
   array<String^>^ args = Environment::GetCommandLineArgs();

   if (args->Length < 2) {
      Console::WriteLine("USAGE : detect_clr <assembly_name>\n");
      return -1;
   }

   Console::WriteLine("{0} is compiled {1}", args[1], IsManaged(args[1]));
}
```

## <a name="see-also"></a>请参阅

[使用 C++ 互操作（隐式 PInvoke）](../dotnet/using-cpp-interop-implicit-pinvoke.md)