---
title: '方法: WebRequest クラスを使用してデータを要求する'
ms.date: 03/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
ms.openlocfilehash: e670a2a503ce704eff847e9e0b3ee340ab52fe62
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048163"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="b0e12-102">方法: WebRequest クラスを使用してデータを要求する</span><span class="sxs-lookup"><span data-stu-id="b0e12-102">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="b0e12-103">次の手順では、Web ページやファイルなどのリソースをサーバーから要求するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="b0e12-104">リソースは URI で識別される必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0e12-104">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="b0e12-105">ホスト サーバーからデータを要求するには</span><span class="sxs-lookup"><span data-stu-id="b0e12-105">To request data from a host server</span></span>

1. <span data-ttu-id="b0e12-106">リソースの URI を指定して <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> を呼び出して <xref:System.Net.WebRequest> インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="b0e12-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="b0e12-108">.NET Framework は、*http:* 、*https:* 、*ftp:* 、*file:* で始まる URI に対応する <xref:System.Net.WebRequest> と <xref:System.Net.WebResponse> クラスから派生したプロトコル固有のクラスを提供します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="b0e12-109">プロトコル固有のプロパティを設定する必要がある場合、<xref:System.Net.WebRequest> または <xref:System.Net.WebResponse> オブジェクトをプロトコル固有のオブジェクトの種類にキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0e12-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="b0e12-110">詳細については、「[プラグ可能なプロトコルのプログラミング](programming-pluggable-protocols.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0e12-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="b0e12-111">`WebRequest` オブジェクトで必要なプロパティ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="b0e12-112">たとえば、認証を有効にするには、<xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> プロパティを <xref:System.Net.NetworkCredential> クラスのインスタンスに設定します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="b0e12-113"><xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> を呼び出してサーバーに要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b0e12-114">このメソッドは、サーバーの応答を格納するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="b0e12-115">返された <xref:System.Net.WebResponse> オブジェクトの型は、要求の URI のスキームで決定されます。</span><span class="sxs-lookup"><span data-stu-id="b0e12-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="b0e12-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-116">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="b0e12-117">`WebResponse` オブジェクトのプロパティにアクセスするか、またはそれをプロトコル固有インスタンスにキャストして、プロトコル固有のプロパティを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b0e12-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="b0e12-118">たとえば、<xref:System.Net.HttpWebResponse> の HTTP 固有のプロパティにアクセスするには、`WebResponse` オブジェクトを `HttpWebResponse` 参照にキャストします。</span><span class="sxs-lookup"><span data-stu-id="b0e12-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="b0e12-119">次のコード例では、応答で送信される HTTP 固有の <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> プロパティを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="b0e12-120">サーバーによって送信された応答データを格納しているストリームを取得するには、<xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b0e12-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-121">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="b0e12-122">応答オブジェクトからデータを読み取った後に、<xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> メソッドを使用してそのオブジェクトを閉じるか、<xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> メソッドを使用して応答ストリームを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b0e12-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b0e12-123">応答オブジェクトまたはストリームのいずれかを閉じないと、アプリケーションからサーバーへの接続が不足し、追加の要求を処理できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b0e12-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="b0e12-124">`WebResponse.Close` メソッドは応答を閉じるときに `Stream.Close` を呼び出すため、応答とストリーム オブジェクトの両方で `Close` を呼び出す必要はありませんが、呼び出しても害はありません。</span><span class="sxs-lookup"><span data-stu-id="b0e12-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="b0e12-125">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0e12-125">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="b0e12-126">例</span><span class="sxs-lookup"><span data-stu-id="b0e12-126">Example</span></span>

<span data-ttu-id="b0e12-127">次のコード例は、Web サーバーへの要求を作成し、その応答内のデータを読み取る方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b0e12-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="b0e12-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0e12-128">See also</span></span>

- [<span data-ttu-id="b0e12-129">インターネット要求の作成</span><span class="sxs-lookup"><span data-stu-id="b0e12-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="b0e12-130">ネットワーク上でストリームを使用する</span><span class="sxs-lookup"><span data-stu-id="b0e12-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="b0e12-131">プロキシを介したインターネットへのアクセス</span><span class="sxs-lookup"><span data-stu-id="b0e12-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="b0e12-132">データの要求</span><span class="sxs-lookup"><span data-stu-id="b0e12-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="b0e12-133">方法: WebRequest クラスを使用してデータを送信する</span><span class="sxs-lookup"><span data-stu-id="b0e12-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
