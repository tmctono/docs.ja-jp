---
title: '方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする'
description: グローバル プロキシ インスタンスを作成し、任意の WebRequest がプロキシを使用して .NET Framework でインターネットと通信できるようにする方法について学習します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 0fc33cea3f5a7fe4669b110e53e71afdb9561c23
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502536"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="35583-103">方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="35583-103">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="35583-104">この例では、<xref:System.Net.WebRequest> でインターネットとの通信にプロキシを使用できるようにするグローバル プロキシ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="35583-104">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="35583-105">ここでは、プロキシ サーバーが `webproxy` という名前で、ポート 80 (標準 HTTP ポート) で通信を行うことを想定します。</span><span class="sxs-lookup"><span data-stu-id="35583-105">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="35583-106">例</span><span class="sxs-lookup"><span data-stu-id="35583-106">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="35583-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="35583-107">Compiling the Code</span></span>

<span data-ttu-id="35583-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35583-108">This example requires:</span></span>

- <span data-ttu-id="35583-109">**System.Net** 名前空間の C# [`using`ディレクティブ](../../csharp/language-reference/keywords/using-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="35583-109">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="35583-110">**System.Net** 名前空間の Visual Basic [`Imports`ステートメント](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。</span><span class="sxs-lookup"><span data-stu-id="35583-110">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="35583-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="35583-111">See also</span></span>

- [<span data-ttu-id="35583-112">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="35583-112">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="35583-113">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="35583-113">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
