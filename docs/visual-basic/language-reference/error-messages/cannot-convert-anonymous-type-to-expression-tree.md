---
title: 型のプロパティは別のプロパティを初期化するために使用されるため、匿名型を式のツリーに変換することはできません。
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: 045061f403b301d460bc85d161c1d6dee9c7d9f1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602399"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a><span data-ttu-id="6ddb6-102">型のプロパティは別のプロパティを初期化するために使用されるため、匿名型を式のツリーに変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ddb6-102">Cannot convert anonymous type to expression tree because it contains a field that is used in the initialization of another field</span></span>
<span data-ttu-id="6ddb6-103">コンパイラでは、匿名型の別のプロパティを初期化するために、匿名型の 1 つのプロパティを使用する場合、匿名の式ツリーへの変換は受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="6ddb6-103">The compiler does not accept conversion of an anonymous to an expression tree when one property of the anonymous type is used to initialize another property of the anonymous type.</span></span> <span data-ttu-id="6ddb6-104">たとえば、次のコードで`Prop1`が初期化リストで宣言されの初期値として使用し、`Prop2`します。</span><span class="sxs-lookup"><span data-stu-id="6ddb6-104">For example, in the following code, `Prop1` is declared in the initialization list and then used as the initial value for `Prop2`.</span></span>  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="6ddb6-105">**エラー ID:** BC36548</span><span class="sxs-lookup"><span data-stu-id="6ddb6-105">**Error ID:** BC36548</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6ddb6-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6ddb6-106">To correct this error</span></span>  
  
- <span data-ttu-id="6ddb6-107">初期値を割り当てる`Prop1`ローカル変数にします。</span><span class="sxs-lookup"><span data-stu-id="6ddb6-107">Assign the initial value for `Prop1` to a local variable.</span></span> <span data-ttu-id="6ddb6-108">両方にその変数を割り当てる`Prop1`と`Prop2`、次のコードに示すようにします。</span><span class="sxs-lookup"><span data-stu-id="6ddb6-108">Assign that variable to both `Prop1` and `Prop2`, as shown in the following code.</span></span>  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6ddb6-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ddb6-109">See also</span></span>

- [<span data-ttu-id="6ddb6-110">匿名型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ddb6-110">Anonymous Types (Visual Basic)</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="6ddb6-111">式ツリー (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ddb6-111">Expression Trees (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/index.md)
- [<span data-ttu-id="6ddb6-112">方法: 式ツリーを使用して動的クエリ (Visual Basic) を作成するには</span><span class="sxs-lookup"><span data-stu-id="6ddb6-112">How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)</span></span>](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
