---
title: "'AddressOf' オペランドはメソッドの名前でなければなりません。かっこは不要です。"
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323825"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="6d656-102">'AddressOf' オペランドはメソッドの名前でなければなりません。かっこは不要です。</span><span class="sxs-lookup"><span data-stu-id="6d656-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="6d656-103">`AddressOf` 演算子は、特定のプロシージャを参照するプロシージャ デリゲート インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="6d656-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="6d656-104">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d656-104">The syntax is as follows.</span></span>  
  
 `AddressOf` `procedurename`  
  
 <span data-ttu-id="6d656-105">かっこで囲んで引数以下を挿入した`AddressOf`none は必要に応じて、します。</span><span class="sxs-lookup"><span data-stu-id="6d656-105">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="6d656-106">**エラー ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="6d656-106">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d656-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="6d656-107">To correct this error</span></span>  
  
1. <span data-ttu-id="6d656-108">次の引数を囲むかっこを削除`AddressOf`します。</span><span class="sxs-lookup"><span data-stu-id="6d656-108">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="6d656-109">引数がメソッド名を確認します。</span><span class="sxs-lookup"><span data-stu-id="6d656-109">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d656-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d656-110">See also</span></span>

- [<span data-ttu-id="6d656-111">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="6d656-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="6d656-112">デリゲート</span><span class="sxs-lookup"><span data-stu-id="6d656-112">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
