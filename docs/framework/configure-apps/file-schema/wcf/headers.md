---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855173"
---
# \<headers>
<span data-ttu-id="e8fa5-101">エンドポイントは、基本となる URI だけでなく、1 つ以上の SOAP ヘッダーによってアドレス指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="e8fa5-102">これが役に立つのは、エンドポイントのクライアントに中継局を指す SOAP ヘッダーを含める必要がある、SOAP 中継局のシナリオの場合です。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="e8fa5-103">この構成要素を使用して、カスタムのアドレス ヘッダーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="e8fa5-104">エンドポイント ヘッダー コレクション内のエントリは、ユーザー定義の XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="e8fa5-105">各要素は、正しい形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="e8fa5-106">構文</span><span class="sxs-lookup"><span data-stu-id="e8fa5-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8fa5-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8fa5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e8fa5-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8fa5-109">属性</span><span class="sxs-lookup"><span data-stu-id="e8fa5-109">Attributes</span></span>  
 <span data-ttu-id="e8fa5-110">なし。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8fa5-111">子要素</span><span class="sxs-lookup"><span data-stu-id="e8fa5-111">Child Elements</span></span>  
 <span data-ttu-id="e8fa5-112">ユーザー定義の XML 要素。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8fa5-113">親要素</span><span class="sxs-lookup"><span data-stu-id="e8fa5-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e8fa5-114">要素</span><span class="sxs-lookup"><span data-stu-id="e8fa5-114">Element</span></span>|<span data-ttu-id="e8fa5-115">説明</span><span class="sxs-lookup"><span data-stu-id="e8fa5-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="e8fa5-116">さまざまなタイプのエンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8fa5-117">解説</span><span class="sxs-lookup"><span data-stu-id="e8fa5-117">Remarks</span></span>  
 <span data-ttu-id="e8fa5-118">オプション ヘッダーは、エンドポイントの識別または対話のために、より詳細なアドレス指定情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="e8fa5-119">たとえば、ヘッダーを使用して、受信メッセージの処理方法や、エンドポイントからの応答メッセージの送信先を指定できるほか、複数のサービス インスタンスが使用できる場合に、特定ユーザーからの受信メッセージの処理に使用するインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e8fa5-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fa5-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8fa5-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="e8fa5-121">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="e8fa5-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
