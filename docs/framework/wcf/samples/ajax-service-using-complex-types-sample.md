---
title: 複合型を使用した AJAX サービスのサンプル
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: cde7e48d0f0c44d68266d60399ac197d322a42cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342220"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="6f1f0-102">複合型を使用した AJAX サービスのサンプル</span><span class="sxs-lookup"><span data-stu-id="6f1f0-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="6f1f0-103">このサンプルでは、Windows Communication Foundation (WCF) を使用して、複合型のインスタンスを作成し、サービスとクライアントの JavaScript Object Notation (JSON) との間で送信する ASP.NET Asynchronous JavaScript and XML (AJAX) サービスを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="6f1f0-104">AJAX サービスには、Web ブラウザー クライアントから JavaScript コードを使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="6f1f0-105">このサンプルでビルド、[基本的な AJAX サービス](../../../../docs/framework/wcf/samples/basic-ajax-service.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="6f1f0-106">WCF での AJAX のサポートがを介して ASP.NET AJAX と共に使用するために最適化された、<xref:System.Web.UI.ScriptManager>コントロール。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="6f1f0-107">WCF を使用して ASP.NET AJAX での例は、次を参照してください。、 [AJAX のサンプル](ajax.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f1f0-108">このサンプルのセットアップ手順とビルド手順については、このトピックの最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6f1f0-109">次のサンプルのサービスには、AJAX 固有のコードなしで WCF サービスです。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="6f1f0-110"><xref:System.ServiceModel.Web.WebGetAttribute> 属性は適用されないため、既定の HTTP 動詞 ("POST") が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="6f1f0-111">サービスには 1 つの `DoMath` 操作があります。この操作は、`MathResult` という名前の複合型を返します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="6f1f0-112">複合型は標準のデータ コントラクト型で、AJAX 固有のコードも含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 <span data-ttu-id="6f1f0-113">基本的な AJAX サービスのサンプルの場合と同様に、<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> を使用してサービスに AJAX エンドポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="6f1f0-114">クライアント Web ページ ComplexTypeClientPage.aspx には、ユーザーがクリックしたときに、サービスを呼び出す ASP.NET および JavaScript のコードが含まれています、**計算**ページ上のボタン。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="6f1f0-115">サービスを呼び出すコードは、JSON 本文を構築しのような HTTP POST を使用して送信、 [AJAX サービスを使用して HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)サンプル。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="6f1f0-116">サービス呼び出しに成功したら、生成された JavaScript オブジェクトのそれぞれのデータ メンバー (`sum`、`difference`、`product`、および `quotient`) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6f1f0-117">サンプルをセットアップ、ビルド、および実行するには</span><span class="sxs-lookup"><span data-stu-id="6f1f0-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6f1f0-118">実行したことを確認、 [Windows Communication Foundation サンプルの 1 回限りのセットアップ手順](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6f1f0-119">」の説明に従って、ソリューション ComplexTypeAjaxService.sln をビルド[Windows Communication Foundation サンプルのビルド](../../../../docs/framework/wcf/samples/building-the-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6f1f0-120">移動します`http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx`(はプロジェクト ディレクトリからブラウザーで ComplexTypeClientPage.aspx を開くしない操作を行います)。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6f1f0-121">サンプルは、既にコンピューターにインストールされている場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="6f1f0-122">続行する前に、次の (既定の) ディレクトリを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6f1f0-123">このディレクトリが存在しない場合に移動[Windows Communication Foundation (WCF) と .NET Framework 4 向けの Windows Workflow Foundation (WF) サンプル](https://go.microsoft.com/fwlink/?LinkId=150780)すべて Windows Communication Foundation (WCF) をダウンロードして[!INCLUDE[wf1](../../../../includes/wf1-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6f1f0-124">このサンプルは、次のディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6f1f0-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="6f1f0-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f1f0-125">See also</span></span>

- [<span data-ttu-id="6f1f0-126">基本的な AJAX サービス</span><span class="sxs-lookup"><span data-stu-id="6f1f0-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
