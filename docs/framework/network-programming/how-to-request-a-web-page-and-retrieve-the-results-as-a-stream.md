---
title: '方法: Web ページを要求し、ストリームとして結果を取得する'
description: この例では、.NET Framework で Web ページを要求し、ストリームで結果を取得する方法を示します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: bd57f9af6be29c783d044e785ebb36aaa8592df2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502484"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="5e044-103">方法: Web ページを要求し、ストリームとして結果を取得する</span><span class="sxs-lookup"><span data-stu-id="5e044-103">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="5e044-104">この例では、Web ページを要求し、ストリームとして結果を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e044-104">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="5e044-105">例</span><span class="sxs-lookup"><span data-stu-id="5e044-105">Example</span></span>

```csharp
var myClient = new WebClient();
Stream response = myClient.OpenRead("https://docs.microsoft.com/dotnet/");
// The stream data is used here.
response.Close();
```

```vb
Dim myClient As New WebClient()
Dim response As Stream = myClient.OpenRead("https://docs.microsoft.com/dotnet/")
' The stream data is used here.
response.Close()
```

## <a name="compiling-the-code"></a><span data-ttu-id="5e044-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="5e044-106">Compiling the Code</span></span>

 <span data-ttu-id="5e044-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5e044-107">This example requires:</span></span>

- <span data-ttu-id="5e044-108"><xref:System.IO> 名前空間と <xref:System.Net> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="5e044-108">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e044-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e044-109">See also</span></span>

- [<span data-ttu-id="5e044-110">データの要求</span><span class="sxs-lookup"><span data-stu-id="5e044-110">Requesting Data</span></span>](requesting-data.md)
