---
title: 構成を使用しない AJAX サービス
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: f5ebc952fcc6c2ca4c7272a90dc1929d4b4a0eae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002821"
---
# <a name="ajax-service-without-configuration"></a><span data-ttu-id="05e2d-102">構成を使用しない AJAX サービス</span><span class="sxs-lookup"><span data-stu-id="05e2d-102">AJAX Service Without Configuration</span></span>
<span data-ttu-id="05e2d-103">このサンプルは、Windows Communication Foundation (WCF) を使用して、任意の構成を使用せずに基本的な ASP.NET Asynchronous JavaScript and XML (AJAX) サービス (Web ブラウザー クライアントから JavaScript コードを使用してアクセスできるサービス) を作成する方法を示します。設定。</span><span class="sxs-lookup"><span data-stu-id="05e2d-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create a basic ASP.NET Asynchronous JavaScript and XML (AJAX) service (a service that you can access by using JavaScript code from a Web browser client) without using any configuration settings.</span></span> <span data-ttu-id="05e2d-104">このサービスは .svc ファイルの特殊な構文を使用して AJAX エンドポイントを自動的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="05e2d-104">The service uses special syntax in the .svc file to automatically enable an AJAX endpoint.</span></span>  
  
 <span data-ttu-id="05e2d-105">WCF での AJAX のサポートがを介して ASP.NET AJAX と共に使用するために最適化された、`ScriptManager`コントロール。</span><span class="sxs-lookup"><span data-stu-id="05e2d-105">AJAX support in WCF is optimized for use with ASP.NET AJAX through the `ScriptManager` control.</span></span> <span data-ttu-id="05e2d-106">WCF を使用して ASP.NET AJAX での例は、次を参照してください。、 [Ajax のサンプル](ajax.md)します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-106">For an example of using WCF with ASP.NET AJAX, see the [Ajax Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05e2d-107">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05e2d-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="05e2d-108">このサンプルは、HTTP POST を使用した AJAX サービスに基づいています。</span><span class="sxs-lookup"><span data-stu-id="05e2d-108">This sample builds upon the AJAX Service Using HTTP POST.</span></span> <span data-ttu-id="05e2d-109">」の説明に従って、[基本的な AJAX サービス](../../../../docs/framework/wcf/samples/basic-ajax-service.md)サンプルでは、<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>サービスをホストするために使用します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-109">As described in the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used to host the service.</span></span>  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <span data-ttu-id="05e2d-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> は、<xref:System.ServiceModel.Description.WebScriptEndpoint> をサービスに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-110"><xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> automatically adds a <xref:System.ServiceModel.Description.WebScriptEndpoint> to the service.</span></span> <span data-ttu-id="05e2d-111">エンドポイントに対する構成変更が不要な場合、`<system.ServiceModel>` セクションはサービスの Web.config ファイルから完全に削除できます。</span><span class="sxs-lookup"><span data-stu-id="05e2d-111">If no configuration changes need to be made to the endpoint, the `<system.ServiceModel>` section can be completely removed from the Web.config file for the service.</span></span> <span data-ttu-id="05e2d-112">Web.config ファイルには、ConfigFreeClientPage.aspx で使用される ASP.NET 設定がいくつか含まれます。</span><span class="sxs-lookup"><span data-stu-id="05e2d-112">The Web.config file contains some ASP.NET settings, which are used by ConfigFreeClientPage.aspx.</span></span> <span data-ttu-id="05e2d-113">そうでない場合は、Web.config ファイル全体を削除できます。</span><span class="sxs-lookup"><span data-stu-id="05e2d-113">If that were not the case, the entire Web.config file could be removed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05e2d-114">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="05e2d-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="05e2d-115">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="05e2d-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="05e2d-116">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="05e2d-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05e2d-117">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="05e2d-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05e2d-118">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="05e2d-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="05e2d-119">セットアップ手順を実行することを確認します。 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-119">Ensure that you perform the setup instructions in [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="05e2d-120">」の説明に従って、ソリューション ConfigFreeAjaxService.sln をビルド[Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-120">Build the solution ConfigFreeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="05e2d-121">移動します`http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx`(はプロジェクト ディレクトリ内からブラウザーで ConfigFreeClientPage.aspx を開くしない操作を行います)。</span><span class="sxs-lookup"><span data-stu-id="05e2d-121">Navigate to `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (do not open ConfigFreeClientPage.aspx in the browser from within the project directory).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05e2d-122">このサンプルを実行する場合、IIS の ServiceModelSamples フォルダーで匿名認証と Windows 認証が同時に有効になっていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="05e2d-122">When running this sample, please ensure that Anonymous Authentication and Windows Authentication are not enabled simultaneously for the ServiceModelSamples folder in IIS.</span></span> <span data-ttu-id="05e2d-123">有効になっている場合は、Windows 認証を無効にしてください。</span><span class="sxs-lookup"><span data-stu-id="05e2d-123">If that is the case, please disable Windows Authentication.</span></span> <span data-ttu-id="05e2d-124">サンプルの実行が終了したら、Windows 認証を有効にし、"iisreset" を実行します。</span><span class="sxs-lookup"><span data-stu-id="05e2d-124">Once you have run the sample, enable Windows Authentication and run "iisreset".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e2d-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="05e2d-125">See also</span></span>

- [<span data-ttu-id="05e2d-126">基本的な AJAX サービス</span><span class="sxs-lookup"><span data-stu-id="05e2d-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
