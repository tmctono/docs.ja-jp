---
title: "'Dir' 関数は、'Pathname' 引数で最初に呼び出されなければなりません。"
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: d255b8dddd098835764f72b8a166eaa08b0353df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59767891"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a><span data-ttu-id="b3339-102">'Dir' 関数は、'Pathname' 引数で最初に呼び出されなければなりません。</span><span class="sxs-lookup"><span data-stu-id="b3339-102">'Dir' function must first be called with a 'PathName' argument</span></span>
<span data-ttu-id="b3339-103">最初に呼び出すとき、`Dir`関数には含まれません、`PathName`引数。</span><span class="sxs-lookup"><span data-stu-id="b3339-103">An initial call to the `Dir` function does not include the `PathName` argument.</span></span> <span data-ttu-id="b3339-104">最初の呼び出し`Dir`含める必要があります、`PathName`が後続の呼び出し`Dir`次の項目を取得するパラメーターを含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b3339-104">The first call to `Dir` must include a `PathName`, but subsequent calls to `Dir` do not need to include parameters to retrieve the next item.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b3339-105">このエラーを解決するには</span><span class="sxs-lookup"><span data-stu-id="b3339-105">To correct this error</span></span>  
  
1. <span data-ttu-id="b3339-106">指定、`PathName`関数呼び出しの引数。</span><span class="sxs-lookup"><span data-stu-id="b3339-106">Supply a `PathName` argument in the function call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3339-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3339-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
