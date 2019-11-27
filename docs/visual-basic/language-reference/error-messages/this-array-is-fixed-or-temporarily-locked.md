---
title: この配列は固定か、または一時的にロックされています。
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350782"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="612d0-102">この配列は固定か、または一時的にロックされています。(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="612d0-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="612d0-103">このエラーには、次のような原因が考えられます。</span><span class="sxs-lookup"><span data-stu-id="612d0-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="612d0-104">`ReDim` を使用して、固定サイズの配列の要素数を変更します。</span><span class="sxs-lookup"><span data-stu-id="612d0-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="612d0-105">モジュールレベルの動的配列を再配置します。この配列では、1つの要素がプロシージャに引数として渡されています。</span><span class="sxs-lookup"><span data-stu-id="612d0-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="612d0-106">要素が渡された場合、配列は、プロシージャ内の参照パラメーターのメモリの解放を防ぐためにロックされます。</span><span class="sxs-lookup"><span data-stu-id="612d0-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="612d0-107">配列を含む `Variant` 変数に値を割り当てようとしましたが、`Variant` は現在ロックされています。</span><span class="sxs-lookup"><span data-stu-id="612d0-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="612d0-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="612d0-108">To correct this error</span></span>  
  
1. <span data-ttu-id="612d0-109">`ReDim` (配列がプロシージャ内で宣言されている場合) で宣言するか、要素の数を指定せずに宣言することによって、元の配列を固定ではなく動的にします (配列がモジュールレベルで宣言されている場合)。</span><span class="sxs-lookup"><span data-stu-id="612d0-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="612d0-110">要素を渡す必要があるかどうかを判断します。これは、モジュール内のすべてのプロシージャ内に表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="612d0-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="612d0-111">`Variant` をロックしているものを特定し、それを修復します。</span><span class="sxs-lookup"><span data-stu-id="612d0-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612d0-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="612d0-112">See also</span></span>

- [<span data-ttu-id="612d0-113">配列</span><span class="sxs-lookup"><span data-stu-id="612d0-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
