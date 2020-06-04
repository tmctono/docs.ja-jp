---
title: "'ReDim' で次元数を変更することはできません"
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: b2404927c2faf30d1d058d2163fd5d67e1a52e1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358168"
---
# <a name="redim-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="b8038-102">'ReDim' で次元数を変更することはできません</span><span class="sxs-lookup"><span data-stu-id="b8038-102">'ReDim' cannot change the number of dimensions</span></span>
<span data-ttu-id="b8038-103">`ReDim` ステートメントを使用して、配列のランク (次元の数) を変更する操作が行われました。</span><span class="sxs-lookup"><span data-stu-id="b8038-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="b8038-104">`ReDim` は既に宣言された配列の 1 つ以上の次元のサイズを変更するために使用できますが、配列のランクを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="b8038-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b8038-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b8038-105">To correct this error</span></span>  
  
- <span data-ttu-id="b8038-106">次元のサイズではなく、配列のランクを変更しようとしていることを確認します。可能な場合は、 `Dim` を使用して、希望のランクを持つ配列を新規に宣言します。</span><span class="sxs-lookup"><span data-stu-id="b8038-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8038-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8038-107">See also</span></span>

- [<span data-ttu-id="b8038-108">Visual Basic における配列</span><span class="sxs-lookup"><span data-stu-id="b8038-108">Arrays in Visual Basic</span></span>](../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="b8038-109">Visual Basic 内の配列の次元</span><span class="sxs-lookup"><span data-stu-id="b8038-109">Array dimensions in Visual Basic</span></span>](../programming-guide/language-features/arrays/array-dimensions.md)
- [<span data-ttu-id="b8038-110">ReDim ステートメント</span><span class="sxs-lookup"><span data-stu-id="b8038-110">ReDim Statement</span></span>](../language-reference/statements/redim-statement.md)
- [<span data-ttu-id="b8038-111">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="b8038-111">Dim Statement</span></span>](../language-reference/statements/dim-statement.md)
