---
title: '方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 99bbff5a3350f55f04fdbd6ce7147b6597773322
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624586"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="d946c-102">方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="d946c-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="d946c-103">この例では、<xref:System.Net.WebRequest> でインターネットとの通信にプロキシを使用できるようにするグローバル プロキシ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="d946c-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="d946c-104">ここでは、プロキシ サーバーが `webproxy` という名前で、ポート 80 (標準 HTTP ポート) で通信を行うことを想定します。</span><span class="sxs-lookup"><span data-stu-id="d946c-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d946c-105">例</span><span class="sxs-lookup"><span data-stu-id="d946c-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d946c-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="d946c-106">Compiling the Code</span></span>  
 <span data-ttu-id="d946c-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d946c-107">This example requires:</span></span>  
  
- <span data-ttu-id="d946c-108">**System.Net** 名前空間の [`using` ディレクティブ](../../csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="d946c-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d946c-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d946c-109">See also</span></span>

- [<span data-ttu-id="d946c-110">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="d946c-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="d946c-111">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d946c-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
