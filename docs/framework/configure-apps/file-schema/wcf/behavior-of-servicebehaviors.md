---
title: <behavior> の <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 8c847368934cc4cd8ccaab017ede00b7b8963897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926402"
---
# <a name="behavior-of-servicebehaviors"></a><span data-ttu-id="91b36-102">\<servicebehaviors の\<動作 > ></span><span class="sxs-lookup"><span data-stu-id="91b36-102">\<behavior> of \<serviceBehaviors></span></span>
<span data-ttu-id="91b36-103">`behavior` 要素には、サービスの動作設定のコレクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="91b36-103">The `behavior` element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="91b36-104">各動作には、それぞれの `name` によってインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="91b36-104">Each behavior is indexed by its `name`.</span></span> <span data-ttu-id="91b36-105">サービスは、 `behaviorConfiguration` [ \<エンドポイント >](endpoint-element.md)要素の属性を使用して、この名前を使用して各動作にリンクできます。</span><span class="sxs-lookup"><span data-stu-id="91b36-105">Services can link to each behavior through this name using the `behaviorConfiguration` attribute of the [\<endpoint>](endpoint-element.md) element.</span></span> <span data-ttu-id="91b36-106">これにより、設定を再定義することなく、エンドポイント間で共通の動作構成を共有できます。</span><span class="sxs-lookup"><span data-stu-id="91b36-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span> <span data-ttu-id="91b36-107">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="91b36-107">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="91b36-108">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91b36-108">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91b36-109">SendMessageChannelCache > 要素など、Windows Workflow アクティビティに固有の動作要素[ \<は、servicebehaviors > ページ\<の > の動作](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)に記載されて[ \<](../windows-workflow-foundation/sendmessagechannelcache.md)います。</span><span class="sxs-lookup"><span data-stu-id="91b36-109">Behavior elements specific to Windows Workflow activities, such as the [\<sendMessageChannelCache>](../windows-workflow-foundation/sendmessagechannelcache.md) element, are documented in the [\<behavior> of \<serviceBehaviors>](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md) page.</span></span>  
  
 <span data-ttu-id="91b36-110">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="91b36-110">\<system.ServiceModel></span></span>  
<span data-ttu-id="91b36-111">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="91b36-111">\<behaviors></span></span>  
<span data-ttu-id="91b36-112">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="91b36-112">\<serviceBehaviors></span></span>  
<span data-ttu-id="91b36-113">\<behavior></span><span class="sxs-lookup"><span data-stu-id="91b36-113">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b36-114">構文</span><span class="sxs-lookup"><span data-stu-id="91b36-114">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91b36-115">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91b36-115">Attributes and Elements</span></span>  
 <span data-ttu-id="91b36-116">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91b36-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91b36-117">属性</span><span class="sxs-lookup"><span data-stu-id="91b36-117">Attributes</span></span>  
  
|<span data-ttu-id="91b36-118">属性</span><span class="sxs-lookup"><span data-stu-id="91b36-118">Attribute</span></span>|<span data-ttu-id="91b36-119">説明</span><span class="sxs-lookup"><span data-stu-id="91b36-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="91b36-120">name</span><span class="sxs-lookup"><span data-stu-id="91b36-120">name</span></span>|<span data-ttu-id="91b36-121">動作の構成名を含む一意の文字列。</span><span class="sxs-lookup"><span data-stu-id="91b36-121">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="91b36-122">この値は、要素の識別文字列として機能するため、一意のユーザー定義の文字列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="91b36-122">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span> <span data-ttu-id="91b36-123">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="91b36-123">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="91b36-124">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91b36-124">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91b36-125">子要素</span><span class="sxs-lookup"><span data-stu-id="91b36-125">Child Elements</span></span>  
  
|<span data-ttu-id="91b36-126">要素</span><span class="sxs-lookup"><span data-stu-id="91b36-126">Element</span></span>|<span data-ttu-id="91b36-127">説明</span><span class="sxs-lookup"><span data-stu-id="91b36-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91b36-128">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="91b36-128">\<dataContractSerializer></span></span>](datacontractserializer-element.md)|<span data-ttu-id="91b36-129">DataContractSerializer 用の構成データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="91b36-129">Contains configuration data for the DataContractSerializer.</span></span>|  
|[<span data-ttu-id="91b36-130">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="91b36-130">\<persistenceProvider></span></span>](persistenceprovider.md)|<span data-ttu-id="91b36-131">使用する永続化プロバイダーの実装の型と、永続化操作に使用するタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-131">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>|  
|[<span data-ttu-id="91b36-132">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="91b36-132">\<routing></span></span>](routing-of-servicebehavior.md)|<span data-ttu-id="91b36-133">ルーティング構成の動的な変更を可能にするルーティング サービスへの実行時アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="91b36-133">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>|  
|[<span data-ttu-id="91b36-134">\<serviceAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="91b36-134">\<serviceAuthenticationManager></span></span>](serviceauthenticationmanager.md)|<span data-ttu-id="91b36-135">サービス レベルで転送、メッセージ、または送信元の有効性を確立するワークフロー構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="91b36-135">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator..</span></span>|  
|[<span data-ttu-id="91b36-136">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="91b36-136">\<serviceAuthorization></span></span>](serviceauthorization-element.md)|<span data-ttu-id="91b36-137">サービス操作へのアクセスを承認する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-137">Specifies settings that authorize access to service operations.</span></span>|  
|[<span data-ttu-id="91b36-138">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="91b36-138">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="91b36-139">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-139">Specifies the credential to be used in authenticating the service and the client credential validation-related settings.</span></span>|  
|[<span data-ttu-id="91b36-140">\<serviceDebug ></span><span class="sxs-lookup"><span data-stu-id="91b36-140">\<serviceDebug></span></span>](servicedebug.md)|<span data-ttu-id="91b36-141">Windows Communication Foundation (WCF) サービスのデバッグ機能とヘルプ情報機能を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-141">Specifies debugging and help information features for a Windows Communication Foundation (WCF) service.</span></span>|  
|[<span data-ttu-id="91b36-142">\<serviceDiscovery ></span><span class="sxs-lookup"><span data-stu-id="91b36-142">\<serviceDiscovery></span></span>](servicediscovery.md)|<span data-ttu-id="91b36-143">サービス エンドポイントの探索可能性を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-143">Specifies the discoverability of service endpoints.</span></span>|  
|[<span data-ttu-id="91b36-144">\<serviceMetadata ></span><span class="sxs-lookup"><span data-stu-id="91b36-144">\<serviceMetadata></span></span>](servicemetadata.md)|<span data-ttu-id="91b36-145">サービス メタデータと関連情報の公開を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-145">Specifies the publication of service metadata and associated information.</span></span>|  
|[<span data-ttu-id="91b36-146">\<serviceSecurityAudit></span><span class="sxs-lookup"><span data-stu-id="91b36-146">\<serviceSecurityAudit></span></span>](servicesecurityaudit.md)|<span data-ttu-id="91b36-147">サービス操作中にセキュリティ イベントの監査を有効にする設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-147">Specifies settings that enable auditing of security events during service operations.</span></span>|  
|[<span data-ttu-id="91b36-148">\<serviceThrottling ></span><span class="sxs-lookup"><span data-stu-id="91b36-148">\<serviceThrottling></span></span>](servicethrottling.md)|<span data-ttu-id="91b36-149">WCF サービスの制限メカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-149">Specifies the throttling mechanism of a WCF service.</span></span>|  
|[<span data-ttu-id="91b36-150">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="91b36-150">\<serviceTimeouts></span></span>](servicetimeouts.md)|<span data-ttu-id="91b36-151">サービスのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-151">Specifies the timeout for a service.</span></span>|  
|[<span data-ttu-id="91b36-152">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="91b36-152">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="91b36-153">ワークフローベースの WCF サービスをホストするための WorkflowRuntime のインスタンスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="91b36-153">Specifies settings for an instance of WorkflowRuntime for hosting workflow-based WCF services.</span></span>|  
|[<span data-ttu-id="91b36-154">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="91b36-154">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="91b36-155">メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="91b36-155">Enables the retrieval of metadata address information from the request message headers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91b36-156">親要素</span><span class="sxs-lookup"><span data-stu-id="91b36-156">Parent Elements</span></span>  
  
|<span data-ttu-id="91b36-157">要素</span><span class="sxs-lookup"><span data-stu-id="91b36-157">Element</span></span>|<span data-ttu-id="91b36-158">説明</span><span class="sxs-lookup"><span data-stu-id="91b36-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91b36-159">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="91b36-159">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="91b36-160">サービス動作要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="91b36-160">A collection of service behavior elements.</span></span>|
