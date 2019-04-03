---
title: Delegate クラス '<classname>' には Invoke メソッドが含まれていないため、この型の式をメソッド呼び出しのターゲットに設定することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 463b4f50e8c431bbbc113509e5fd9dd1756b5928
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822519"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="003c7-102">Delegate クラス\<classname >' この型の式はメソッド呼び出しのターゲットにすることはできませんので Invoke メソッドがありません</span><span class="sxs-lookup"><span data-stu-id="003c7-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="003c7-103">呼び出し`Invoke`デリゲートを通じてが失敗したため、`Invoke`デリゲート クラスは実装されていません。</span><span class="sxs-lookup"><span data-stu-id="003c7-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="003c7-104">**エラー ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="003c7-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="003c7-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="003c7-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="003c7-106">デリゲート クラスのインスタンスが作成されたことを確認、`Dim`ステートメントと、プロシージャがデリゲートのインスタンスに割り当てられたこと、`AddressOf`演算子。</span><span class="sxs-lookup"><span data-stu-id="003c7-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2.  <span data-ttu-id="003c7-107">デリゲート クラスを実装するコードを見つけて、それを実装することを確認、`Invoke`プロシージャ。</span><span class="sxs-lookup"><span data-stu-id="003c7-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003c7-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="003c7-108">See also</span></span>

- [<span data-ttu-id="003c7-109">デリゲート</span><span class="sxs-lookup"><span data-stu-id="003c7-109">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="003c7-110">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="003c7-110">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="003c7-111">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="003c7-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="003c7-112">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="003c7-112">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
