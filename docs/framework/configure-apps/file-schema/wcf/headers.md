---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: a982fa87ab84725e36ee913f00200cd34f0b8f6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925576"
---
# <a name="headers"></a><span data-ttu-id="cfc26-101">\<ヘッダー ></span><span class="sxs-lookup"><span data-stu-id="cfc26-101">\<headers></span></span>
<span data-ttu-id="cfc26-102">エンドポイントは、基本となる URI だけでなく、1 つ以上の SOAP ヘッダーによってアドレス指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfc26-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="cfc26-103">これが役に立つのは、エンドポイントのクライアントに中継局を指す SOAP ヘッダーを含める必要がある、SOAP 中継局のシナリオの場合です。</span><span class="sxs-lookup"><span data-stu-id="cfc26-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="cfc26-104">この構成要素を使用して、カスタムのアドレス ヘッダーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="cfc26-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="cfc26-105">エンドポイント ヘッダー コレクション内のエントリは、ユーザー定義の XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="cfc26-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="cfc26-106">各要素は、正しい形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfc26-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="cfc26-107">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cfc26-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="cfc26-108">\<client></span><span class="sxs-lookup"><span data-stu-id="cfc26-108">\<client></span></span>  
<span data-ttu-id="cfc26-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="cfc26-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc26-110">構文</span><span class="sxs-lookup"><span data-stu-id="cfc26-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfc26-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cfc26-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cfc26-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfc26-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfc26-113">属性</span><span class="sxs-lookup"><span data-stu-id="cfc26-113">Attributes</span></span>  
 <span data-ttu-id="cfc26-114">なし。</span><span class="sxs-lookup"><span data-stu-id="cfc26-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cfc26-115">子要素</span><span class="sxs-lookup"><span data-stu-id="cfc26-115">Child Elements</span></span>  
 <span data-ttu-id="cfc26-116">ユーザー定義の XML 要素。</span><span class="sxs-lookup"><span data-stu-id="cfc26-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfc26-117">親要素</span><span class="sxs-lookup"><span data-stu-id="cfc26-117">Parent Elements</span></span>  
  
|<span data-ttu-id="cfc26-118">要素</span><span class="sxs-lookup"><span data-stu-id="cfc26-118">Element</span></span>|<span data-ttu-id="cfc26-119">説明</span><span class="sxs-lookup"><span data-stu-id="cfc26-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfc26-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="cfc26-120">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="cfc26-121">さまざまなタイプのエンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="cfc26-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfc26-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="cfc26-122">Remarks</span></span>  
 <span data-ttu-id="cfc26-123">オプション ヘッダーは、エンドポイントの識別または対話のために、より詳細なアドレス指定情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cfc26-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="cfc26-124">たとえば、ヘッダーを使用して、受信メッセージの処理方法や、エンドポイントからの応答メッセージの送信先を指定できるほか、複数のサービス インスタンスが使用できる場合に、特定ユーザーからの受信メッセージの処理に使用するインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfc26-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfc26-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfc26-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="cfc26-126">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="cfc26-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
