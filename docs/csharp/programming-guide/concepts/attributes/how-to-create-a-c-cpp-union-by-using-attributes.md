---
title: 属性を使用して C/C++ の共用体を作成する方法 (C#)
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: ff8ce560444581a28b257820573224f89a274cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141573"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="a4681-102">属性を使用して C/C++ の共用体を作成する方法 (C#)</span><span class="sxs-lookup"><span data-stu-id="a4681-102">How to create a C/C++ union by using attributes (C#)</span></span>

<span data-ttu-id="a4681-103">属性を使用すると、構造体のメモリ内での配置をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="a4681-103">By using attributes, you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="a4681-104">たとえば、`StructLayout(LayoutKind.Explicit)` 属性と `FieldOffset` 属性を使用すると、C/C++ の共用体と呼ばれるものを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a4681-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="a4681-105">例</span><span class="sxs-lookup"><span data-stu-id="a4681-105">Example</span></span>

<span data-ttu-id="a4681-106">このコード セグメントでは、`TestUnion` のすべてのフィールドがメモリ内の同じ場所で開始されます。</span><span class="sxs-lookup"><span data-stu-id="a4681-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

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

## <a name="example"></a><span data-ttu-id="a4681-107">例</span><span class="sxs-lookup"><span data-stu-id="a4681-107">Example</span></span>

<span data-ttu-id="a4681-108">次の例でも、明示的に設定されたさまざまな場所でフィールドが開始されます。</span><span class="sxs-lookup"><span data-stu-id="a4681-108">The following is another example where fields start at different explicitly set locations.</span></span>

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

<span data-ttu-id="a4681-109">2 つの整数フィールド、`i1` および `i2` は、`lg` と同じメモリ位置を共有します。</span><span class="sxs-lookup"><span data-stu-id="a4681-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="a4681-110">このような構造体配置の制御は、プラットフォームを呼び出すときに便利です。</span><span class="sxs-lookup"><span data-stu-id="a4681-110">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4681-111">参照</span><span class="sxs-lookup"><span data-stu-id="a4681-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="a4681-112">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="a4681-112">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="a4681-113">属性</span><span class="sxs-lookup"><span data-stu-id="a4681-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="a4681-114">リフレクション (C#)</span><span class="sxs-lookup"><span data-stu-id="a4681-114">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="a4681-115">属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="a4681-115">Attributes (C#)</span></span>](index.md)
- [<span data-ttu-id="a4681-116">カスタム属性の作成 (C#)</span><span class="sxs-lookup"><span data-stu-id="a4681-116">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="a4681-117">リフレクションを使用した属性へのアクセス (C#)</span><span class="sxs-lookup"><span data-stu-id="a4681-117">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
