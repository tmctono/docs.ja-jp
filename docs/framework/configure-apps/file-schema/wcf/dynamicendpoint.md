---
title: <dynamicEndpoint>
ms.date: 03/30/2017
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
ms.openlocfilehash: da57ca3ba3bc0036727a749f1cab9ec3657a4fda
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855344"
---
# <a name="dynamicendpoint"></a><span data-ttu-id="5328b-101">\<dynamicEndpoint ></span><span class="sxs-lookup"><span data-stu-id="5328b-101">\<dynamicEndpoint></span></span>
<span data-ttu-id="5328b-102">この構成要素は、アプリケーションが、実行時に動的にエンドポイント アドレスを検索するクライアント プログラムとして機能するための情報を格納する標準エンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="5328b-102">This configuration element defines a standard endpoint that contains information to enable an application to function as a client program that can find the endpoint address dynamically at runtime.</span></span>  
  
<span data-ttu-id="5328b-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5328b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5328b-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5328b-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5328b-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="5328b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="5328b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dynamicEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="5328b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dynamicEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5328b-107">構文</span><span class="sxs-lookup"><span data-stu-id="5328b-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5328b-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5328b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5328b-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5328b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5328b-110">属性</span><span class="sxs-lookup"><span data-stu-id="5328b-110">Attributes</span></span>  
 <span data-ttu-id="5328b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="5328b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5328b-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5328b-112">Child Elements</span></span>  
  
|<span data-ttu-id="5328b-113">要素</span><span class="sxs-lookup"><span data-stu-id="5328b-113">Element</span></span>|<span data-ttu-id="5328b-114">説明</span><span class="sxs-lookup"><span data-stu-id="5328b-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5328b-115">\<discoveryClientSettings></span><span class="sxs-lookup"><span data-stu-id="5328b-115">\<discoveryClientSettings></span></span>](discoveryclientsettings.md)|<span data-ttu-id="5328b-116">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="5328b-116">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5328b-117">親要素</span><span class="sxs-lookup"><span data-stu-id="5328b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5328b-118">要素</span><span class="sxs-lookup"><span data-stu-id="5328b-118">Element</span></span>|<span data-ttu-id="5328b-119">説明</span><span class="sxs-lookup"><span data-stu-id="5328b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5328b-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5328b-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="5328b-121">1 つ以上のプロパティ (アドレス、バインディング、コントラクト) が固定されている、あらかじめ定義されたエンドポイントである標準エンドポイントのコレクション。</span><span class="sxs-lookup"><span data-stu-id="5328b-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5328b-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="5328b-122">See also</span></span>

- <xref:System.ServiceModel.Discovery.DynamicEndpoint>
- <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
