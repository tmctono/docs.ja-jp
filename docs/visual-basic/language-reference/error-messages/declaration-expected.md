---
title: 宣言が必要です。
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: 237622d0dc6c57f66d402f491a6191a5911574e2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409739"
---
# <a name="declaration-expected"></a><span data-ttu-id="a450d-102">宣言が必要です。</span><span class="sxs-lookup"><span data-stu-id="a450d-102">Declaration expected</span></span>
<span data-ttu-id="a450d-103">代入ステートメントやループ ステートメントなどの非宣言ステートメントが、プロシージャの外側に記述されています。</span><span class="sxs-lookup"><span data-stu-id="a450d-103">A nondeclarative statement, such as an assignment or loop statement, occurs outside any procedure.</span></span> <span data-ttu-id="a450d-104">プロシージャの外側で許可されるのは宣言のみです。</span><span class="sxs-lookup"><span data-stu-id="a450d-104">Only declarations are allowed outside procedures.</span></span>  
  
 <span data-ttu-id="a450d-105">または、プログラミング要素が、`Dim` や `Const` などの宣言キーワードを使用せずに宣言されています。</span><span class="sxs-lookup"><span data-stu-id="a450d-105">Alternatively, a programming element is declared without a declaration keyword such as `Dim` or `Const`.</span></span>  
  
 <span data-ttu-id="a450d-106">**エラー ID:** BC30188</span><span class="sxs-lookup"><span data-stu-id="a450d-106">**Error ID:** BC30188</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a450d-107">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="a450d-107">To correct this error</span></span>  
  
- <span data-ttu-id="a450d-108">非宣言ステートメントをプロシージャの本体に移動します。</span><span class="sxs-lookup"><span data-stu-id="a450d-108">Move the nondeclarative statement to the body of a procedure.</span></span>  
  
- <span data-ttu-id="a450d-109">適切な宣言キーワードを使用して、宣言を開始します。</span><span class="sxs-lookup"><span data-stu-id="a450d-109">Begin the declaration with an appropriate declaration keyword.</span></span>  
  
- <span data-ttu-id="a450d-110">宣言キーワードのスペルが間違っていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a450d-110">Ensure that a declaration keyword is not misspelled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a450d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="a450d-111">See also</span></span>

- [<span data-ttu-id="a450d-112">手順</span><span class="sxs-lookup"><span data-stu-id="a450d-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a450d-113">Dim ステートメント</span><span class="sxs-lookup"><span data-stu-id="a450d-113">Dim Statement</span></span>](../statements/dim-statement.md)
