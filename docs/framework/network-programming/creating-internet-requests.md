---
title: インターネット要求の作成
description: 渡された URI スキームに基づいて派生クラスを作成する WebRequest.Create メソッドを利用することでアプリケーションで WebRequest インスタンスが作成されるしくみについて説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325630"
---
# <a name="create-internet-requests"></a><span data-ttu-id="59f8c-103">インターネット要求の作成</span><span class="sxs-lookup"><span data-stu-id="59f8c-103">Create internet requests</span></span>

<span data-ttu-id="59f8c-104">アプリケーションは、<xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> メソッドを使用して <xref:System.Net.WebRequest> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="59f8c-104">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="59f8c-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> は、渡された URI スキームに基づいて <xref:System.Net.WebRequest> から派生するクラスを作成する静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="59f8c-105"><xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> is a static method that creates a class derived from <xref:System.Net.WebRequest> based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="59f8c-106">Web、ファイル、FTP 要求</span><span class="sxs-lookup"><span data-stu-id="59f8c-106">Web, file, and FTP requests</span></span>

<span data-ttu-id="59f8c-107">.NET Framework は、`WebRequest` から派生する <xref:System.Net.HttpWebRequest> クラスを提供することにより、HTTP および HTTPS 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="59f8c-107">.NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from `WebRequest`, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="59f8c-108">ほとんどの場合、`WebRequest` クラスは要求を行うのに必要なすべてのプロパティを提供しますが、必要に応じて、`WebRequest.Create` メソッドで作成した `WebRequest` オブジェクトを `HttpWebRequest` 型にキャストすることにより、その要求の HTTP 固有のプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="59f8c-108">In most cases, the `WebRequest` class provides all the properties you need to make a request; however, if necessary, you can cast `WebRequest` objects created by the `WebRequest.Create` method to the `HttpWebRequest` type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="59f8c-109">同様に、`HttpWebResponse` オブジェクトは、HTTP および HTTPS 要求からの応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="59f8c-109">Similarly, the `HttpWebResponse` object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="59f8c-110">`HttpWebResponse` オブジェクトの HTTP 固有プロパティにアクセスするには、`WebResponse` オブジェクトを `HttpWebResponse` 型にキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59f8c-110">To access the HTTP-specific properties of the `HttpWebResponse` object, you need to cast `WebResponse` objects to the `HttpWebResponse` type.</span></span>  
  
<span data-ttu-id="59f8c-111">.NET Framework では、URI スキームの "file:" を使用するリソースの要求を処理するために、<xref:System.Net.FileWebRequest> および <xref:System.Net.FileWebResponse> クラスも提供します。</span><span class="sxs-lookup"><span data-stu-id="59f8c-111">.NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="59f8c-112">同様に、"ftp:" スキームを使用するリソースの要求を処理するために、<xref:System.Net.FtpWebRequest> および <xref:System.Net.FtpWebResponse> クラスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="59f8c-112">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="59f8c-113">要求が、これらのスキームのいずれかを使用するリソースに対するものである場合、`WebRequest.Create` メソッドを使用して、要求を行うために使用するオブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="59f8c-113">If your request is for a resource that uses any of these schemes, you can use the `WebRequest.Create` method to obtain an object with which to make your request.</span></span>  
  
<span data-ttu-id="59f8c-114">アプリケーション レベルの他のプロトコルを使用する要求を処理するには、`WebRequest` および `WebResponse` から派生するプロトコル固有のクラスを実装します。</span><span class="sxs-lookup"><span data-stu-id="59f8c-114">To handle requests that use other application-level protocols, implement protocol-specific classes derived from `WebRequest` and `WebResponse`.</span></span> <span data-ttu-id="59f8c-115">詳細については、「[プラグ可能なプロトコルのプログラミング](programming-pluggable-protocols.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59f8c-115">For more information, see [Programming Pluggable Protocols](programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f8c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="59f8c-116">See also</span></span>

- [<span data-ttu-id="59f8c-117">方法: WebRequest クラスを使用してデータを要求する</span><span class="sxs-lookup"><span data-stu-id="59f8c-117">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="59f8c-118">データの要求</span><span class="sxs-lookup"><span data-stu-id="59f8c-118">Requesting Data</span></span>](requesting-data.md)
