---
title: '方法: WebRequest を使用してカスタム プロトコルを登録する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 05b6f6c3f0f1fc1b36b60e8b0dae50de2826aba4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048253"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="b1379-102">方法: WebRequest を使用してカスタム プロトコルを登録する</span><span class="sxs-lookup"><span data-stu-id="b1379-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="b1379-103">この例では、他の場所で定義されているプロトコル固有のクラスを登録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b1379-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="b1379-104">この例では、`CustomWebRequestCreator` は、**オブジェクトを返す**Create`CustomWebRequest` メソッドを実装するユーザー実装のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="b1379-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="b1379-105">このコード例では、カスタム プロトコルを実装する `CustomWebRequest` コードが既に作成されているものとします。</span><span class="sxs-lookup"><span data-stu-id="b1379-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1379-106">例</span><span class="sxs-lookup"><span data-stu-id="b1379-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b1379-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="b1379-107">Compiling the Code</span></span>  
 <span data-ttu-id="b1379-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b1379-108">This example requires:</span></span>  
  
 <span data-ttu-id="b1379-109"><xref:System.Net> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="b1379-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1379-110">参照</span><span class="sxs-lookup"><span data-stu-id="b1379-110">See also</span></span>

- [<span data-ttu-id="b1379-111">プラグ可能なプロトコルのプログラミング</span><span class="sxs-lookup"><span data-stu-id="b1379-111">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
