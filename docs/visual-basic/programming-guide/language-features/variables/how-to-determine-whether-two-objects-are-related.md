---
title: '方法: 2つのオブジェクトが関連付けられているかどうかを判断する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: 2b17be4ef5a7dabfc4779ab6f5675cc2baec9c3c
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626557"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="641fb-102">方法: 2つのオブジェクトが関連付けられているかどうかを判断する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="641fb-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="641fb-103">2つのオブジェクトを比較して、作成元のクラス間のリレーションシップ (存在する場合) を判断できます。</span><span class="sxs-lookup"><span data-stu-id="641fb-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="641fb-104">クラスのメソッドは<xref:System.Type.IsInstanceOfType%2A> 、指定`True`したクラスが現在のクラスから継承している場合、または現在の型が指定したクラスでサポートされているインターフェイスである場合にを返します。 <xref:System.Type?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="641fb-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="641fb-105">あるオブジェクトが別のオブジェクトのクラスまたはインターフェイスから継承しているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="641fb-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="641fb-106">基本型と考えられるオブジェクトで、 <xref:System.Object.GetType%2A>メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="641fb-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="641fb-107">によって<xref:System.Object.GetType%2A>返される<xref:System.Type.IsInstanceOfType%2A>オブジェクトで、メソッドを呼び出します。 <xref:System.Type?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="641fb-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="641fb-108">の<xref:System.Type.IsInstanceOfType%2A>引数リストで、派生型として考えられるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="641fb-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="641fb-109"><xref:System.Type.IsInstanceOfType%2A>引数`True`の型がオブジェクト型から継承<xref:System.Type?displayProperty=nameWithType>される場合は、を返します。</span><span class="sxs-lookup"><span data-stu-id="641fb-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="641fb-110">例</span><span class="sxs-lookup"><span data-stu-id="641fb-110">Example</span></span>
 <span data-ttu-id="641fb-111">次の例では、あるオブジェクトが、別のオブジェクトのクラスから派生したクラスを表しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="641fb-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

```vb
Public Class baseClass
End Class
Public Class derivedClass : Inherits baseClass
End Class
Public Class testTheseClasses
    Public Sub seeIfRelated()
        Dim baseObj As Object = New baseClass()
        Dim derivedObj As Object = New derivedClass()
        Dim related As Boolean
        related = baseObj.GetType().IsInstanceOfType(derivedObj)
        MsgBox(CStr(related))
    End Sub
End Class
```

<span data-ttu-id="641fb-112">の呼び出しで、2つのオブジェクト変数が予期せず<xref:System.Type.IsInstanceOfType%2A>に配置されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="641fb-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="641fb-113">想定される基本型は<xref:System.Type?displayProperty=nameWithType>クラスを生成するために使用され、想定される派生型は引数として<xref:System.Type.IsInstanceOfType%2A>メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="641fb-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="641fb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="641fb-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="641fb-115">Object 型</span><span class="sxs-lookup"><span data-stu-id="641fb-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="641fb-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="641fb-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="641fb-117">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="641fb-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="641fb-118">方法: 2つのオブジェクトが同一かどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="641fb-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
