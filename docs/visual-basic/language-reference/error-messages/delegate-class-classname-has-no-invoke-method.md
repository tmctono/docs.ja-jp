---
title: Delegate クラス '<classname>' には Invoke メソッドが含まれていないため、この型の式をメソッド呼び出しのターゲットに設定することはできません。
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: e6ad06262806088347c94b3040b743618a3b3695
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874504"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="450cf-102">Delegate クラス '\<classname>' には Invoke メソッドが含まれていないため、この型の式をメソッド呼び出しのターゲットに設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="450cf-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>

<span data-ttu-id="450cf-103">デリゲート クラスに `Invoke` が実装されていないため、デリゲートを使用して `Invoke` を呼び出すことができませんでした。</span><span class="sxs-lookup"><span data-stu-id="450cf-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="450cf-104">**エラー ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="450cf-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="450cf-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="450cf-105">To correct this error</span></span>  
  
1. <span data-ttu-id="450cf-106">デリゲート クラスのインスタンスが `Dim` ステートメントを使用して作成されていること、およびプロシージャが `AddressOf` 演算子を使用してデリゲート インスタンスに割り当てられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="450cf-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="450cf-107">デリゲート クラスを実装するコードを見つけ、それによって `Invoke` プロシージャが実装されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="450cf-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450cf-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="450cf-108">See also</span></span>

- [<span data-ttu-id="450cf-109">デリゲート</span><span class="sxs-lookup"><span data-stu-id="450cf-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="450cf-110">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="450cf-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="450cf-111">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="450cf-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="450cf-112">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="450cf-112">Dim Statement</span></span>](../statements/dim-statement.md)
