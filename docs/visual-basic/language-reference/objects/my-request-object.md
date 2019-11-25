---
title: My.Request オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 22329bc501c9bb75b1336dd5384ab5b23a98ac21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350675"
---
# <a name="myrequest-object"></a><span data-ttu-id="d3713-102">My.Request オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d3713-102">My.Request Object</span></span>
<span data-ttu-id="d3713-103">要求されたページの <xref:System.Web.HttpRequest> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3713-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3713-104">Remarks</span><span class="sxs-lookup"><span data-stu-id="d3713-104">Remarks</span></span>  
 <span data-ttu-id="d3713-105">`My.Request` オブジェクトには、現在の HTTP 要求に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d3713-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="d3713-106">`My.Request` オブジェクトは、ASP.NET アプリケーションでのみ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d3713-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3713-107">例</span><span class="sxs-lookup"><span data-stu-id="d3713-107">Example</span></span>  
 <span data-ttu-id="d3713-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span><span class="sxs-lookup"><span data-stu-id="d3713-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d3713-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3713-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="d3713-110">My.Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d3713-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
