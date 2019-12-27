---
title: '方法 : 2 つのオブジェクトが関連しているかどうかを決める'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b3f5fc017166ba9cf28359db5de850c81b73bd69
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348630"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="cfbaa-102">方法: 2 つのオブジェクトが関連しているかどうかを判別する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfbaa-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="cfbaa-103">2つのオブジェクトを比較して、作成元のクラス間のリレーションシップ (存在する場合) を判断できます。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="cfbaa-104"><xref:System.Type?displayProperty=nameWithType> クラスの <xref:System.Type.IsInstanceOfType%2A> メソッドは、指定したクラスが現在のクラスから継承している場合、または現在の型が指定したクラスでサポートされているインターフェイスである場合に `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="cfbaa-105">あるオブジェクトが別のオブジェクトのクラスまたはインターフェイスから継承しているかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="cfbaa-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="cfbaa-106">基本型と考えられるオブジェクトで、<xref:System.Object.GetType%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="cfbaa-107"><xref:System.Object.GetType%2A>によって返される <xref:System.Type?displayProperty=nameWithType> オブジェクトで、<xref:System.Type.IsInstanceOfType%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="cfbaa-108"><xref:System.Type.IsInstanceOfType%2A>の引数リストで、派生型として考えられるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="cfbaa-109">引数の型が <xref:System.Type?displayProperty=nameWithType> オブジェクト型から継承されている場合、<xref:System.Type.IsInstanceOfType%2A> は `True` を返します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="cfbaa-110">例</span><span class="sxs-lookup"><span data-stu-id="cfbaa-110">Example</span></span>
 <span data-ttu-id="cfbaa-111">次の例では、あるオブジェクトが、別のオブジェクトのクラスから派生したクラスを表しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

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

<span data-ttu-id="cfbaa-112"><xref:System.Type.IsInstanceOfType%2A>の呼び出しで、2つのオブジェクト変数が予期せずに配置されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="cfbaa-113">想定される基本型を使用して <xref:System.Type?displayProperty=nameWithType> クラスを生成し、想定される派生型を引数として <xref:System.Type.IsInstanceOfType%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="cfbaa-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfbaa-114">参照</span><span class="sxs-lookup"><span data-stu-id="cfbaa-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="cfbaa-115">Object データ型</span><span class="sxs-lookup"><span data-stu-id="cfbaa-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="cfbaa-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="cfbaa-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="cfbaa-117">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="cfbaa-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="cfbaa-118">方法: 2 つのオブジェクトが同一であるかどうか判別する</span><span class="sxs-lookup"><span data-stu-id="cfbaa-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
