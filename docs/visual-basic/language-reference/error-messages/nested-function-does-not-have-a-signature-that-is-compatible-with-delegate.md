---
title: 入れ子になった関数に、デリゲート '<delegatename>' と互換性のあるシグネチャがありません。
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580643"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="4b229-102">入れ子になった関数に、デリゲート ' \<delegatename > ' と互換性のあるシグネチャがありません</span><span class="sxs-lookup"><span data-stu-id="4b229-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="4b229-103">互換性のないシグネチャを持つデリゲートにラムダ式が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4b229-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="4b229-104">たとえば、次のコードでは、delegate `Del` に2つの整数パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="4b229-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="4b229-105">1つの引数を持つラムダ式が `Del` 型として宣言されている場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="4b229-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="4b229-106">**エラー ID:** BC36532</span><span class="sxs-lookup"><span data-stu-id="4b229-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4b229-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="4b229-107">To correct this error</span></span>

<span data-ttu-id="4b229-108">デリゲート定義または割り当てられたラムダ式を調整して、シグネチャに互換性を持たせるようにします。</span><span class="sxs-lookup"><span data-stu-id="4b229-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b229-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b229-109">See also</span></span>

- [<span data-ttu-id="4b229-110">厳密でないデリゲート変換</span><span class="sxs-lookup"><span data-stu-id="4b229-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="4b229-111">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="4b229-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
