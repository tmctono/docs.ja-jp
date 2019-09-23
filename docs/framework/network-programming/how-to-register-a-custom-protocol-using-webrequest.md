---
title: '方法: WebRequest を使用してカスタム プロトコルを登録する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 05b6f6c3f0f1fc1b36b60e8b0dae50de2826aba4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048253"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="24001-102">方法: WebRequest を使用してカスタム プロトコルを登録する</span><span class="sxs-lookup"><span data-stu-id="24001-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="24001-103">この例では、他の場所で定義されているプロトコル固有のクラスを登録する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="24001-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="24001-104">この例では、`CustomWebRequestCreator` は、`CustomWebRequest` オブジェクトを返す **Create** メソッドを実装するユーザー実装のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="24001-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="24001-105">このコード例では、カスタム プロトコルを実装する `CustomWebRequest` コードが既に作成されているものとします。</span><span class="sxs-lookup"><span data-stu-id="24001-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24001-106">例</span><span class="sxs-lookup"><span data-stu-id="24001-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24001-107">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="24001-107">Compiling the Code</span></span>  
 <span data-ttu-id="24001-108">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="24001-108">This example requires:</span></span>  
  
 <span data-ttu-id="24001-109"><xref:System.Net> 名前空間への参照。</span><span class="sxs-lookup"><span data-stu-id="24001-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24001-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="24001-110">See also</span></span>

- [<span data-ttu-id="24001-111">プラグ可能なプロトコルのプログラミング</span><span class="sxs-lookup"><span data-stu-id="24001-111">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
