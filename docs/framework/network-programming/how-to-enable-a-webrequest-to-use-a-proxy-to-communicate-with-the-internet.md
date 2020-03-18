---
title: '方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039539"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="704b3-102">方法: WebRequest でインターネットとの通信にプロキシを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="704b3-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="704b3-103">この例では、<xref:System.Net.WebRequest> でインターネットとの通信にプロキシを使用できるようにするグローバル プロキシ インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="704b3-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="704b3-104">ここでは、プロキシ サーバーが `webproxy` という名前で、ポート 80 (標準 HTTP ポート) で通信を行うことを想定します。</span><span class="sxs-lookup"><span data-stu-id="704b3-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="704b3-105">例</span><span class="sxs-lookup"><span data-stu-id="704b3-105">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="704b3-106">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="704b3-106">Compiling the Code</span></span>

<span data-ttu-id="704b3-107">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="704b3-107">This example requires:</span></span>

- <span data-ttu-id="704b3-108">[System.Net`using` 名前空間の C# ](../../csharp/language-reference/keywords/using-directive.md)**ディレクティブ**。</span><span class="sxs-lookup"><span data-stu-id="704b3-108">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="704b3-109">[System.Net`Imports` 名前空間の Visual Basic ](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)**ステートメント**。</span><span class="sxs-lookup"><span data-stu-id="704b3-109">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="704b3-110">参照</span><span class="sxs-lookup"><span data-stu-id="704b3-110">See also</span></span>

- [<span data-ttu-id="704b3-111">アプリケーション プロトコルの使用</span><span class="sxs-lookup"><span data-stu-id="704b3-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="704b3-112">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="704b3-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
