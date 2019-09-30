---
title: '方法: Web ページを要求し、ストリームとして結果を取得する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d32b7f35-29d8-4fb7-ad71-d219edc5e359
ms.openlocfilehash: 65bda268cd77959dbcd786c365d0a30c324b89ce
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71393108"
---
# <a name="how-to-request-a-web-page-and-retrieve-the-results-as-a-stream"></a><span data-ttu-id="e1b80-102">方法: Web ページを要求し、ストリームとして結果を取得する</span><span class="sxs-lookup"><span data-stu-id="e1b80-102">How to: Request a Web Page and Retrieve the Results as a Stream</span></span>

<span data-ttu-id="e1b80-103">この例では、Web ページを要求し、ストリームとして結果を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1b80-103">This example shows how to request a Web page and retrieve the results in a stream.</span></span>
  
## <a name="example"></a><span data-ttu-id="e1b80-104">例</span><span class="sxs-lookup"><span data-stu-id="e1b80-104">Example</span></span>

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

## <a name="compiling-the-code"></a><span data-ttu-id="e1b80-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="e1b80-105">Compiling the Code</span></span>

 <span data-ttu-id="e1b80-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e1b80-106">This example requires:</span></span>

- <span data-ttu-id="e1b80-107"><xref:System.IO> 名前空間と <xref:System.Net> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="e1b80-107">References to the <xref:System.IO> and <xref:System.Net> namespaces.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1b80-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1b80-108">See also</span></span>

- [<span data-ttu-id="e1b80-109">データの要求</span><span class="sxs-lookup"><span data-stu-id="e1b80-109">Requesting Data</span></span>](requesting-data.md)
