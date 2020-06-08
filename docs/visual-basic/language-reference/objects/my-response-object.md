---
title: My.Response オブジェクト
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 962108264563c5e0b2894c5c856a5f23a3c1a8b4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372462"
---
# <a name="myresponse-object"></a><span data-ttu-id="e4333-102">My.Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e4333-102">My.Response Object</span></span>
<span data-ttu-id="e4333-103"><xref:System.Web.UI.Page> に関連付けられた <xref:System.Web.HttpResponse> オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e4333-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="e4333-104">このオブジェクトでは、HTTP 応答データをクライアントに送信し、その応答に関する情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e4333-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4333-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="e4333-105">Remarks</span></span>  
 <span data-ttu-id="e4333-106">`My.Response` オブジェクトには、ページに関連付けられている現在の <xref:System.Web.HttpResponse> オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4333-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="e4333-107">`My.Response` オブジェクトは、ASP.NET アプリケーションでのみ使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4333-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4333-108">例</span><span class="sxs-lookup"><span data-stu-id="e4333-108">Example</span></span>  
 <span data-ttu-id="e4333-109">次の例では、`My.Request` オブジェクトからヘッダー コレクションを取得し、`My.Response` オブジェクトを使用して ASP.NET ページに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e4333-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e4333-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4333-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="e4333-111">My.Request オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e4333-111">My.Request Object</span></span>](my-request-object.md)
