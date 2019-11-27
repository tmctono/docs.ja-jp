---
title: '方法: 属性を使用してC++ C 共用体を作成する'
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: acb8dc781e2872ae46e5aa058a98b3dd98f3e064
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349499"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a><span data-ttu-id="7b83d-102">方法: 属性を使用してC++ C/共用体を作成する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b83d-102">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>

<span data-ttu-id="7b83d-103">属性を使用すると、構造体のメモリ内での配置をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7b83d-103">By using attributes you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="7b83d-104">たとえば、`StructLayout(LayoutKind.Explicit)` 属性と `FieldOffset` 属性を使用すると、C/C++ の共用体と呼ばれるものを作成できます。</span><span class="sxs-lookup"><span data-stu-id="7b83d-104">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="7b83d-105">例</span><span class="sxs-lookup"><span data-stu-id="7b83d-105">Example</span></span>

<span data-ttu-id="7b83d-106">このコード セグメントでは、`TestUnion` のすべてのフィールドがメモリ内の同じ場所で開始されます。</span><span class="sxs-lookup"><span data-stu-id="7b83d-106">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

```vb
' Add an Imports statement for System.Runtime.InteropServices.

<System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestUnion
    <System.Runtime.InteropServices.FieldOffset(0)>
    Public i As Integer

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public d As Double

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public c As Char

    <System.Runtime.InteropServices.FieldOffset(0)>
    Public b As Byte
End Structure
```

## <a name="example"></a><span data-ttu-id="7b83d-107">例</span><span class="sxs-lookup"><span data-stu-id="7b83d-107">Example</span></span>

<span data-ttu-id="7b83d-108">次の例でも、明示的に設定されたさまざまな場所でフィールドが開始されます。</span><span class="sxs-lookup"><span data-stu-id="7b83d-108">The following is another example where fields start at different explicitly set locations.</span></span>

```vb
' Add an Imports statement for System.Runtime.InteropServices.

 <System.Runtime.InteropServices.StructLayout(
      System.Runtime.InteropServices.LayoutKind.Explicit)>
Structure TestExplicit
     <System.Runtime.InteropServices.FieldOffset(0)>
     Public lg As Long

     <System.Runtime.InteropServices.FieldOffset(0)>
     Public i1 As Integer

     <System.Runtime.InteropServices.FieldOffset(4)>
     Public i2 As Integer

     <System.Runtime.InteropServices.FieldOffset(8)>
     Public d As Double

     <System.Runtime.InteropServices.FieldOffset(12)>
     Public c As Char

     <System.Runtime.InteropServices.FieldOffset(14)>
     Public b As Byte
 End Structure
```

<span data-ttu-id="7b83d-109">2 つの整数フィールド、`i1` および `i2` は、`lg` と同じメモリ位置を共有します。</span><span class="sxs-lookup"><span data-stu-id="7b83d-109">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="7b83d-110">このような構造体配置の制御は、プラットフォームを呼び出すときに便利です。</span><span class="sxs-lookup"><span data-stu-id="7b83d-110">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b83d-111">参照</span><span class="sxs-lookup"><span data-stu-id="7b83d-111">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="7b83d-112">Visual Basic のプログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="7b83d-112">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="7b83d-113">属性</span><span class="sxs-lookup"><span data-stu-id="7b83d-113">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="7b83d-114">リフレクション (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b83d-114">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="7b83d-115">属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b83d-115">Attributes (Visual Basic)</span></span>](../../../../visual-basic/language-reference/attributes.md)
- [<span data-ttu-id="7b83d-116">カスタム属性の作成 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b83d-116">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [<span data-ttu-id="7b83d-117">リフレクションを使用した属性へのアクセス (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b83d-117">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
