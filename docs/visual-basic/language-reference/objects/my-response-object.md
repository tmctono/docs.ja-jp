---
title: My.settings オブジェクト (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567454"
---
# <a name="myresponse-object"></a><span data-ttu-id="c03be-102">My.Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c03be-102">My.Response Object</span></span>
<span data-ttu-id="c03be-103">に関連付けられた<xref:System.Web.HttpResponse>オブジェクトを取得します。 <xref:System.Web.UI.Page></span><span class="sxs-lookup"><span data-stu-id="c03be-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="c03be-104">このオブジェクトでは、HTTP 応答データをクライアントに送信し、その応答に関する情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c03be-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c03be-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c03be-105">Remarks</span></span>  
 <span data-ttu-id="c03be-106">オブジェクト`My.Response`には、ページ<xref:System.Web.HttpResponse>に関連付けられている現在のオブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c03be-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="c03be-107">オブジェクト`My.Response`は、ASP.NET アプリケーションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c03be-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c03be-108">例</span><span class="sxs-lookup"><span data-stu-id="c03be-108">Example</span></span>  
 <span data-ttu-id="c03be-109">次の例では、 `My.Request`オブジェクトからヘッダーコレクションを取得し、 `My.Response`オブジェクトを使用して ASP.NET ページに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="c03be-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c03be-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="c03be-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="c03be-111">My.Request オブジェクト</span><span class="sxs-lookup"><span data-stu-id="c03be-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
