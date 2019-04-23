---
title: レコード番号が正しくありません
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340803"
---
# <a name="bad-record-number"></a><span data-ttu-id="e0ad2-102">レコード番号が正しくありません</span><span class="sxs-lookup"><span data-stu-id="e0ad2-102">Bad record number</span></span>
<span data-ttu-id="e0ad2-103">`a FileGet`、 `FilePut`、 `FileGetObject`、または `FilePutObject` ステートメント内のレコード番号が 0 以下です。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e0ad2-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e0ad2-104">To correct this error</span></span>  
  
1. <span data-ttu-id="e0ad2-105">レコード番号の生成で使用される計算を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="e0ad2-106">レコード番号が含まれている変数、またはレコード番号の計算で使用される変数のスペルを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="e0ad2-107">モジュールで `Option Explicit On` を使用しない限り、スペル ミスの変数名は暗黙的に宣言され、0 に初期化されます。</span><span class="sxs-lookup"><span data-stu-id="e0ad2-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ad2-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ad2-108">See also</span></span>

- [<span data-ttu-id="e0ad2-109">Option Explicit ステートメント</span><span class="sxs-lookup"><span data-stu-id="e0ad2-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
