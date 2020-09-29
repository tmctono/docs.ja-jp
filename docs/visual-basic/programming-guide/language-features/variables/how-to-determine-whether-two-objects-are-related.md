---
title: '方法: 2 つのオブジェクトが関連しているかどうかを決める'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: b33815d58b0ef40f7f75a6a41bb4b1eeef591859
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072224"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="aadfa-102">方法: 2 つのオブジェクトが関連しているかどうかを判別する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aadfa-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>

<span data-ttu-id="aadfa-103">2 つのオブジェクトを比較することで、それらの作成元であるクラス間のリレーションシップ (存在する場合) を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="aadfa-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="aadfa-104">指定したクラスが現在のクラスを継承している場合、または現在の型が、指定したクラスでサポートされているインターフェイスである場合、<xref:System.Type?displayProperty=nameWithType> クラスの <xref:System.Type.IsInstanceOfType%2A> メソッドから `True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="aadfa-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>

### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="aadfa-105">あるオブジェクトが別のオブジェクトのクラスまたはインターフェイスを継承しているかどうかを判別するには</span><span class="sxs-lookup"><span data-stu-id="aadfa-105">To determine if one object inherits from another object's class or interface</span></span>

1. <span data-ttu-id="aadfa-106">基本データ型と考えられるオブジェクトで、<xref:System.Object.GetType%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aadfa-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>

2. <span data-ttu-id="aadfa-107"><xref:System.Object.GetType%2A> から返された <xref:System.Type?displayProperty=nameWithType> オブジェクト上で、<xref:System.Type.IsInstanceOfType%2A> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="aadfa-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

3. <span data-ttu-id="aadfa-108"><xref:System.Type.IsInstanceOfType%2A> の引数リスト内で、派生型であると考えられるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="aadfa-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>

    <span data-ttu-id="aadfa-109">その引数の型がオブジェクトの型 <xref:System.Type?displayProperty=nameWithType> を継承している場合は、<xref:System.Type.IsInstanceOfType%2A> から `True` が返されます。</span><span class="sxs-lookup"><span data-stu-id="aadfa-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>

## <a name="example"></a><span data-ttu-id="aadfa-110">例</span><span class="sxs-lookup"><span data-stu-id="aadfa-110">Example</span></span>

 <span data-ttu-id="aadfa-111">次の例では、あるオブジェクトが、別のオブジェクトのクラスから派生したクラスを表しているかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="aadfa-111">The following example determines whether one object represents a class derived from another object's class.</span></span>

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

<span data-ttu-id="aadfa-112"><xref:System.Type.IsInstanceOfType%2A> への呼び出しで、2 つのオブジェクト変数が予期しない配置である点に注目してください。</span><span class="sxs-lookup"><span data-stu-id="aadfa-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="aadfa-113">想定される基本データ型を使用して <xref:System.Type?displayProperty=nameWithType> クラスを生成し、想定される派生型を引数として <xref:System.Type.IsInstanceOfType%2A> メソッドに渡します。</span><span class="sxs-lookup"><span data-stu-id="aadfa-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>

## <a name="see-also"></a><span data-ttu-id="aadfa-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="aadfa-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="aadfa-115">Object 型</span><span class="sxs-lookup"><span data-stu-id="aadfa-115">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="aadfa-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="aadfa-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="aadfa-117">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="aadfa-117">Object Variable Values</span></span>](object-variable-values.md)
- [<span data-ttu-id="aadfa-118">方法: 2 つのオブジェクトが同一であるかどうかを判別する</span><span class="sxs-lookup"><span data-stu-id="aadfa-118">How to: Determine Whether Two Objects Are Identical</span></span>](how-to-determine-whether-two-objects-are-identical.md)
