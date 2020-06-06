---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855344"
---
# \<dynamicEndpoint>
<span data-ttu-id="126bd-101">この構成要素は、アプリケーションが、実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="126bd-101">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="126bd-102">構文</span><span class="sxs-lookup"><span data-stu-id="126bd-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="126bd-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="126bd-103">Attributes and Elements</span></span>  
 <span data-ttu-id="126bd-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="126bd-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="126bd-105">属性</span><span class="sxs-lookup"><span data-stu-id="126bd-105">Attributes</span></span>  
 <span data-ttu-id="126bd-106">なし。</span><span class="sxs-lookup"><span data-stu-id="126bd-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="126bd-107">子要素</span><span class="sxs-lookup"><span data-stu-id="126bd-107">Child Elements</span></span>  
  
|<span data-ttu-id="126bd-108">要素</span><span class="sxs-lookup"><span data-stu-id="126bd-108">Element</span></span>|<span data-ttu-id="126bd-109">説明</span><span class="sxs-lookup"><span data-stu-id="126bd-109">Description</span></span>|  
|-------------|-----------------|  
|[\<discoveryClientSettings>](discoveryclientsettings.md)|<span data-ttu-id="126bd-110">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="126bd-110">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="126bd-111">親要素</span><span class="sxs-lookup"><span data-stu-id="126bd-111">Parent Elements</span></span>  
  
|<span data-ttu-id="126bd-112">要素</span><span class="sxs-lookup"><span data-stu-id="126bd-112">Element</span></span>|<span data-ttu-id="126bd-113">説明</span><span class="sxs-lookup"><span data-stu-id="126bd-113">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="126bd-114">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="126bd-114">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="126bd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="126bd-115">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
