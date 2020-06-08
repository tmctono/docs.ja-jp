---
title: ラムダ式は、'Select Case' ステートメントの最初の式では有効ではありません
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 08f7cd9dd95a10cad0df6539ba43122495347bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397364"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="8433b-102">ラムダ式は、'Select Case' ステートメントの最初の式では有効ではありません</span><span class="sxs-lookup"><span data-stu-id="8433b-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>
<span data-ttu-id="8433b-103">ラムダ式は、`Select Case` ステートメントのテスト式に使用できません。</span><span class="sxs-lookup"><span data-stu-id="8433b-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="8433b-104">ラムダ式の定義では関数を返しますが、`Select Case` ステートメントのテスト式は基本データ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8433b-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="8433b-105">次のコードではこのエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8433b-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="8433b-106">**エラー ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="8433b-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8433b-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8433b-107">To correct this error</span></span>  
  
- <span data-ttu-id="8433b-108">コードを調べて、 `If...Then...Else` ステートメントなどの別の条件構造を使用できないかをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="8433b-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="8433b-109">次のコードに示すように、関数を呼び出そうとした可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8433b-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="8433b-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="8433b-110">See also</span></span>

- [<span data-ttu-id="8433b-111">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="8433b-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="8433b-112">If...Then...Else ステートメント</span><span class="sxs-lookup"><span data-stu-id="8433b-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="8433b-113">Select...Case ステートメント</span><span class="sxs-lookup"><span data-stu-id="8433b-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
