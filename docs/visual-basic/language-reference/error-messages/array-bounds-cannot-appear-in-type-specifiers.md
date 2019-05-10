---
title: 配列の上下限を、型指定子に記述できません。
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 50e1cd0e41da467a9e816c8e5d64d09a36923d65
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665748"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="3ef61-102">配列の上下限を、型指定子に記述できません。</span><span class="sxs-lookup"><span data-stu-id="3ef61-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="3ef61-103">配列のサイズは、データ型の指定子の一部として宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ef61-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="3ef61-104">**エラー ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="3ef61-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3ef61-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="3ef61-105">To correct this error</span></span>  
  
- <span data-ttu-id="3ef61-106">次の例に示すように、型の後に、配列のサイズを配置することではなく変数名のすぐ後の配列のサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="3ef61-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
- <span data-ttu-id="3ef61-107">配列を定義し、次の例に示すように、必要な数の要素を初期化します。</span><span class="sxs-lookup"><span data-stu-id="3ef61-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ef61-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ef61-108">See also</span></span>

- [<span data-ttu-id="3ef61-109">配列</span><span class="sxs-lookup"><span data-stu-id="3ef61-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
