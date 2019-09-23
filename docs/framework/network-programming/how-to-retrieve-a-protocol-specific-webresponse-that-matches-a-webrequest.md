---
title: '方法: WebRequest に一致するプロトコル固有の WebResponse を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 0cb2d11306f52df767d8c053e8ab745696bb8e47
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048136"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="ae540-102">方法: WebRequest に一致するプロトコル固有の WebResponse を取得する</span><span class="sxs-lookup"><span data-stu-id="ae540-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="ae540-103">この例では、WebRequest に一致するプロトコル固有の WebResponse を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ae540-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae540-104">例</span><span class="sxs-lookup"><span data-stu-id="ae540-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ae540-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ae540-105">Compiling the Code</span></span>  
 <span data-ttu-id="ae540-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae540-106">This example requires:</span></span>  
  
- <span data-ttu-id="ae540-107">**System.Net** 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="ae540-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae540-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae540-108">See also</span></span>

- [<span data-ttu-id="ae540-109">データの要求</span><span class="sxs-lookup"><span data-stu-id="ae540-109">Requesting Data</span></span>](requesting-data.md)
