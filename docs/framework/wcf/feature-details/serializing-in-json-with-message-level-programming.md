---
title: メッセージ レベルのプログラミングによる JSON 形式でのシリアル化
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 7576594f8fa694ce2d34cf38c88d2e28a00f5295
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991133"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="1024f-102">メッセージ レベルのプログラミングによる JSON 形式でのシリアル化</span><span class="sxs-lookup"><span data-stu-id="1024f-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="1024f-103">WCF は、JSON 形式でのデータのシリアル化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1024f-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="1024f-104">このトピックでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を使用して型をシリアル化することを WCF に命令する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1024f-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="1024f-105">型指定されたメッセージのプログラミング</span><span class="sxs-lookup"><span data-stu-id="1024f-105">Typed Message Programming</span></span>  
 <span data-ttu-id="1024f-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> は、<xref:System.ServiceModel.Web.WebGetAttribute> または <xref:System.ServiceModel.Web.WebInvokeAttribute> がサービス操作に適用されるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1024f-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="1024f-107">どちらの属性でも、`RequestFormat` と `ResponseFormat` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1024f-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="1024f-108">要求と応答に JSON を使用する場合。</span><span class="sxs-lookup"><span data-stu-id="1024f-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="1024f-109">両方をに`WebMessageFormat.Json`設定します。</span><span class="sxs-lookup"><span data-stu-id="1024f-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="1024f-110">JSON を使用するには、を使用<xref:System.ServiceModel.WebHttpBinding>する必要があり<xref:System.ServiceModel.Description.WebHttpBehavior>ます。これにより、が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="1024f-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="1024f-111">WCF シリアル化の詳細については、「[シリアル化と逆シリアル](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)化」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1024f-111">For more information about WCF serialization, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span> <span data-ttu-id="1024f-112">JSON と WCF の詳細については、「[サービスステーション-wcf を使用した RESTful サービスの概要](https://msdn.microsoft.com/magazine/dd315413.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1024f-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](https://msdn.microsoft.com/magazine/dd315413.aspx).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1024f-113">JSON を使用するには、SOAP 通信をサポートしていない <xref:System.ServiceModel.WebHttpBinding> と <xref:System.ServiceModel.Description.WebHttpBehavior> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1024f-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="1024f-114">と通信するサービスは<xref:System.ServiceModel.WebHttpBinding> 、サービスメタデータの公開をサポートしていないため、クライアント側プロキシを生成するために Visual Studio のサービス参照の追加機能または svcutil.exe コマンドラインツールを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1024f-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="1024f-115">を使用<xref:System.ServiceModel.WebHttpBinding>するサービスをプログラムで呼び出す方法の詳細については、「 [WCF で REST サービスを使用する方法](https://blogs.msdn.microsoft.com/pedram/2008/04/21/how-to-consume-rest-services-with-wcf/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1024f-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](https://blogs.msdn.microsoft.com/pedram/2008/04/21/how-to-consume-rest-services-with-wcf/).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="1024f-116">型指定されていないメッセージのプログラミング</span><span class="sxs-lookup"><span data-stu-id="1024f-116">Untyped Message Programming</span></span>  
 <span data-ttu-id="1024f-117">型指定されていないメッセージ オブジェクトを直接操作する場合は、型指定されていないメッセージのプロパティを明示的に設定して JSON としてシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1024f-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="1024f-118">これを行う方法を次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="1024f-118">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,   
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="1024f-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1024f-119">See also</span></span>

- [<span data-ttu-id="1024f-120">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="1024f-120">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="1024f-121">スタンドアロン JSON のシリアル化</span><span class="sxs-lookup"><span data-stu-id="1024f-121">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="1024f-122">JSON シリアル化</span><span class="sxs-lookup"><span data-stu-id="1024f-122">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
