---
title: ループ コントロール変数として宣言された配列を初期サイズで宣言することはできません
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: bee3bcd3701945f5cf77f6761defc8be77acf49f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843579"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="15dac-102">ループ コントロール変数として宣言された配列を初期サイズで宣言することはできません</span><span class="sxs-lookup"><span data-stu-id="15dac-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="15dac-103">A`For Each`ループとして配列を使用してその*要素*繰り返し変数は、その配列を初期化します。</span><span class="sxs-lookup"><span data-stu-id="15dac-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="15dac-104">次のステートメントでは、このエラーの生成方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="15dac-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="15dac-105">最初の`For Each`ステートメントの要素にアクセスする正しい方法は、`arrayList`します。</span><span class="sxs-lookup"><span data-stu-id="15dac-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="15dac-106">2 番目の`For Each`ステートメントには、このエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="15dac-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="15dac-107">**エラー ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="15dac-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15dac-108">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="15dac-108">To correct this error</span></span>  
  
-   <span data-ttu-id="15dac-109">宣言から初期化を削除、*要素*繰り返し変数。</span><span class="sxs-lookup"><span data-stu-id="15dac-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15dac-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="15dac-110">See also</span></span>

- [<span data-ttu-id="15dac-111">For...Next ステートメント</span><span class="sxs-lookup"><span data-stu-id="15dac-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="15dac-112">配列</span><span class="sxs-lookup"><span data-stu-id="15dac-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="15dac-113">コレクション</span><span class="sxs-lookup"><span data-stu-id="15dac-113">Collections</span></span>](../../../standard/collections/index.md)
