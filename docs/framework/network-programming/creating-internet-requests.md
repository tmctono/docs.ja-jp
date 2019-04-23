---
title: インターネット要求の作成
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
ms.openlocfilehash: 2a4915796310e4f6899d833f20bc5260e0ee032b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171034"
---
# <a name="creating-internet-requests"></a><span data-ttu-id="8a2ef-102">インターネット要求の作成</span><span class="sxs-lookup"><span data-stu-id="8a2ef-102">Creating Internet Requests</span></span>
<span data-ttu-id="8a2ef-103">アプリケーションは、<xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> メソッドを使用して <xref:System.Net.WebRequest> のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-103">Applications create <xref:System.Net.WebRequest> instances through the <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8a2ef-104">これは、渡された URI スキームに基づいて **WebRequest** から派生するクラスを作成する静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-104">This is a static method that creates a class derived from **WebRequest** based on the URI scheme passed to it.</span></span>  
  
## <a name="web-file-and-ftp-requests"></a><span data-ttu-id="8a2ef-105">Web、ファイルおよび FTP 要求</span><span class="sxs-lookup"><span data-stu-id="8a2ef-105">Web, File and FTP Requests</span></span>  
 <span data-ttu-id="8a2ef-106">.NET Framework は、**WebRequest** から派生する <xref:System.Net.HttpWebRequest> クラスを提供することにより、HTTP および HTTPS 要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-106">The .NET Framework provides the <xref:System.Net.HttpWebRequest> class, which is derived from **WebRequest**, to handle HTTP and HTTPS requests.</span></span> <span data-ttu-id="8a2ef-107">ほとんどの場合、**WebRequest** クラスは要求を行うのに必要なすべてのプロパティを提供しますが、必要に応じて、**WebRequest.Create** メソッドで作成した **WebRequest** オブジェクトを **HttpWebRequest** 型にキャストすることにより、その要求の HTTP 固有のプロパティにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-107">In most cases, the **WebRequest** class provides all the properties you need to make a request; however, if necessary, you can cast **WebRequest** objects created by the **WebRequest.Create** method to the **HttpWebRequest** type to access the HTTP-specific properties of the request.</span></span> <span data-ttu-id="8a2ef-108">同様に、**HttpWebResponse** オブジェクトは、HTTP および HTTPS 要求からの応答を処理します。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-108">Similarly, the **HttpWebResponse** object handles the responses from HTTP and HTTPS requests.</span></span> <span data-ttu-id="8a2ef-109">**HttpWebResponse** オブジェクトの HTTP 固有のプロパティにアクセスするには、**WebResponse** オブジェクトを **HttpWebResponse** 型にキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-109">To access the HTTP-specific properties of the **HttpWebResponse** object, you need to cast **WebResponse** objects to the **HttpWebResponse** type.</span></span>  
  
 <span data-ttu-id="8a2ef-110">.NET Framework では、URI スキームの "file:" を使用するリソースの要求を処理するために、<xref:System.Net.FileWebRequest> および <xref:System.Net.FileWebResponse> クラスも提供します。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-110">The .NET Framework also provides the <xref:System.Net.FileWebRequest> and <xref:System.Net.FileWebResponse> classes to handle requests for resources that use the "file:" URI scheme.</span></span> <span data-ttu-id="8a2ef-111">同様に、"ftp:" スキームを使用するリソースの要求を処理するために、<xref:System.Net.FtpWebRequest> および <xref:System.Net.FtpWebResponse> クラスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-111">Likewise, the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes are provided to handle requests for resources that use the "ftp:" scheme.</span></span> <span data-ttu-id="8a2ef-112">要求が、これらのスキームのいずれかを使用するリソースに対するものである場合、**WebRequest.Create** メソッドを使用して、要求を行うために使用するオブジェクトを取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-112">If your request is for a resource that uses any of these schemes, you can use the **WebRequest.Create** method to obtain an object with which to make your request.</span></span>  
  
 <span data-ttu-id="8a2ef-113">アプリケーション レベルの他のプロトコルを使用する要求を処理するには、**WebRequest** および **WebResponse** から派生するプロトコル固有のクラスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-113">To handle requests that use other application-level protocols, you need to implement protocol-specific classes derived from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="8a2ef-114">詳細については、「[Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md)」(プラグ可能なプロトコルのプログラミング) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a2ef-114">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a2ef-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a2ef-115">See also</span></span>

- [<span data-ttu-id="8a2ef-116">方法: WebRequest クラスを使用してデータを要求する</span><span class="sxs-lookup"><span data-stu-id="8a2ef-116">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="8a2ef-117">データの要求</span><span class="sxs-lookup"><span data-stu-id="8a2ef-117">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
