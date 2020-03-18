---
title: '方法: グローバル プロキシの選択をオーバーライドする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048269"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="3682f-102">方法: グローバル プロキシの選択をオーバーライドする</span><span class="sxs-lookup"><span data-stu-id="3682f-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="3682f-103">この例では、**に**WebRequest`www.contoso.com` を送信し、ポート 80 の `alternateproxy` という名前のプロキシ サーバーでグローバル プロキシの選択をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3682f-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3682f-104">例</span><span class="sxs-lookup"><span data-stu-id="3682f-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3682f-105">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="3682f-105">Compiling the Code</span></span>  
 <span data-ttu-id="3682f-106">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3682f-106">This example requires:</span></span>  
  
- <span data-ttu-id="3682f-107">[System.Net`using` 名前空間の ](../../csharp/language-reference/keywords/using-directive.md) **ディレクティブ**。</span><span class="sxs-lookup"><span data-stu-id="3682f-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3682f-108">参照</span><span class="sxs-lookup"><span data-stu-id="3682f-108">See also</span></span>

- [<span data-ttu-id="3682f-109">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="3682f-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="3682f-110">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="3682f-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
