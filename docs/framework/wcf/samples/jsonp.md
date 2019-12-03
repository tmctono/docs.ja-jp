---
title: JSONP
ms.date: 03/30/2017
ms.assetid: c13b4d7b-dac7-4ffd-9f84-765c903511e1
ms.openlocfilehash: 82fa0bb09ebdf3ca2325872c2b884f4940de17ed
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715717"
---
# <a name="jsonp"></a><span data-ttu-id="fc916-102">JSONP</span><span class="sxs-lookup"><span data-stu-id="fc916-102">JSONP</span></span>
<span data-ttu-id="fc916-103">このサンプルでは、WCF REST サービスの JSONP (JSON with Padding) をサポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fc916-103">This sample demonstrates how to support JSON with Padding (JSONP) in WCF REST services.</span></span> <span data-ttu-id="fc916-104">JSONP とは、現在のドキュメントでスクリプト タグを生成してドメイン間スクリプトを呼び出す際に使用される変換です。</span><span class="sxs-lookup"><span data-stu-id="fc916-104">JSONP is a convention used to invoke cross-domain scripts by generating script tags in the current document.</span></span> <span data-ttu-id="fc916-105">結果は、指定したコールバック関数で返されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-105">The result is returned in a specified callback function.</span></span> <span data-ttu-id="fc916-106">JSONP は、`<script src="http://..." >` などのタグで任意のドメインからのスクリプトを評価でき、このようなタグによって取得されたスクリプトを既に他の関数が定義されている範囲で評価するという考えに基づいています。</span><span class="sxs-lookup"><span data-stu-id="fc916-106">JSONP is based on the idea that tags such as `<script src="http://..." >` can evaluate scripts from any domain and the script retrieved by those tags is evaluated within a scope in which other functions may already be defined.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="fc916-107">例</span><span class="sxs-lookup"><span data-stu-id="fc916-107">Demonstrates</span></span>
 <span data-ttu-id="fc916-108">JSONP によるドメイン間スクリプト。</span><span class="sxs-lookup"><span data-stu-id="fc916-108">Cross-domain scripting with JSONP.</span></span>

## <a name="discussion"></a><span data-ttu-id="fc916-109">ディスカッション</span><span class="sxs-lookup"><span data-stu-id="fc916-109">Discussion</span></span>
 <span data-ttu-id="fc916-110">このサンプルには、ブラウザーで表示された後にスクリプト ブロックを動的に追加する Web ページが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc916-110">The sample includes a Web page that dynamically adds a script block after the page has been rendered in the browser.</span></span> <span data-ttu-id="fc916-111">このスクリプト ブロックは、`GetCustomer` 操作を 1 つ持つ WCF REST サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc916-111">This script block calls a WCF REST service that has a single operation, `GetCustomer`.</span></span> <span data-ttu-id="fc916-112">WCF REST サービスは、コールバック関数名でラップされた顧客の名前とアドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="fc916-112">The WCF REST service returns a customer’s name and address wrapped in a callback function name.</span></span> <span data-ttu-id="fc916-113">WCF REST サービスが応答を返すと、顧客データを使用して Web ページ上のコールバック関数が呼び出され、このコールバック関数によって Web ページ上に顧客データが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-113">When the WCF REST service responds, the callback function on the Web page is invoked with the customer data and the callback function displays the data on the Web page.</span></span> <span data-ttu-id="fc916-114">スクリプト タグの挿入とコールバック関数の実行は、ASP.NET AJAX ScriptManager コントロールによって自動的に処理されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-114">The injection of the script tag and the execution of the callback function is automatically handled by the ASP.NET AJAX ScriptManager control.</span></span> <span data-ttu-id="fc916-115">次のコードに示すように、使用パターンはすべての ASP.NET AJAX プロキシと同じで、JSONP を有効にするための行が 1 つ追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-115">The usage pattern is the same as with all ASP.NET AJAX proxies, with the addition of one line to enable JSONP, as shown in the following code:</span></span>

```csharp
var proxy = new JsonpAjaxService.CustomerService();
proxy.set_enableJsonp(true);
proxy.GetCustomer(onSuccess, onFail, null);
```

 <span data-ttu-id="fc916-116">Web ページでは、WCF REST サービスを呼び出すことができます。これは、WCF REST サービスが、<xref:System.ServiceModel.Description.WebScriptEndpoint> が `crossDomainScriptAccessEnabled` に設定された `true` を使用しているからです。</span><span class="sxs-lookup"><span data-stu-id="fc916-116">The Web page can call the WCF REST service because the service is using the <xref:System.ServiceModel.Description.WebScriptEndpoint> with `crossDomainScriptAccessEnabled` set to `true`.</span></span> <span data-ttu-id="fc916-117">これらの構成はどちらも、Web.config ファイルの \<System.servicemodel > 要素の下に行われます。</span><span class="sxs-lookup"><span data-stu-id="fc916-117">Both of these configurations are done in the Web.config file under the \<system.serviceModel> element.</span></span>

```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>
  <standardEndpoints>
    <webScriptEndpoint>
      <standardEndpoint name="" crossDomainScriptAccessEnabled="true"/>
    </webScriptEndpoint>
  </standardEndpoints>
</system.serviceModel>
```

 <span data-ttu-id="fc916-118">ScriptManager はサービスとのやり取りを管理し、JSONP アクセスの手動実装の複雑さを隠蔽します。</span><span class="sxs-lookup"><span data-stu-id="fc916-118">ScriptManager manages the interaction with the service and hides away the complexity of manually implementing JSONP access.</span></span> <span data-ttu-id="fc916-119">`crossDomainScriptAccessEnabled` が `true` に設定されていて、操作の応答形式が JSON である場合、WCF インフラストラクチャは、コールバッククエリ文字列パラメーターの要求の URI を検査し、コールバッククエリ文字列パラメーターの値を使用して JSON 応答をラップします。</span><span class="sxs-lookup"><span data-stu-id="fc916-119">When `crossDomainScriptAccessEnabled` is set to `true` and the response format for an operation is JSON, the WCF infrastructure inspects the URI of the request for a callback query string parameter and wraps the JSON response with the value of the callback query string parameter.</span></span> <span data-ttu-id="fc916-120">このサンプルでは、Web ページは次の URI を使用して WCF REST サービスを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fc916-120">In the sample, the Web page calls the WCF REST service with the following URI.</span></span>

```http
http://localhost:33695/CustomerService/GetCustomer?callback=Sys._json0
```

 <span data-ttu-id="fc916-121">コールバック クエリ文字列パラメーターには `JsonPCallback` の値が含まれているため、WCF サービスは次の例に示す JSONP 応答を返します。</span><span class="sxs-lookup"><span data-stu-id="fc916-121">Because the callback query string parameter has a value of `JsonPCallback`, the WCF service returns a JSONP response shown in the following example.</span></span>

```json
Sys._json0({"__type":"Customer:#Microsoft.Samples.Jsonp","Address":"1 Example Way","Name":"Bob"});
```

 <span data-ttu-id="fc916-122">JSONP 応答には、JSON として書式設定され、Web ページが要求したコールバック関数名でラップされた顧客データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fc916-122">This JSONP response includes the customer data formatted as JSON, wrapped with the callback function name that the Web page requested.</span></span> <span data-ttu-id="fc916-123">ScriptManager は、ドメイン間要求を実現するスクリプト タグを使用してこのコールバックを実行し、ASP.NET AJAX プロキシの GetCustomer 操作に渡された onSuccess ハンドラーに結果を渡します。</span><span class="sxs-lookup"><span data-stu-id="fc916-123">ScriptManager will execute this callback using a script tag to accomplish the cross-domain request, and then pass the result to the onSuccess handler that was passed to the GetCustomer operation of the ASP.NET AJAX proxy.</span></span>

 <span data-ttu-id="fc916-124">このサンプルは2つの ASP.NET web アプリケーションで構成されています。1つは WCF サービスだけを含み、もう1つはサービスを呼び出す .aspx web ページを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="fc916-124">The sample consists of two ASP.NET web applications: one contains just a WCF service, and another one contains the .aspx webpage, which calls the service.</span></span> <span data-ttu-id="fc916-125">ソリューションを実行すると、Visual Studio 2012 は異なるポートで2つの web サイトをホストします。これにより、サービスとクライアントが異なるドメイン上に存在する環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-125">When running the solution, Visual Studio 2012 will host the two websites on different ports, which creates an environment where the service and client live on different domains.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc916-126">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="fc916-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fc916-127">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fc916-127">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="fc916-128">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459)にアクセスして、すべての WINDOWS COMMUNICATION FOUNDATION (wcf) と [!INCLUDE[wf1](../../../../includes/wf1-md.md)] サンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="fc916-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fc916-129">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fc916-129">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\AJAX\JSONP`  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="fc916-130">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="fc916-130">To run the sample</span></span>  
  
1. <span data-ttu-id="fc916-131">JSONP サンプルのソリューションを開きます。</span><span class="sxs-lookup"><span data-stu-id="fc916-131">Open the solution for the JSONP Sample.</span></span>  
  
2. <span data-ttu-id="fc916-132">F5 キーを押して、ブラウザーで `http://localhost:26648/JSONPClientPage.aspx` を起動します。</span><span class="sxs-lookup"><span data-stu-id="fc916-132">Press F5 to launch `http://localhost:26648/JSONPClientPage.aspx` in the browser.</span></span>  
  
3. <span data-ttu-id="fc916-133">ページが読み込まれた後、"名前" と "アドレス" のテキスト入力に値が設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fc916-133">Notice that after the page loads, the text inputs for "Name" and "Address" are populated by values.</span></span>  <span data-ttu-id="fc916-134">これらの値は、ブラウザーがページの表示を終了した後に、WCF サービスの呼び出しから指定されました。</span><span class="sxs-lookup"><span data-stu-id="fc916-134">These values were supplied from a call to the WCF service after the browser finished rendering the page.</span></span>
