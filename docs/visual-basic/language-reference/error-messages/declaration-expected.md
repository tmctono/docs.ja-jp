---
title: 宣言が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: e6f8bf2b4ce9789a1715971b8262bdd162ba8035
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619530"
---
# <a name="declaration-expected"></a><span data-ttu-id="38c6a-102">宣言が必要です。</span><span class="sxs-lookup"><span data-stu-id="38c6a-102">Declaration expected</span></span>
<span data-ttu-id="38c6a-103">代入ステートメントやループ ステートメントなどの非宣言ステートメントが、プロシージャの外側に記述されています。</span><span class="sxs-lookup"><span data-stu-id="38c6a-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="38c6a-104">プロシージャの外側で許可されるのは宣言のみです。</span><span class="sxs-lookup"><span data-stu-id="38c6a-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="38c6a-105">または、プログラミング要素が、`Dim` や `Const` などの宣言キーワードを使用せずに宣言されています。</span><span class="sxs-lookup"><span data-stu-id="38c6a-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="38c6a-106">**エラー ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="38c6a-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="38c6a-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="38c6a-107">To correct this error</span></span>  
  
- <span data-ttu-id="38c6a-108">非宣言ステートメントをプロシージャの本体に移動します。</span><span class="sxs-lookup"><span data-stu-id="38c6a-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="38c6a-109">適切な宣言キーワードを使用して、宣言を開始します。</span><span class="sxs-lookup"><span data-stu-id="38c6a-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="38c6a-110">宣言キーワードのスペルが間違っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="38c6a-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c6a-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="38c6a-111">See also</span></span>

- [<span data-ttu-id="38c6a-112">手順</span><span class="sxs-lookup"><span data-stu-id="38c6a-112">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="38c6a-113">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="38c6a-113">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
