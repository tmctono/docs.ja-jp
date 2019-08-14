---
title: HTTP POST を使用する AJAX サービス
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: c5e5de34573fbfc8a5c6e9607d10881941a9bed5
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972018"
---
# <a name="ajax-service-using-http-post"></a><span data-ttu-id="61bc4-102">HTTP POST を使用する AJAX サービス</span><span class="sxs-lookup"><span data-stu-id="61bc4-102">AJAX Service Using HTTP POST</span></span>

<span data-ttu-id="61bc4-103">このサンプルでは、Windows Communication Foundation (WCF) を使用して、HTTP POST を使用する AJAX (ASP.NET 非同期 JavaScript and XML) サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="61bc4-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that uses HTTP POST.</span></span> <span data-ttu-id="61bc4-104">AJAX サービスには、Web ブラウザー クライアントから基本的な JavaScript コードを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="61bc4-104">An AJAX service is one that you can access by using basic JavaScript code from a Web browser client.</span></span> <span data-ttu-id="61bc4-105">このサンプルは、[基本的な AJAX サービス](../../../../docs/framework/wcf/samples/basic-ajax-service.md)のサンプルに基づいています。2つのサンプルの唯一の違いは、http GET の代わりに HTTP POST を使用することです。</span><span class="sxs-lookup"><span data-stu-id="61bc4-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample; the only difference between the two samples is the use of HTTP POST instead of HTTP GET.</span></span>

<span data-ttu-id="61bc4-106">Windows Communication Foundation (WCF) での ajax サポートは、 `ScriptManager`コントロールを介して ASP.NET ajax で使用できるように最適化されています。</span><span class="sxs-lookup"><span data-stu-id="61bc4-106">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="61bc4-107">ASP.NET AJAX で WCF を使用する例については、 [ajax のサンプル](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61bc4-107">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>

> [!NOTE]
> <span data-ttu-id="61bc4-108">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61bc4-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="61bc4-109">次のサンプルのサービスは、AJAX 固有のコードを持たない WCF サービスです。</span><span class="sxs-lookup"><span data-stu-id="61bc4-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span>

<span data-ttu-id="61bc4-110">属性が操作に適用されている場合、 <xref:System.ServiceModel.Web.WebGetAttribute>または属性が適用されていない場合は、既定の HTTP 動詞 ("POST") が使用されます。 <xref:System.ServiceModel.Web.WebInvokeAttribute></span><span class="sxs-lookup"><span data-stu-id="61bc4-110">If the <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute is applied on an operation, or the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="61bc4-111">POST 要求は、GET 要求よりも作成が困難ですが、キャッシュされません。キャッシュが不適切な操作に対しては、POST 要求を使用します。</span><span class="sxs-lookup"><span data-stu-id="61bc4-111">POST requests are harder to construct than GET requests, but they are not cached; use POST requests for all operations where caching is not appropriate.</span></span>

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

<span data-ttu-id="61bc4-112">基本的な AJAX サービスのサンプルの場合と同様に、<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> を使用してサービスに AJAX エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="61bc4-112">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="61bc4-113">GET 要求とは異なり、POST サービスはブラウザーから呼び出すことができません。</span><span class="sxs-lookup"><span data-stu-id="61bc4-113">Unlike GET requests, you cannot invoke POST services from the browser.</span></span> <span data-ttu-id="61bc4-114">たとえば、に移動する`http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200`と、エラーが発生します。これは、 `n1` POST `n2`サービスでは、URL ではなく JSON 形式のメッセージ本文で、およびパラメーターが送信されることを想定しているためです。</span><span class="sxs-lookup"><span data-stu-id="61bc4-114">For example, navigating to `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` results in an error, because the POST service expects the `n1` and `n2` parameters to be sent in the message body in the JSON format, and not in the URL.</span></span>

<span data-ttu-id="61bc4-115">クライアントの Web ページの PostAjaxClientPage.aspx には、ユーザーがページ上のいずれかの操作ボタンをクリックするとサービスを呼び出す ASP.NET コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="61bc4-115">The client Web page PostAjaxClientPage.aspx contains ASP.NET code to invoke the service whenever the user clicks one of the operation buttons on the page.</span></span> <span data-ttu-id="61bc4-116">サービスは、[基本 AJAX サービス](../../../../docs/framework/wcf/samples/basic-ajax-service.md)サンプルと同じ方法で GET 要求を使用して応答します。</span><span class="sxs-lookup"><span data-stu-id="61bc4-116">The service responds in the same way as in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, with the GET request.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61bc4-117">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="61bc4-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="61bc4-118">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="61bc4-118">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="61bc4-119">このディレクトリが存在しない場合は、 [Windows Communication Foundation (wcf) および Windows Workflow Foundation (WF) のサンプルの .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780)にアクセスして、すべての[!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (wcf) とサンプルをダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="61bc4-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="61bc4-120">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="61bc4-120">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="61bc4-121">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="61bc4-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="61bc4-122">[Windows Communication Foundation のサンプルについ](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ては、セットアップ手順の1回限りのセットアップ手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="61bc4-122">Ensure that you perform the setup instructions [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="61bc4-123">「 [Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)」の説明に従って、ソリューション postajaxservice.sln をビルドします。</span><span class="sxs-lookup"><span data-stu-id="61bc4-123">Build the solution PostAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="61bc4-124">移動 `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (開かないで PostAjaxClientPage.aspx プロジェクト ディレクトリからブラウザーで)。</span><span class="sxs-lookup"><span data-stu-id="61bc4-124">Navigate to `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (do not open PostAjaxClientPage.aspx in the browser from the project directory).</span></span>
