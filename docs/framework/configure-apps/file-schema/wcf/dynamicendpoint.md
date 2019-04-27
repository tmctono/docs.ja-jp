---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: e1a53869faa1997d2e79c3d2869a15001ee29626
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673161"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="c61b7-101">\<dynamicEndpoint></span><span class="sxs-lookup"><span data-stu-id="c61b7-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="c61b7-102">この構成要素は、アプリケーションが、実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="c61b7-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="c61b7-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c61b7-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c61b7-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c61b7-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61b7-105">構文</span><span class="sxs-lookup"><span data-stu-id="c61b7-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c61b7-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c61b7-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c61b7-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c61b7-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c61b7-108">属性</span><span class="sxs-lookup"><span data-stu-id="c61b7-108">Attributes</span></span>  
 <span data-ttu-id="c61b7-109">なし。</span><span class="sxs-lookup"><span data-stu-id="c61b7-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c61b7-110">子要素</span><span class="sxs-lookup"><span data-stu-id="c61b7-110">Child Elements</span></span>  
  
|<span data-ttu-id="c61b7-111">要素</span><span class="sxs-lookup"><span data-stu-id="c61b7-111">Element</span></span>|<span data-ttu-id="c61b7-112">説明</span><span class="sxs-lookup"><span data-stu-id="c61b7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61b7-113">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="c61b7-113">\<discoveryClientSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|<span data-ttu-id="c61b7-114">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="c61b7-114">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c61b7-115">親要素</span><span class="sxs-lookup"><span data-stu-id="c61b7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c61b7-116">要素</span><span class="sxs-lookup"><span data-stu-id="c61b7-116">Element</span></span>|<span data-ttu-id="c61b7-117">説明</span><span class="sxs-lookup"><span data-stu-id="c61b7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c61b7-118">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c61b7-118">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="c61b7-119">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="c61b7-119">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c61b7-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c61b7-120">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
