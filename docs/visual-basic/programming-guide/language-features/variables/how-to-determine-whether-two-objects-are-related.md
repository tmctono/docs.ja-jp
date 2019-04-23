---
title: '方法: 2 つのオブジェクトが関連するかどうかを判断する (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], Visual Basic objects
- objects [Visual Basic], inheritance
- object variables [Visual Basic], determining relation
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
ms.openlocfilehash: f59e00d80d28fc4bf24874d25b5c12643649c834
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342103"
---
# <a name="how-to-determine-whether-two-objects-are-related-visual-basic"></a><span data-ttu-id="3baed-102">方法: 2 つのオブジェクトが関連するかどうかを判断する (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3baed-102">How to: Determine Whether Two Objects Are Related (Visual Basic)</span></span>
<span data-ttu-id="3baed-103">作成元のクラス間のリレーションシップを判別する 2 つのオブジェクトを比較することができます。</span><span class="sxs-lookup"><span data-stu-id="3baed-103">You can compare two objects to determine the relationship, if any, between the classes from which they are created.</span></span> <span data-ttu-id="3baed-104"><xref:System.Type.IsInstanceOfType%2A>のメソッド、<xref:System.Type?displayProperty=nameWithType>クラスを返します。`True`指定したクラスは、現在のクラスから継承する場合、または現在の型が指定したクラスでサポートされているインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="3baed-104">The <xref:System.Type.IsInstanceOfType%2A> method of the <xref:System.Type?displayProperty=nameWithType> class returns `True` if the specified class inherits from the current class, or if the current type is an interface supported by the specified class.</span></span>  
  
### <a name="to-determine-if-one-object-inherits-from-another-objects-class-or-interface"></a><span data-ttu-id="3baed-105">1 つのオブジェクトが別のオブジェクトのクラスまたはインターフェイスから継承かどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="3baed-105">To determine if one object inherits from another object's class or interface</span></span>  
  
1. <span data-ttu-id="3baed-106">思われるオブジェクトの可能性があります、基本型で、呼び出し、<xref:System.Object.GetType%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="3baed-106">On the object you think might be of the base type, invoke the <xref:System.Object.GetType%2A> method.</span></span>  
  
2. <span data-ttu-id="3baed-107"><xref:System.Type?displayProperty=nameWithType>によって返されるオブジェクト<xref:System.Object.GetType%2A>を呼び出し、<xref:System.Type.IsInstanceOfType%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="3baed-107">On the <xref:System.Type?displayProperty=nameWithType> object returned by <xref:System.Object.GetType%2A>, invoke the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
3. <span data-ttu-id="3baed-108">引数リストで<xref:System.Type.IsInstanceOfType%2A>、派生型のオブジェクトと思われる場合がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="3baed-108">In the argument list for <xref:System.Type.IsInstanceOfType%2A>, specify the object you think might be of the derived type.</span></span>  
  
     <span data-ttu-id="3baed-109"><xref:System.Type.IsInstanceOfType%2A> 返します`True`その引数の型から継承している場合、<xref:System.Type?displayProperty=nameWithType>オブジェクトの種類。</span><span class="sxs-lookup"><span data-stu-id="3baed-109"><xref:System.Type.IsInstanceOfType%2A> returns `True` if its argument type inherits from the <xref:System.Type?displayProperty=nameWithType> object type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3baed-110">例</span><span class="sxs-lookup"><span data-stu-id="3baed-110">Example</span></span>  
 <span data-ttu-id="3baed-111">次の例では、1 つのオブジェクトが別のオブジェクトのクラスから派生したクラスを表すかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3baed-111">The following example determines whether one object represents a class derived from another object's class.</span></span>  
  
```  
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
  
 <span data-ttu-id="3baed-112">予期しない呼び出しで 2 つのオブジェクト変数の配置に注意してください<xref:System.Type.IsInstanceOfType%2A>します。</span><span class="sxs-lookup"><span data-stu-id="3baed-112">Note the unexpected placement of the two object variables in the call to <xref:System.Type.IsInstanceOfType%2A>.</span></span> <span data-ttu-id="3baed-113">想定される基本データ型の生成に使用、<xref:System.Type?displayProperty=nameWithType>クラス、および想定される派生型が引数として渡される、<xref:System.Type.IsInstanceOfType%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="3baed-113">The supposed base type is used to generate the <xref:System.Type?displayProperty=nameWithType> class, and the supposed derived type is passed as an argument to the <xref:System.Type.IsInstanceOfType%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3baed-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3baed-114">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.IsInstanceOfType%2A>
- [<span data-ttu-id="3baed-115">Object 型</span><span class="sxs-lookup"><span data-stu-id="3baed-115">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="3baed-116">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="3baed-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3baed-117">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="3baed-117">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="3baed-118">方法: 2 つのオブジェクトが同一かどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3baed-118">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
