---
title: <type1>'<typename>"実装する必要があります"<methodname>'interface' の<interfacename>'
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304910"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="f4bb1-102">\<type1 >'\<typename >' を実装する必要があります '\<methodname >' のインターフェイス'\<interfacename >'</span><span class="sxs-lookup"><span data-stu-id="f4bb1-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="f4bb1-103">クラスまたは構造体がインターフェイスを実装するために要求しているインターフェイスによって定義されたプロシージャを実装していません。</span><span class="sxs-lookup"><span data-stu-id="f4bb1-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="f4bb1-104">インターフェイスのすべてのメンバーを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4bb1-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="f4bb1-105">**エラー ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="f4bb1-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4bb1-106">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="f4bb1-106">To correct this error</span></span>  
  
1. <span data-ttu-id="f4bb1-107">同じ名前と、インターフェイスで定義されたシグネチャを持つプロシージャを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f4bb1-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="f4bb1-108">必ず含めて、少なくとも`End Function`または`End Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f4bb1-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="f4bb1-109">追加、`Implements`句の末尾に、`Function`または`Sub`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="f4bb1-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="f4bb1-110">例えば:</span><span class="sxs-lookup"><span data-stu-id="f4bb1-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4bb1-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4bb1-111">See also</span></span>

- [<span data-ttu-id="f4bb1-112">Implements ステートメント</span><span class="sxs-lookup"><span data-stu-id="f4bb1-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="f4bb1-113">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f4bb1-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
