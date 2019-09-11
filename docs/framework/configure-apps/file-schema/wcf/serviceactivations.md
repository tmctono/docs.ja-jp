---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: 64ae0bfd90ae941fc78515c7936c998201c87485
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855138"
---
# <a name="serviceactivations"></a><span data-ttu-id="01b55-101">\<serviceActivations のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="01b55-101">\<serviceActivations></span></span>

<span data-ttu-id="01b55-102">Windows Communication Foundation (WCF) サービスの種類にマップする仮想サービスのアクティブ化の設定を定義する設定を追加できるようにする構成要素。</span><span class="sxs-lookup"><span data-stu-id="01b55-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="01b55-103">これにより、.svc ファイルを使用せずに、WAS/IIS でホストされているサービスをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="01b55-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="01b55-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01b55-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01b55-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="01b55-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="01b55-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="01b55-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="01b55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceActivations のアクティブ化**</span><span class="sxs-lookup"><span data-stu-id="01b55-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceActivations>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="01b55-108">構文</span><span class="sxs-lookup"><span data-stu-id="01b55-108">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="01b55-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01b55-109">Attributes and Elements</span></span>

<span data-ttu-id="01b55-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="01b55-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="01b55-111">属性</span><span class="sxs-lookup"><span data-stu-id="01b55-111">Attributes</span></span>

<span data-ttu-id="01b55-112">なし。</span><span class="sxs-lookup"><span data-stu-id="01b55-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="01b55-113">子要素</span><span class="sxs-lookup"><span data-stu-id="01b55-113">Child Elements</span></span>

|<span data-ttu-id="01b55-114">要素</span><span class="sxs-lookup"><span data-stu-id="01b55-114">Element</span></span>|<span data-ttu-id="01b55-115">説明</span><span class="sxs-lookup"><span data-stu-id="01b55-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01b55-116">\<add></span><span class="sxs-lookup"><span data-stu-id="01b55-116">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="01b55-117">サービス アプリケーションのアクティベーションを指定する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="01b55-117">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="01b55-118">親要素</span><span class="sxs-lookup"><span data-stu-id="01b55-118">Parent Elements</span></span>

|<span data-ttu-id="01b55-119">要素</span><span class="sxs-lookup"><span data-stu-id="01b55-119">Element</span></span>|<span data-ttu-id="01b55-120">説明</span><span class="sxs-lookup"><span data-stu-id="01b55-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="01b55-121">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="01b55-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="01b55-122">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="01b55-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="01b55-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="01b55-123">Remarks</span></span>

<span data-ttu-id="01b55-124">web.config ファイルでアクティベーション設定を構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="01b55-124">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="01b55-125">この構成を使用して、.svc ファイルを使用せずに、GreetingService をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="01b55-125">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="01b55-126">`<serviceHostingEnvironment>` はアプリケーション レベルの構成であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="01b55-126">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="01b55-127">構成を格納した `web.config` は、仮想アプリケーションのルートの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01b55-127">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="01b55-128">また、 `serviceHostingEnvironment`は machineToApplication 継承可能なセクションです。</span><span class="sxs-lookup"><span data-stu-id="01b55-128">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="01b55-129">コンピューターのルートに単一のサービスを登録すると、アプリケーションの各サービスはこのサービスを継承します。</span><span class="sxs-lookup"><span data-stu-id="01b55-129">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="01b55-130">構成ベースのアクティベーションは、http および非 http プロトコル経由のアクティベーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="01b55-130">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="01b55-131">これには、relativeAddress、xoml、または .xamlx の拡張機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="01b55-131">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="01b55-132">既知の buildProviders に対して独自の拡張子をマップできます。これにより、任意の拡張子を使用してサービスをアクティブ化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="01b55-132">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="01b55-133">競合が発生した場合には、`<serviceActivations>` セクションにより、.svc の登録がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="01b55-133">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="01b55-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="01b55-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
