---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855138"
---
# \<serviceActivations>

<span data-ttu-id="e41a7-101">Windows Communication Foundation (WCF) サービスの種類にマップする仮想サービスのアクティブ化の設定を定義する設定を追加できるようにする構成要素。</span><span class="sxs-lookup"><span data-stu-id="e41a7-101">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="e41a7-102">これにより、.svc ファイルを使用せずに、WAS/IIS でホストされているサービスをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="e41a7-102">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**  

## <a name="syntax"></a><span data-ttu-id="e41a7-103">構文</span><span class="sxs-lookup"><span data-stu-id="e41a7-103">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e41a7-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e41a7-104">Attributes and Elements</span></span>

<span data-ttu-id="e41a7-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e41a7-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="e41a7-106">属性</span><span class="sxs-lookup"><span data-stu-id="e41a7-106">Attributes</span></span>

<span data-ttu-id="e41a7-107">なし。</span><span class="sxs-lookup"><span data-stu-id="e41a7-107">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e41a7-108">子要素</span><span class="sxs-lookup"><span data-stu-id="e41a7-108">Child Elements</span></span>

|<span data-ttu-id="e41a7-109">要素</span><span class="sxs-lookup"><span data-stu-id="e41a7-109">Element</span></span>|<span data-ttu-id="e41a7-110">説明</span><span class="sxs-lookup"><span data-stu-id="e41a7-110">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-serviceactivations.md)|<span data-ttu-id="e41a7-111">サービス アプリケーションのアクティベーションを指定する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="e41a7-111">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e41a7-112">親要素</span><span class="sxs-lookup"><span data-stu-id="e41a7-112">Parent Elements</span></span>

|<span data-ttu-id="e41a7-113">要素</span><span class="sxs-lookup"><span data-stu-id="e41a7-113">Element</span></span>|<span data-ttu-id="e41a7-114">説明</span><span class="sxs-lookup"><span data-stu-id="e41a7-114">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="e41a7-115">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="e41a7-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e41a7-116">解説</span><span class="sxs-lookup"><span data-stu-id="e41a7-116">Remarks</span></span>

<span data-ttu-id="e41a7-117">web.config ファイルでアクティベーション設定を構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="e41a7-117">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="e41a7-118">この構成を使用して、.svc ファイルを使用せずに、GreetingService をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="e41a7-118">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="e41a7-119">`<serviceHostingEnvironment>` はアプリケーション レベルの構成であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e41a7-119">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="e41a7-120">構成を格納した `web.config` は、仮想アプリケーションのルートの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e41a7-120">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="e41a7-121">また、 `serviceHostingEnvironment` は machineToApplication 継承可能なセクションです。</span><span class="sxs-lookup"><span data-stu-id="e41a7-121">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="e41a7-122">コンピューターのルートに単一のサービスを登録すると、アプリケーションの各サービスはこのサービスを継承します。</span><span class="sxs-lookup"><span data-stu-id="e41a7-122">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="e41a7-123">構成ベースのアクティベーションは、http および非 http プロトコル経由のアクティベーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="e41a7-123">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="e41a7-124">これには、relativeAddress、xoml、または .xamlx の拡張機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="e41a7-124">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="e41a7-125">既知の buildProviders に対して独自の拡張子をマップできます。これにより、任意の拡張子を使用してサービスをアクティブ化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e41a7-125">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="e41a7-126">競合が発生した場合には、`<serviceActivations>` セクションにより、.svc の登録がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="e41a7-126">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="e41a7-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e41a7-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
