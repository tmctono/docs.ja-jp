---
title: コンパイラの警告 CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 6147fc1aafc06d7c844cfc39eafebbd737d89610
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69601960"
---
# <a name="compiler-warning-cs3024"></a><span data-ttu-id="c0625-102">コンパイラの警告 CS3024</span><span class="sxs-lookup"><span data-stu-id="c0625-102">Compiler Warning CS3024</span></span>
<span data-ttu-id="c0625-103">制約型 'type' が CLS に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="c0625-103">Constraint type 'type' is not CLS-compliant.</span></span>  
  
 <span data-ttu-id="c0625-104">CLS 非準拠の型をジェネリック型制約として使用すると、一部の言語で記述されたコードがジェネリック クラスを使用できなくなる可能性があるため、コンパイラはこの警告を発行します。</span><span class="sxs-lookup"><span data-stu-id="c0625-104">The compiler issues this warning because the use of a non-CLS-compliant type as a generic type constraint could make it impossible for code written in some languages to consume your generic class.</span></span>  
  
### <a name="to-eliminate-this-warning"></a><span data-ttu-id="c0625-105">この警告を回避するには</span><span class="sxs-lookup"><span data-stu-id="c0625-105">To eliminate this warning</span></span>  
  
1. <span data-ttu-id="c0625-106">型制約には、CLS 準拠の型を使用します。</span><span class="sxs-lookup"><span data-stu-id="c0625-106">Use a CLS-compliant type for the type constraint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0625-107">例</span><span class="sxs-lookup"><span data-stu-id="c0625-107">Example</span></span>  
 <span data-ttu-id="c0625-108">次の例では、複数の場所で CS3024 が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c0625-108">The following example generates CS3024 in several locations:</span></span>  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0625-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0625-109">See also</span></span>

- [<span data-ttu-id="c0625-110">型パラメーターの制約</span><span class="sxs-lookup"><span data-stu-id="c0625-110">Constraints on Type Parameters</span></span>](../programming-guide/generics/constraints-on-type-parameters.md)
