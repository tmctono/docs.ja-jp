---
title: インデックス番号がインデックス付き配列の次元を超えています。
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: 4d8ffd2c4ad0a386053ced0f98503969723c7168
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409375"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="afc74-102">インデックス番号がインデックス付き配列の次元を超えています。</span><span class="sxs-lookup"><span data-stu-id="afc74-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="afc74-103">配列要素にアクセスするために使用されるインデックスの数は、配列のランク、つまり配列に宣言した次元の数とまったく同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="afc74-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="afc74-104">**エラー ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="afc74-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="afc74-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="afc74-105">To correct this error</span></span>  
  
- <span data-ttu-id="afc74-106">添字の合計数が配列のランクと同じになるまで、配列参照から添字を削除します。</span><span class="sxs-lookup"><span data-stu-id="afc74-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="afc74-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="afc74-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="afc74-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="afc74-108">See also</span></span>

- [<span data-ttu-id="afc74-109">配列</span><span class="sxs-lookup"><span data-stu-id="afc74-109">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
