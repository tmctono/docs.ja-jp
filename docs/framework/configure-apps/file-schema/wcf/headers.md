---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855173"
---
# <a name="headers"></a><span data-ttu-id="fea93-101">\<ヘッダー ></span><span class="sxs-lookup"><span data-stu-id="fea93-101">\<headers></span></span>
<span data-ttu-id="fea93-102">エンドポイントは、基本となる URI だけでなく、1 つ以上の SOAP ヘッダーによってアドレス指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fea93-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="fea93-103">これが役に立つのは、エンドポイントのクライアントに中継局を指す SOAP ヘッダーを含める必要がある、SOAP 中継局のシナリオの場合です。</span><span class="sxs-lookup"><span data-stu-id="fea93-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="fea93-104">この構成要素を使用して、カスタムのアドレス ヘッダーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="fea93-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="fea93-105">エンドポイント ヘッダー コレクション内のエントリは、ユーザー定義の XML 要素です。</span><span class="sxs-lookup"><span data-stu-id="fea93-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="fea93-106">各要素は、正しい形式の XML である必要があります。</span><span class="sxs-lookup"><span data-stu-id="fea93-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="fea93-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fea93-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fea93-108">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fea93-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fea93-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="fea93-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="fea93-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="fea93-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="fea93-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ヘッダー >**</span><span class="sxs-lookup"><span data-stu-id="fea93-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fea93-112">構文</span><span class="sxs-lookup"><span data-stu-id="fea93-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fea93-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fea93-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fea93-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fea93-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fea93-115">属性</span><span class="sxs-lookup"><span data-stu-id="fea93-115">Attributes</span></span>  
 <span data-ttu-id="fea93-116">なし。</span><span class="sxs-lookup"><span data-stu-id="fea93-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fea93-117">子要素</span><span class="sxs-lookup"><span data-stu-id="fea93-117">Child Elements</span></span>  
 <span data-ttu-id="fea93-118">ユーザー定義の XML 要素。</span><span class="sxs-lookup"><span data-stu-id="fea93-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fea93-119">親要素</span><span class="sxs-lookup"><span data-stu-id="fea93-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fea93-120">要素</span><span class="sxs-lookup"><span data-stu-id="fea93-120">Element</span></span>|<span data-ttu-id="fea93-121">説明</span><span class="sxs-lookup"><span data-stu-id="fea93-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fea93-122">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="fea93-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="fea93-123">さまざまなタイプのエンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="fea93-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fea93-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="fea93-124">Remarks</span></span>  
 <span data-ttu-id="fea93-125">オプション ヘッダーは、エンドポイントの識別または対話のために、より詳細なアドレス指定情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fea93-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="fea93-126">たとえば、ヘッダーを使用して、受信メッセージの処理方法や、エンドポイントからの応答メッセージの送信先を指定できるほか、複数のサービス インスタンスが使用できる場合に、特定ユーザーからの受信メッセージの処理に使用するインスタンスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fea93-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea93-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="fea93-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="fea93-128">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="fea93-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
