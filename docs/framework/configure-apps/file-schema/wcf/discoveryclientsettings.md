---
title: <discoveryClientSettings>
ms.date: 03/30/2017
ms.assetid: 02e1b823-a8bb-4074-90d5-8599f71e8f9d
ms.openlocfilehash: 6e3f273af807eb362f005fef63246013ecc88581
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192244"
---
# \<discoveryClientSettings>

<span data-ttu-id="b4cd3-101">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-101">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<discoveryClientSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="b4cd3-102">構文</span><span class="sxs-lookup"><span data-stu-id="b4cd3-102">Syntax</span></span>  
  
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
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4cd3-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b4cd3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="b4cd3-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4cd3-105">属性</span><span class="sxs-lookup"><span data-stu-id="b4cd3-105">Attributes</span></span>  
  
|<span data-ttu-id="b4cd3-106">属性</span><span class="sxs-lookup"><span data-stu-id="b4cd3-106">Attribute</span></span>|<span data-ttu-id="b4cd3-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="b4cd3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b4cd3-108">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="b4cd3-108">discoveryEndpoint</span></span>|<span data-ttu-id="b4cd3-109">クライアント アプリケーションが実行時に探索可能なサービスを自動的に検索し、そのアドレスを見つけることができる探索エンドポイントの名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-109">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4cd3-110">子要素</span><span class="sxs-lookup"><span data-stu-id="b4cd3-110">Child Elements</span></span>  
  
|<span data-ttu-id="b4cd3-111">要素</span><span class="sxs-lookup"><span data-stu-id="b4cd3-111">Element</span></span>|<span data-ttu-id="b4cd3-112">説明</span><span class="sxs-lookup"><span data-stu-id="b4cd3-112">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="b4cd3-113">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-113">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="b4cd3-114">基準は、(探しているサービスを指定する) 検索条件と (検索をどのくらい続けるかを指定する) 検索終了条件にグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-114">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b4cd3-115">親要素</span><span class="sxs-lookup"><span data-stu-id="b4cd3-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b4cd3-116">要素</span><span class="sxs-lookup"><span data-stu-id="b4cd3-116">Element</span></span>|<span data-ttu-id="b4cd3-117">説明</span><span class="sxs-lookup"><span data-stu-id="b4cd3-117">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="b4cd3-118">アプリケーションが実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="b4cd3-118">Defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4cd3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4cd3-119">See also</span></span>

- <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>
- <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientSettingsElement>
