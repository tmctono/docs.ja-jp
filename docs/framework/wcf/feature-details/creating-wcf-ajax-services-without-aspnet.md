---
title: ASP.NET を使用せずに WCF AJAX サービスを作成する方法
ms.date: 03/30/2017
ms.assetid: ba4a7d1b-e277-4978-9f62-37684e6dc934
ms.openlocfilehash: 04d2831407f4aa32c72aabbbff0e6fdde769bd23
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895092"
---
# <a name="creating-wcf-ajax-services-without-aspnet"></a><span data-ttu-id="b858c-102">ASP.NET を使用せずに WCF AJAX サービスを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b858c-102">Creating WCF AJAX Services without ASP.NET</span></span>
<span data-ttu-id="b858c-103">Windows Communication Foundation (WCF) AJAX サービスには、ASP.NET AJAX を必要とせずに、任意の JavaScript 対応の Web ページからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b858c-103">Windows Communication Foundation (WCF) AJAX services can be accessed from any JavaScript-enabled Web page, without requiring ASP.NET AJAX.</span></span> <span data-ttu-id="b858c-104">このトピックでは、このような WCF サービスを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b858c-104">This topic describes how to create such a WCF service.</span></span>  
  
 <span data-ttu-id="b858c-105">ASP.NET AJAX で WCF を使用する方法については、「 [ASP.NET ajax 用の Wcf サービスの作成](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b858c-105">For instructions on using WCF with ASP.NET AJAX, see [Creating WCF Services for ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md).</span></span>  
  
 <span data-ttu-id="b858c-106">WCF AJAX サービスを作成するには、次の3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="b858c-106">There are three parts to a creating a WCF AJAX service:</span></span>  
  
- <span data-ttu-id="b858c-107">ブラウザーからアクセスできる AJAX エンドポイントの作成</span><span class="sxs-lookup"><span data-stu-id="b858c-107">Creating an AJAX endpoint that can be accessed from the browser.</span></span>  
  
- <span data-ttu-id="b858c-108">AJAX 互換サービス コントラクトの作成</span><span class="sxs-lookup"><span data-stu-id="b858c-108">Creating an AJAX-compatible service contract.</span></span>  
  
- <span data-ttu-id="b858c-109">WCF AJAX サービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="b858c-109">Accessing WCF AJAX services.</span></span>  
  
## <a name="creating-an-ajax-endpoint"></a><span data-ttu-id="b858c-110">AJAX エンドポイントの作成</span><span class="sxs-lookup"><span data-stu-id="b858c-110">Creating an AJAX Endpoint</span></span>  
 <span data-ttu-id="b858c-111">WCF サービスで AJAX のサポートを有効にする最も基本的な方法は、 <xref:System.ServiceModel.Activation.WebServiceHostFactory>次の例のように、サービスに関連付けられている .svc ファイルでを使用することです。</span><span class="sxs-lookup"><span data-stu-id="b858c-111">The most basic way to enable AJAX support in a WCF service is to use the <xref:System.ServiceModel.Activation.WebServiceHostFactory> in the .svc file associated with the service, as in the following example.</span></span>  
  
```text
<%ServiceHost   
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CityService"  
    Factory=System.ServiceModel.Activation.WebServiceHostFactory  
%>  
```  
  
 <span data-ttu-id="b858c-112">構成を使用して AJAX エンドポイントを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b858c-112">Alternatively, you can also use configuration to add an AJAX endpoint.</span></span> <span data-ttu-id="b858c-113">次のコード スニペットに示すように、サービス エンドポイントで <xref:System.ServiceModel.WebHttpBinding> を使用し、<xref:System.ServiceModel.Description.WebHttpBehavior> を使用してこのエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="b858c-113">Use the <xref:System.ServiceModel.WebHttpBinding> on the service endpoint and configure that endpoint with the <xref:System.ServiceModel.Description.WebHttpBehavior> as shown in the following code snippet.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="AjaxBehavior">  
          <webHttp/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Ajax.Samples.CityService">  
        <endpoint   
          address="ajaxEndpoint"  
          behaviorConfiguration="AjaxBehavior"  
          binding="webHttpBinding"  
          contract="Microsoft.Ajax.Samples.ICityService" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="b858c-114">実際の例については、「 [JSON と XML を使用した AJAX サービス](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b858c-114">For a working example, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>  
  
## <a name="creating-an-ajax-compatible-service-contract"></a><span data-ttu-id="b858c-115">AJAX 互換サービス コントラクトの作成</span><span class="sxs-lookup"><span data-stu-id="b858c-115">Creating an AJAX-Compatible Service Contract</span></span>  
 <span data-ttu-id="b858c-116">既定では、AJAX エンドポイントを介して公開されるサービス コントラクトは、XML 形式でデータを返します。</span><span class="sxs-lookup"><span data-stu-id="b858c-116">By default, service contracts exposed over an AJAX endpoint return data in the XML format.</span></span> <span data-ttu-id="b858c-117">また、次の例に示すように、既定では、エンドポイント アドレスの後に操作名を追加した URL に対する HTTP POST 要求によって、サービス操作にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b858c-117">Also, by default service operations are accessible through HTTP POST requests to URLs that include the endpoint address followed by the operation name, as shown in the following example.</span></span>  
  
```csharp
[OperationContract]  
string[] GetCities(string firstLetters);  
```  
  
 <span data-ttu-id="b858c-118">この操作には、へ`http://serviceaddress/endpointaddress/GetCities`の HTTP POST を使用してアクセスし、XML メッセージを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b858c-118">This operation is accessible using an HTTP POST to `http://serviceaddress/endpointaddress/GetCities` and return an XML message.</span></span>  
  
 <span data-ttu-id="b858c-119">Web プログラミング モデルを活用することで、これらの基本的な部分をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="b858c-119">You can use the full Web Programming Model to customize these basic aspects.</span></span> <span data-ttu-id="b858c-120">たとえば、<xref:System.ServiceModel.Web.WebGetAttribute> 属性または <xref:System.ServiceModel.Web.WebInvokeAttribute> 属性を使用して、操作が応答する HTTP 動詞を制御したり、これらの属性の `UriTemplate` プロパティを使用して、カスタム URI を指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="b858c-120">For example, you can use the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attributes to control the HTTP verb to which the operation responds or use the `UriTemplate` property of these respective attributes to specify custom URIs.</span></span> <span data-ttu-id="b858c-121">詳細については、「 [WCF WEB HTTP プログラミングモデル](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b858c-121">For more information, see the [WCF Web HTTP Programming Model](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md) topic.</span></span>  
  
 <span data-ttu-id="b858c-122">AJAX サービスでは、JSON データ形式がよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="b858c-122">The JSON data format is often used in AJAX services.</span></span> <span data-ttu-id="b858c-123">XML ではなく JSON を返す操作を作成するには、<xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (または <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) プロパティを <xref:System.ServiceModel.Web.WebMessageFormat.Json> に設定します。</span><span class="sxs-lookup"><span data-stu-id="b858c-123">To create an operation that returns JSON instead of XML, set the <xref:System.ServiceModel.Web.WebGetAttribute.ResponseFormat%2A> (or the <xref:System.ServiceModel.Web.WebInvokeAttribute.ResponseFormat%2A>) property to <xref:System.ServiceModel.Web.WebMessageFormat.Json>.</span></span> <span data-ttu-id="b858c-124">[スタンドアロンの Json シリアル化](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)のトピックでは、組み込みの .net 型とデータコントラクト型が json にどのように対応しているかを示します。</span><span class="sxs-lookup"><span data-stu-id="b858c-124">The [Stand-Alone JSON Serialization](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md) topic shows how built-in .NET types and data contract types map to JSON.</span></span>  
  
 <span data-ttu-id="b858c-125">JSON の要求と応答は、通常 1 つの項目のみで構成されます。</span><span class="sxs-lookup"><span data-stu-id="b858c-125">Normally, JSON requests and responses consist of just one item.</span></span> <span data-ttu-id="b858c-126">前述の `GetCities` 操作の場合、要求は次のようなステートメントになります。</span><span class="sxs-lookup"><span data-stu-id="b858c-126">For the preceding `GetCities` operation, the request resembles the following statement.</span></span>  
  
```json
"na"  
```  
  
 <span data-ttu-id="b858c-127">この要求に対する応答は、次のようなステートメントになります。</span><span class="sxs-lookup"><span data-stu-id="b858c-127">The response to that request resembles the following statement.</span></span>  
  
```json
["Nairobi", "Naples", "Nashville"]  
```  
  
 <span data-ttu-id="b858c-128">操作で追加のパラメーターを受け取る場合は、両方のパラメーターを 1 つの JSON オブジェクトにラップするために、要求スタイルをラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b858c-128">If the operation takes an extra parameter, the request style must be wrapped to wrap both parameters in a single JSON object.</span></span> <span data-ttu-id="b858c-129">このスタイルの JSON メッセージの一例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b858c-129">An example of this style JSON message is in the following example.</span></span>  
  
```json  
{"firstLetters": "na", "maxNumber": 2}  
```  
  
 <span data-ttu-id="b858c-130">次のコントラクトがこのメッセージを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b858c-130">The following contract accepts this message.</span></span>  
  
```csharp
[WebInvoke(BodyStyle=WebMessageBodyStyle.WrappedRequest, ResponseFormat=WebMessageFormat.Json)]  
[OperationContract]  
string[] GetCities(string firstLetters, int maxNumber);  
```  
  
## <a name="accessing-ajax-services"></a><span data-ttu-id="b858c-131">AJAX サービスへのアクセス</span><span class="sxs-lookup"><span data-stu-id="b858c-131">Accessing AJAX Services</span></span>  
 <span data-ttu-id="b858c-132">WCF AJAX エンドポイントは、常に JSON 要求と XML 要求の両方を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="b858c-132">WCF AJAX endpoints always accept both JSON and XML requests.</span></span>  
  
 <span data-ttu-id="b858c-133">Content-type が "application/json" の HTTP POST 要求は JSON として扱われます。また、XML を示す content-type (たとえば、"text/XML") は XML として扱われます。</span><span class="sxs-lookup"><span data-stu-id="b858c-133">HTTP POST requests with a content-type of "application/json" are treated as JSON, and those with content-type that indicate XML (for example, "text/xml") are treated as XML.</span></span>  
  
 <span data-ttu-id="b858c-134">HTTP GET 要求では、URL 自体にすべての要求パラメーターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b858c-134">HTTP GET requests contain all the request parameters in the URL itself.</span></span>  
  
 <span data-ttu-id="b858c-135">エンドポイントに対して HTTP 要求を作成する方法は、ユーザーが自由に決定できます。</span><span class="sxs-lookup"><span data-stu-id="b858c-135">It is up to the user to decide how to create the HTTP request to the endpoint.</span></span> <span data-ttu-id="b858c-136">また、要求の本文を構成する JSON の作成についても、ユーザーが完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="b858c-136">Also, the user has full control over constructing the JSON that forms the body of the request.</span></span> <span data-ttu-id="b858c-137">JavaScript から要求を作成する例については、「 [JSON および XML を使用した AJAX サービス](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b858c-137">For an example of creating a request from JavaScript, see the [AJAX Service with JSON and XML](../../../../docs/framework/wcf/samples/ajax-service-with-json-and-xml-sample.md).</span></span>
