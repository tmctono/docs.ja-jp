---
title: インデックス番号がインデックス付き配列の次元を超えています。
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 01659205f271b089fe4e8aa87cf7a8c44e7a4000
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918165"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="e0bde-102">インデックス番号がインデックス付き配列の次元を超えています。</span><span class="sxs-lookup"><span data-stu-id="e0bde-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="e0bde-103">配列要素にアクセスするために使用されるインデックスの数は、配列のランク、つまり配列に宣言した次元の数とまったく同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0bde-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="e0bde-104">**エラー ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="e0bde-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e0bde-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="e0bde-105">To correct this error</span></span>  
  
- <span data-ttu-id="e0bde-106">添字の合計数には、配列のランクと同じになるまでは、配列参照からの添字を削除します。</span><span class="sxs-lookup"><span data-stu-id="e0bde-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="e0bde-107">例:</span><span class="sxs-lookup"><span data-stu-id="e0bde-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e0bde-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0bde-108">See also</span></span>

- [<span data-ttu-id="e0bde-109">配列</span><span class="sxs-lookup"><span data-stu-id="e0bde-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
