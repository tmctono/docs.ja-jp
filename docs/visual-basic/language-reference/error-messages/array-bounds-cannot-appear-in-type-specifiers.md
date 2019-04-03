---
title: 配列の上下限を、型指定子に記述できません。
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: f20ed883005641082eb89e2effa5221594910ffe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838782"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="f4301-102">配列の上下限を、型指定子に記述できません。</span><span class="sxs-lookup"><span data-stu-id="f4301-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="f4301-103">配列のサイズは、データ型の指定子の一部として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="f4301-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="f4301-104">**エラー ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="f4301-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4301-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f4301-105">To correct this error</span></span>  
  
-   <span data-ttu-id="f4301-106">次の例に示すように、型の後に、配列のサイズを配置することではなく変数名のすぐ後の配列のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="f4301-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="f4301-107">配列を定義し、次の例に示すように、必要な数の要素を初期化します。</span><span class="sxs-lookup"><span data-stu-id="f4301-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4301-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4301-108">See also</span></span>

- [<span data-ttu-id="f4301-109">配列</span><span class="sxs-lookup"><span data-stu-id="f4301-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
