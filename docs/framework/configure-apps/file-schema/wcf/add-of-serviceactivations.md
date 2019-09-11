---
title: <add> の <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: a0f68717f765482f53e675458fae63d1a374d6fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850332"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="25a5c-102">\<serviceactivations の\<アクティブ化の追加 ></span><span class="sxs-lookup"><span data-stu-id="25a5c-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="25a5c-103">Windows Communication Foundation (WCF) サービスの種類にマップする仮想サービスのアクティブ化の設定を定義できるようにする構成要素。</span><span class="sxs-lookup"><span data-stu-id="25a5c-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="25a5c-104">これにより、.svc ファイルを使用せずに、WAS/IIS でホストされているサービスをアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="25a5c-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="25a5c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25a5c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25a5c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="25a5c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25a5c-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="25a5c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="25a5c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceActivations のアクティブ化**](serviceactivations.md)</span><span class="sxs-lookup"><span data-stu-id="25a5c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceActivations>**](serviceactivations.md)</span></span>\
<span data-ttu-id="25a5c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="25a5c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="25a5c-110">構文</span><span class="sxs-lookup"><span data-stu-id="25a5c-110">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="25a5c-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="25a5c-111">Attributes and Elements</span></span>

<span data-ttu-id="25a5c-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="25a5c-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="25a5c-113">属性</span><span class="sxs-lookup"><span data-stu-id="25a5c-113">Attributes</span></span>

|<span data-ttu-id="25a5c-114">属性</span><span class="sxs-lookup"><span data-stu-id="25a5c-114">Attribute</span></span>|<span data-ttu-id="25a5c-115">説明</span><span class="sxs-lookup"><span data-stu-id="25a5c-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="25a5c-116">factory</span><span class="sxs-lookup"><span data-stu-id="25a5c-116">factory</span></span>|<span data-ttu-id="25a5c-117">サービス アクティベーション要素を生成するファクトリの CLR 型名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="25a5c-117">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="25a5c-118">サービス</span><span class="sxs-lookup"><span data-stu-id="25a5c-118">service</span></span>|<span data-ttu-id="25a5c-119">サービスを実装する ServiceType (完全修飾 Typename または省略形の Typename (App_Code フォルダーに配置されている場合))。</span><span class="sxs-lookup"><span data-stu-id="25a5c-119">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="25a5c-120">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="25a5c-120">relativeAddress</span></span>|<span data-ttu-id="25a5c-121">現在の IIS アプリケーション内の相対アドレス (たとえば "Service.svc")。</span><span class="sxs-lookup"><span data-stu-id="25a5c-121">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="25a5c-122">WCF 4.0 ではこの相対アドレスが 1 個の既知のファイル拡張子 (.svc、.xamlx など) を含む必要があります。relativeUrl 用の物理ファイルは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="25a5c-122">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="25a5c-123">子要素</span><span class="sxs-lookup"><span data-stu-id="25a5c-123">Child Elements</span></span>

<span data-ttu-id="25a5c-124">なし。</span><span class="sxs-lookup"><span data-stu-id="25a5c-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="25a5c-125">親要素</span><span class="sxs-lookup"><span data-stu-id="25a5c-125">Parent Elements</span></span>

|<span data-ttu-id="25a5c-126">要素</span><span class="sxs-lookup"><span data-stu-id="25a5c-126">Element</span></span>|<span data-ttu-id="25a5c-127">説明</span><span class="sxs-lookup"><span data-stu-id="25a5c-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25a5c-128">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="25a5c-128">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="25a5c-129">アクティベーション設定を記述する構成セクション。</span><span class="sxs-lookup"><span data-stu-id="25a5c-129">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="25a5c-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="25a5c-130">Remarks</span></span>

<span data-ttu-id="25a5c-131">web.config ファイルでアクティベーション設定を構成する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="25a5c-131">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="25a5c-132">この構成を使用して、.svc ファイルを使用せずに、GreetingService をアクティブ化できます。</span><span class="sxs-lookup"><span data-stu-id="25a5c-132">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="25a5c-133">`<serviceHostingEnvironment>` はアプリケーション レベルの構成であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="25a5c-133">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="25a5c-134">構成を格納した `web.config` は、仮想アプリケーションのルートの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25a5c-134">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="25a5c-135">また、 `serviceHostingEnvironment`は machineToApplication 継承可能なセクションです。</span><span class="sxs-lookup"><span data-stu-id="25a5c-135">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="25a5c-136">コンピューターのルートに単一のサービスを登録すると、アプリケーションの各サービスはこのサービスを継承します。</span><span class="sxs-lookup"><span data-stu-id="25a5c-136">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="25a5c-137">構成ベースのアクティベーションは、http および非 http プロトコル経由のアクティベーションをサポートします。</span><span class="sxs-lookup"><span data-stu-id="25a5c-137">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="25a5c-138">RelativeAddress の拡張機能、つまり .svc、xoml、または .xamlx が必要です。</span><span class="sxs-lookup"><span data-stu-id="25a5c-138">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="25a5c-139">既知の buildProviders に対して独自の拡張子をマップできます。これにより、任意の拡張子を使用してサービスをアクティブ化できるようになります。</span><span class="sxs-lookup"><span data-stu-id="25a5c-139">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="25a5c-140">競合が発生した場合には、`<serviceActivations>` セクションにより、.svc の登録がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="25a5c-140">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="25a5c-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="25a5c-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
