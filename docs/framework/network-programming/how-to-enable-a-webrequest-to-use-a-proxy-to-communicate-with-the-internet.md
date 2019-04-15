---
title: '方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: a2179e767a0556f5223f2f4c1cc91708133120a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103702"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="cb336-102">方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="cb336-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="cb336-103">この例では、<xref:System.Net.WebRequest> でインターネットとの通信にプロキシを使用できるようにするグローバル プロキシ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb336-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="cb336-104">ここでは、プロキシ サーバーが `webproxy` という名前で、ポート 80 (標準 HTTP ポート) で通信を行うことを想定します。</span><span class="sxs-lookup"><span data-stu-id="cb336-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb336-105">例</span><span class="sxs-lookup"><span data-stu-id="cb336-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cb336-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="cb336-106">Compiling the Code</span></span>  
 <span data-ttu-id="cb336-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb336-107">This example requires:</span></span>  
  
-   <span data-ttu-id="cb336-108">**System.Net** 名前空間の [`using` ディレクティブ](../../csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="cb336-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb336-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb336-109">See also</span></span>

- [<span data-ttu-id="cb336-110">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="cb336-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="cb336-111">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="cb336-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
