---
title: 方法:属性を使用して C/C++ の共用体を作成する (C#)
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: fdadc9505b93f40c66001ac36345efada2edd270
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595371"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="28014-102">方法:属性を使用して C/C++ の共用体を作成する (C#)</span><span class="sxs-lookup"><span data-stu-id="28014-102">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>
<span data-ttu-id="28014-103">属性を使用すると、構造体のメモリ内での配置をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="28014-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="28014-104">たとえば、`StructLayout(LayoutKind.Explicit)` 属性と `FieldOffset` 属性を使用すると、C/C++ の共用体と呼ばれるものを作成できます。</span><span class="sxs-lookup"><span data-stu-id="28014-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28014-105">例</span><span class="sxs-lookup"><span data-stu-id="28014-105">Example</span></span>  
 <span data-ttu-id="28014-106">このコード セグメントでは、`TestUnion` のすべてのフィールドがメモリ内の同じ場所で開始されます。</span><span class="sxs-lookup"><span data-stu-id="28014-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a><span data-ttu-id="28014-107">例</span><span class="sxs-lookup"><span data-stu-id="28014-107">Example</span></span>  
 <span data-ttu-id="28014-108">次の例でも、明示的に設定されたさまざまな場所でフィールドが開始されます。</span><span class="sxs-lookup"><span data-stu-id="28014-108">The following is another example where fields start at different explicitly set locations.</span></span>  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 <span data-ttu-id="28014-109">2 つの整数フィールド、`i1` および `i2` は、`lg` と同じメモリ位置を共有します。</span><span class="sxs-lookup"><span data-stu-id="28014-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="28014-110">このような構造体配置の制御は、プラットフォームを呼び出すときに便利です。</span><span class="sxs-lookup"><span data-stu-id="28014-110">This sort of control over struct layout is useful when using platform invocation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28014-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="28014-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="28014-112">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="28014-112">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="28014-113">属性</span><span class="sxs-lookup"><span data-stu-id="28014-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="28014-114">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="28014-114">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="28014-115">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="28014-115">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="28014-116">カスタム属性の作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="28014-116">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
- [<span data-ttu-id="28014-117">リフレクションを使用した属性へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="28014-117">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
