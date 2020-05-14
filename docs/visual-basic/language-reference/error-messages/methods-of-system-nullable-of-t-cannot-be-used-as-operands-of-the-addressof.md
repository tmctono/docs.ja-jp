---
title: "'System.Nullable(Of T)' のメソッドを 'AddressOf' 演算子のオペランドとして使用することはできません。"
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: e55e561fa20a3740d352537958681b0a66fc381e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592041"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a><span data-ttu-id="d3b0c-102">'System.Nullable(Of T)' のメソッドを 'AddressOf' 演算子のオペランドとして使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-102">Methods of 'System.Nullable(Of T)' cannot be used as operands of the 'AddressOf' operator</span></span>
<span data-ttu-id="d3b0c-103">ステートメントで、<xref:System.Nullable%601> 構造のプロシージャを表すオペランドで、`AddressOf` 演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-103">A statement uses the `AddressOf` operator with an operand that represents a procedure of the <xref:System.Nullable%601> structure.</span></span>  
  
 <span data-ttu-id="d3b0c-104">**エラー ID:** BC32126</span><span class="sxs-lookup"><span data-stu-id="d3b0c-104">**Error ID:** BC32126</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3b0c-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="d3b0c-105">To correct this error</span></span>  
  
- <span data-ttu-id="d3b0c-106">`AddressOf` 句のプロシージャ名を、<xref:System.Nullable%601> のメンバーではないオペランドに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-106">Replace the procedure name in the `AddressOf` clause with an operand that is not a member of <xref:System.Nullable%601>.</span></span>  
  
- <span data-ttu-id="d3b0c-107">使用する <xref:System.Nullable%601> のメソッドをラップするクラスを記述します。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-107">Write a class that wraps the method of <xref:System.Nullable%601> that you want to use.</span></span> <span data-ttu-id="d3b0c-108">次の例では、`NullableWrapper` クラスで `GetValueOrDefault` という名前の新しいメソッドを定義しています。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-108">In the following example, the `NullableWrapper` class defines a new method named `GetValueOrDefault`.</span></span> <span data-ttu-id="d3b0c-109">この新しいメソッドは <xref:System.Nullable%601> のメンバーではないため、null 許容型のインスタンスである `nullInstance` に適用して `AddressOf` の引数を形成できます。</span><span class="sxs-lookup"><span data-stu-id="d3b0c-109">Because this new method is not a member of <xref:System.Nullable%601>, it can be applied to `nullInstance`, an instance of a nullable type, to form an argument for `AddressOf`.</span></span>  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3b0c-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3b0c-110">See also</span></span>

- <xref:System.Nullable%601>
- [<span data-ttu-id="d3b0c-111">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="d3b0c-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="d3b0c-112">null 許容値型</span><span class="sxs-lookup"><span data-stu-id="d3b0c-112">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [<span data-ttu-id="d3b0c-113">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3b0c-113">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
