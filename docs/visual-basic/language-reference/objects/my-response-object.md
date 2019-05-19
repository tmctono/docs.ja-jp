---
title: My.Response オブジェクト (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0e49a3b5732ee1a3626666ce06e366c4940eca05
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881962"
---
# <a name="myresponse-object"></a><span data-ttu-id="1c067-102">My.Response オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1c067-102">My.Response Object</span></span>
<span data-ttu-id="1c067-103">取得、<xref:System.Web.HttpResponse>オブジェクトに関連付けられている、<xref:System.Web.UI.Page>します。</span><span class="sxs-lookup"><span data-stu-id="1c067-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="1c067-104">このオブジェクトでは、HTTP 応答データをクライアントに送信し、その応答に関する情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1c067-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c067-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c067-105">Remarks</span></span>  
 <span data-ttu-id="1c067-106">`My.Response`オブジェクトには、現在が含まれています。<xref:System.Web.HttpResponse>ページに関連付けられているオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c067-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="1c067-107">`My.Response`オブジェクトは、ASP.NET アプリケーションの使用のみ。</span><span class="sxs-lookup"><span data-stu-id="1c067-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c067-108">例</span><span class="sxs-lookup"><span data-stu-id="1c067-108">Example</span></span>  
 <span data-ttu-id="1c067-109">次の例からヘッダーのコレクションを取得、`My.Request`オブジェクトと使用、 `My.Response` ASP.NET ページに書き込むオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1c067-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1c067-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c067-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="1c067-111">My.Request オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1c067-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
