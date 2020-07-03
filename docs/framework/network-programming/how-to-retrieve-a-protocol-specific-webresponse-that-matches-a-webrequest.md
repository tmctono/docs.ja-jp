---
title: '方法: WebRequest に一致するプロトコル固有の WebResponse を取得する'
description: .NET Framework で WebRequest に一致するプロトコル固有の WebResponse を取得する方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 15b1912a7bd951df7f3c14eb96251c2bdf237b4f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502458"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="74f1f-103">方法: WebRequest に一致するプロトコル固有の WebResponse を取得する</span><span class="sxs-lookup"><span data-stu-id="74f1f-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="74f1f-104">この例では、WebRequest に一致するプロトコル固有の WebResponse を取得する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="74f1f-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74f1f-105">例</span><span class="sxs-lookup"><span data-stu-id="74f1f-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74f1f-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="74f1f-106">Compiling the Code</span></span>  
 <span data-ttu-id="74f1f-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="74f1f-107">This example requires:</span></span>  
  
- <span data-ttu-id="74f1f-108">**System.Net** 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="74f1f-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f1f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="74f1f-109">See also</span></span>

- [<span data-ttu-id="74f1f-110">データの要求</span><span class="sxs-lookup"><span data-stu-id="74f1f-110">Requesting Data</span></span>](requesting-data.md)
