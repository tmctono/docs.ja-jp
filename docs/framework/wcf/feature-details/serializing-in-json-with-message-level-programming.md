---
title: メッセージ レベルのプログラミングによる JSON 形式でのシリアル化
ms.date: 03/30/2017
ms.assetid: 5f940ba2-57ee-4c49-a779-957c5e7e71fa
ms.openlocfilehash: 36459dbc0ddee883678a98a27f9abb74fde78e86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184494"
---
# <a name="serializing-in-json-with-message-level-programming"></a><span data-ttu-id="1a53a-102">メッセージ レベルのプログラミングによる JSON 形式でのシリアル化</span><span class="sxs-lookup"><span data-stu-id="1a53a-102">Serializing in Json with Message Level Programming</span></span>
<span data-ttu-id="1a53a-103">WCF は、JSON 形式でのデータのシリアル化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="1a53a-103">WCF supports serializing data in JSON format.</span></span> <span data-ttu-id="1a53a-104">このトピックでは、<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> を使用して型をシリアル化することを WCF に命令する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a53a-104">This topic describes how to tell WCF to serialize your types using the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="typed-message-programming"></a><span data-ttu-id="1a53a-105">型指定されたメッセージのプログラミング</span><span class="sxs-lookup"><span data-stu-id="1a53a-105">Typed Message Programming</span></span>  
 <span data-ttu-id="1a53a-106"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> は、<xref:System.ServiceModel.Web.WebGetAttribute> または <xref:System.ServiceModel.Web.WebInvokeAttribute> がサービス操作に適用されるときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a53a-106">The <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> is used when the <xref:System.ServiceModel.Web.WebGetAttribute> or the <xref:System.ServiceModel.Web.WebInvokeAttribute> is applied to a service operation.</span></span> <span data-ttu-id="1a53a-107">どちらの属性でも、`RequestFormat` と `ResponseFormat` を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a53a-107">Both of these attributes allow you to specify the `RequestFormat` and `ResponseFormat`.</span></span> <span data-ttu-id="1a53a-108">要求と応答に JSON を使用する。</span><span class="sxs-lookup"><span data-stu-id="1a53a-108">To use JSON for requests and responses.</span></span> <span data-ttu-id="1a53a-109">両方を`WebMessageFormat.Json`に設定します。</span><span class="sxs-lookup"><span data-stu-id="1a53a-109">set both of these to `WebMessageFormat.Json`.</span></span>  <span data-ttu-id="1a53a-110">JSON を使用するには、 を<xref:System.ServiceModel.WebHttpBinding>使用する必要があります。 <xref:System.ServiceModel.Description.WebHttpBehavior></span><span class="sxs-lookup"><span data-stu-id="1a53a-110">In order to use JSON, you must use the <xref:System.ServiceModel.WebHttpBinding>, which automatically configures the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span> <span data-ttu-id="1a53a-111">WCF シリアル化の詳細については、「[シリアル化と逆シリアル化](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a53a-111">For more information about WCF serialization, see [Serialization and Deserialization](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md).</span></span> <span data-ttu-id="1a53a-112">JSON と WCF の詳細については、「 サービス ステーション - WCF を[使用した RESTful サービスの概要](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a53a-112">For more information about JSON and WCF, see [Service Station - An Introduction To RESTful Services With WCF](https://docs.microsoft.com/archive/msdn-magazine/2009/january/service-station-an-introduction-to-restful-services-with-wcf).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a53a-113">JSON を使用するには、SOAP 通信をサポートしていない <xref:System.ServiceModel.WebHttpBinding> と <xref:System.ServiceModel.Description.WebHttpBehavior> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a53a-113">Using JSON requires use of <xref:System.ServiceModel.WebHttpBinding> and <xref:System.ServiceModel.Description.WebHttpBehavior> which do not support SOAP communication.</span></span> <span data-ttu-id="1a53a-114">と通信するサービスは<xref:System.ServiceModel.WebHttpBinding>サービス メタデータの公開をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="1a53a-114">Services that communicate with the <xref:System.ServiceModel.WebHttpBinding> do not support exposing service metadata so you will not be able to use Visual Studio’s Add Service Reference functionality or the svcutil command-line tool to generate a client-side proxy.</span></span> <span data-ttu-id="1a53a-115">を使用<xref:System.ServiceModel.WebHttpBinding>するサービスをプログラムで呼び出す方法の詳細については、「 [WCF で REST サービスを使用する方法](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a53a-115">For more information how you can programmatically call services that use <xref:System.ServiceModel.WebHttpBinding>, see [How to Consume REST Services with WCF](https://docs.microsoft.com/archive/blogs/pedram/how-to-consume-rest-services-with-wcf).</span></span>  
  
## <a name="untyped-message-programming"></a><span data-ttu-id="1a53a-116">型指定されていないメッセージのプログラミング</span><span class="sxs-lookup"><span data-stu-id="1a53a-116">Untyped Message Programming</span></span>  
 <span data-ttu-id="1a53a-117">型指定されていないメッセージ オブジェクトを直接操作する場合は、型指定されていないメッセージのプロパティを明示的に設定して JSON としてシリアル化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a53a-117">When working directly with untyped Message objects, you must explicitly set the properties on the untyped message to serialize it as JSON.</span></span> <span data-ttu-id="1a53a-118">これを行う方法を次のコード スニペットに示します。</span><span class="sxs-lookup"><span data-stu-id="1a53a-118">The following code snippet shows how to do this.</span></span>  
  
```csharp
 Message response = Message.CreateMessage(  
                  MessageVersion.None,    // No SOAP message version  
                             "*",                     // SOAP action, ignored since this is JSON  
                             "Response string: JSON format specified", // Message body  
                             new DataContractJsonSerializer(typeof(string))); // Specify DataContractJsonSerializer  
      response.Properties.Add( WebBodyFormatMessageProperty.Name,
                    new WebBodyFormatMessageProperty(WebContentFormat.Json)); // Use JSON format  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a53a-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a53a-119">See also</span></span>

- [<span data-ttu-id="1a53a-120">AJAX の統合と JSON のサポート</span><span class="sxs-lookup"><span data-stu-id="1a53a-120">AJAX Integration and JSON Support</span></span>](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md)
- [<span data-ttu-id="1a53a-121">スタンドアロン JSON のシリアル化</span><span class="sxs-lookup"><span data-stu-id="1a53a-121">Stand-Alone JSON Serialization</span></span>](../../../../docs/framework/wcf/feature-details/stand-alone-json-serialization.md)
- [<span data-ttu-id="1a53a-122">JSON シリアル化</span><span class="sxs-lookup"><span data-stu-id="1a53a-122">JSON Serialization</span></span>](../../../../docs/framework/wcf/samples/json-serialization.md)
