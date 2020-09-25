---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: 6f9cb127deb5651ed27a0ef5802512fb5b6c7b54
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190099"
---
# \<dynamicEndpoint>

<span data-ttu-id="220b2-101">この構成要素は、アプリケーションが、実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="220b2-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="220b2-102">構文</span><span class="sxs-lookup"><span data-stu-id="220b2-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="220b2-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="220b2-103">Attributes and Elements</span></span>  

 <span data-ttu-id="220b2-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="220b2-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="220b2-105">属性</span><span class="sxs-lookup"><span data-stu-id="220b2-105">Attributes</span></span>  

 <span data-ttu-id="220b2-106">なし。</span><span class="sxs-lookup"><span data-stu-id="220b2-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="220b2-107">子要素</span><span class="sxs-lookup"><span data-stu-id="220b2-107">Child Elements</span></span>  
  
|<span data-ttu-id="220b2-108">要素</span><span class="sxs-lookup"><span data-stu-id="220b2-108">Element</span></span>|<span data-ttu-id="220b2-109">説明</span><span class="sxs-lookup"><span data-stu-id="220b2-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="220b2-110">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="220b2-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="220b2-111">親要素</span><span class="sxs-lookup"><span data-stu-id="220b2-111">Parent Elements</span></span>  
  
|<span data-ttu-id="220b2-112">要素</span><span class="sxs-lookup"><span data-stu-id="220b2-112">Element</span></span>|<span data-ttu-id="220b2-113">説明</span><span class="sxs-lookup"><span data-stu-id="220b2-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="220b2-114">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="220b2-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="220b2-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="220b2-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
