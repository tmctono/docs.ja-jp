---
title: 正しくないパターン文字列
ms.date: 07/20/2015
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
ms.openlocfilehash: 7390b9b32eea248969813b52f8d9799798718de0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298683"
---
# <a name="invalid-pattern-string"></a><span data-ttu-id="899d1-102">正しくないパターン文字列</span><span class="sxs-lookup"><span data-stu-id="899d1-102">Invalid pattern string</span></span>
<span data-ttu-id="899d1-103">検索の `Like` 演算で指定されているパターン文字列が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="899d1-103">The pattern string specified in the `Like` operation of a search is invalid.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="899d1-104">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="899d1-104">To correct this error</span></span>  
  
1. <span data-ttu-id="899d1-105">リスト式に使用できる文字を確認します。</span><span class="sxs-lookup"><span data-stu-id="899d1-105">Review the valid characters for list expressions.</span></span>  
  
2. <span data-ttu-id="899d1-106">パターン範囲の指定で、 `[a-z]`のように、範囲の開始文字が終了文字より小さいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="899d1-106">In the pattern range, ensure that the start range character is less than the end range character, as in `[a-z]`.</span></span>  
  
3. <span data-ttu-id="899d1-107">パターン範囲の指定で、 `[a--z]`のように、複数のハイフンが続けて指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="899d1-107">In the pattern range, ensure that there are not multiple hyphens next to each other, as in `[a--z]`.</span></span>  
  
4. <span data-ttu-id="899d1-108">パターン範囲を右角かっこで終了します。</span><span class="sxs-lookup"><span data-stu-id="899d1-108">End pattern ranges with a closing bracket.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899d1-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="899d1-109">See also</span></span>

- [<span data-ttu-id="899d1-110">Like 演算子</span><span class="sxs-lookup"><span data-stu-id="899d1-110">Like Operator</span></span>](../../visual-basic/language-reference/operators/like-operator.md)
