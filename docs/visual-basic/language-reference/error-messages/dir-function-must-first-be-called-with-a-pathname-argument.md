---
title: "'Dir' 関数は、'Pathname' 引数で最初に呼び出されなければなりません。"
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 1064a44f7c266b9dcce05dfddedef6bb1e919999
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874454"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="45ea0-102">'Dir' 関数は、'Pathname' 引数で最初に呼び出されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="45ea0-102">'Dir' function must first be called with a 'PathName' argument</span></span>

<span data-ttu-id="45ea0-103">`Dir` 関数の最初の呼び出しには、`PathName` 引数は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="45ea0-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="45ea0-104">`Dir` の最初の呼び出しには `PathName` を含める必要がありますが、後続の `Dir` の呼び出しには、次の項目を取得するためのパラメーターを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="45ea0-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45ea0-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="45ea0-105">To correct this error</span></span>  
  
1. <span data-ttu-id="45ea0-106">関数呼び出しに `PathName` 引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="45ea0-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ea0-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="45ea0-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
