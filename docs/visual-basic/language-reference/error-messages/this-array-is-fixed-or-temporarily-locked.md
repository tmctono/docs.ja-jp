---
title: この配列は固定か、または一時的にロックされています。
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 05fb8e2ef788920fd200d79a75eec3d7c252b123
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873583"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="8b017-102">この配列は固定か、または一時的にロックされています。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8b017-102">This array is fixed or temporarily locked (Visual Basic)</span></span>

<span data-ttu-id="8b017-103">このエラーには、次のような原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="8b017-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="8b017-104">`ReDim` を使用して、固定サイズの配列の要素数を変更している。</span><span class="sxs-lookup"><span data-stu-id="8b017-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="8b017-105">モジュールレベルの動的配列を再定義しており、その中の 1 つの要素がプロシージャへの引数として渡されている。</span><span class="sxs-lookup"><span data-stu-id="8b017-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="8b017-106">要素が渡されると、プロシージャ内の参照パラメーターのメモリの割り当て解除を防ぐために、配列がロックされます。</span><span class="sxs-lookup"><span data-stu-id="8b017-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="8b017-107">配列を格納する `Variant` 変数に値を代入しようとしたが、`Variant` が現在ロックされている。</span><span class="sxs-lookup"><span data-stu-id="8b017-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b017-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="8b017-108">To correct this error</span></span>  
  
1. <span data-ttu-id="8b017-109">`ReDim` で宣言する (配列がプロシージャ内で宣言されている場合) か、要素数を指定せずに宣言する (配列がモジュール レベルで宣言されている場合) ことによって、元の配列を固定ではなく動的にします。</span><span class="sxs-lookup"><span data-stu-id="8b017-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="8b017-110">モジュールのすべてのプロシージャ内で要素が表示されるようになるため、本当に要素を渡す必要があるかどうかを判断してください。</span><span class="sxs-lookup"><span data-stu-id="8b017-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="8b017-111">`Variant` をロックしているものを特定し、それを修復します。</span><span class="sxs-lookup"><span data-stu-id="8b017-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b017-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b017-112">See also</span></span>

- [<span data-ttu-id="8b017-113">配列</span><span class="sxs-lookup"><span data-stu-id="8b017-113">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
