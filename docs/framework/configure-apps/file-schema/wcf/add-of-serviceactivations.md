---
title: <add> の <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850332"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="fbbb9-102">\<add> の \<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="fbbb9-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="fbbb9-103">Windows Communication Foundation (WCF) サービスの種類にマップする仮想サービスのアクティブ化の設定を定義できるようにする構成要素。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="fbbb9-104">これにより、.svc ファイルを使用せずに、WAS/IIS でホストされているサービスをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="fbbb9-105">構文</span><span class="sxs-lookup"><span data-stu-id="fbbb9-105">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="fbbb9-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fbbb9-106">Attributes and Elements</span></span>

<span data-ttu-id="fbbb9-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="fbbb9-108">属性</span><span class="sxs-lookup"><span data-stu-id="fbbb9-108">Attributes</span></span>

|<span data-ttu-id="fbbb9-109">属性</span><span class="sxs-lookup"><span data-stu-id="fbbb9-109">Attribute</span></span>|<span data-ttu-id="fbbb9-110">説明</span><span class="sxs-lookup"><span data-stu-id="fbbb9-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="fbbb9-111">factory</span><span class="sxs-lookup"><span data-stu-id="fbbb9-111">factory</span></span>|<span data-ttu-id="fbbb9-112">サービス アクティベーション要素を生成するファクトリの CLR 型名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-112">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="fbbb9-113">サービス (service)</span><span class="sxs-lookup"><span data-stu-id="fbbb9-113">service</span></span>|<span data-ttu-id="fbbb9-114">サービスを実装する ServiceType (完全修飾 Typename または省略形の Typename (App_Code フォルダーに配置されている場合))。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-114">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="fbbb9-115">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="fbbb9-115">relativeAddress</span></span>|<span data-ttu-id="fbbb9-116">現在の IIS アプリケーション内の相対アドレス (たとえば "Service.svc")。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-116">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="fbbb9-117">WCF 4.0 では、この相対アドレスには既知のファイル拡張子 (.svc、.xamlx、...) のいずれかが含まれている必要があります。RelativeUrl の物理ファイルが存在しません</span><span class="sxs-lookup"><span data-stu-id="fbbb9-117">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fbbb9-118">子要素</span><span class="sxs-lookup"><span data-stu-id="fbbb9-118">Child Elements</span></span>

<span data-ttu-id="fbbb9-119">なし。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fbbb9-120">親要素</span><span class="sxs-lookup"><span data-stu-id="fbbb9-120">Parent Elements</span></span>

|<span data-ttu-id="fbbb9-121">要素</span><span class="sxs-lookup"><span data-stu-id="fbbb9-121">Element</span></span>|<span data-ttu-id="fbbb9-122">Description</span><span class="sxs-lookup"><span data-stu-id="fbbb9-122">Description</span></span>|
|-------------|-----------------|
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="fbbb9-123">アクティベーション設定を記述する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-123">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="fbbb9-124">解説</span><span class="sxs-lookup"><span data-stu-id="fbbb9-124">Remarks</span></span>

<span data-ttu-id="fbbb9-125">web.config ファイルでアクティベーション設定を構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-125">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="fbbb9-126">この構成を使用して、.svc ファイルを使用せずに、GreetingService をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-126">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="fbbb9-127">`<serviceHostingEnvironment>` はアプリケーション レベルの構成であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-127">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="fbbb9-128">構成を格納した `web.config` は、仮想アプリケーションのルートの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-128">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="fbbb9-129">また、 `serviceHostingEnvironment` は machineToApplication 継承可能なセクションです。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-129">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="fbbb9-130">コンピューターのルートに単一のサービスを登録すると、アプリケーションの各サービスはこのサービスを継承します。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-130">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="fbbb9-131">構成ベースのアクティベーションは、http および非 http プロトコル経由のアクティベーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-131">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="fbbb9-132">RelativeAddress の拡張機能、つまり .svc、xoml、または .xamlx が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-132">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="fbbb9-133">既知の buildProviders に対して独自の拡張子をマップできます。これにより、任意の拡張子を使用してサービスをアクティブ化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-133">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="fbbb9-134">競合が発生した場合には、`<serviceActivations>` セクションにより、.svc の登録がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="fbbb9-134">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbbb9-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbbb9-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
