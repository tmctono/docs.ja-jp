---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 0673507b72690c3a5c7dcc35442c05e378dba43c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153036"
---
# <a name="baseaddressprefixfilters"></a><span data-ttu-id="5d275-101">\<>を使用します。</span><span class="sxs-lookup"><span data-stu-id="5d275-101">\<baseAddressPrefixFilters></span></span>
<span data-ttu-id="5d275-102">IIS で Windows 通信基盤 (WCF) アプリケーションをホストするときに適切なインターネット インフォメーション サービス (IIS) バインディングを選択するメカニズムを提供する、パススルー フィルターを指定する構成要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5d275-102">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="5d275-103">\<> "ローカル ホスト" を認識しません。代わりに完全修飾マシン名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="5d275-103">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
<span data-ttu-id="5d275-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d275-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d275-105">&nbsp;&nbsp;[**\<システム.サービスモデル>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5d275-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5d275-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<サービスホスティング環境>**](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="5d275-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="5d275-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>を適用します。**</span><span class="sxs-lookup"><span data-stu-id="5d275-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d275-108">構文</span><span class="sxs-lookup"><span data-stu-id="5d275-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d275-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d275-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5d275-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d275-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d275-111">属性</span><span class="sxs-lookup"><span data-stu-id="5d275-111">Attributes</span></span>  
 <span data-ttu-id="5d275-112">[なし] :</span><span class="sxs-lookup"><span data-stu-id="5d275-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d275-113">子要素</span><span class="sxs-lookup"><span data-stu-id="5d275-113">Child Elements</span></span>  
  
|<span data-ttu-id="5d275-114">要素</span><span class="sxs-lookup"><span data-stu-id="5d275-114">Element</span></span>|<span data-ttu-id="5d275-115">説明</span><span class="sxs-lookup"><span data-stu-id="5d275-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d275-116">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="5d275-116">\<add></span></span>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="5d275-117">サービス ホストによって使用されるベース アドレスのプレフィックス フィルターを指定する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="5d275-117">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d275-118">親要素</span><span class="sxs-lookup"><span data-stu-id="5d275-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5d275-119">要素</span><span class="sxs-lookup"><span data-stu-id="5d275-119">Element</span></span>|<span data-ttu-id="5d275-120">説明</span><span class="sxs-lookup"><span data-stu-id="5d275-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d275-121">\<サービスホスティング環境></span><span class="sxs-lookup"><span data-stu-id="5d275-121">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="5d275-122">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="5d275-122">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d275-123">解説</span><span class="sxs-lookup"><span data-stu-id="5d275-123">Remarks</span></span>  
 <span data-ttu-id="5d275-124">プレフィックス フィルターは、サービスによって使用される URI を、共有ホスティング プロバイダーが指定できるようにする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d275-124">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="5d275-125">これにより、共有ホストは、同じサイト上の同じスキームに対して、別々のベース アドレスを使用して複数のアプリケーションをホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d275-125">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="5d275-126">IIS Web サイトは、仮想ディレクトリを含む仮想アプリケーションのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="5d275-126">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="5d275-127">サイト内のアプリケーションには、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5d275-127">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="5d275-128">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="5d275-128">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="5d275-129">バインディング プロトコル (HTTP など) は通信を行うスキームを定義し、バインディング情報 (IP アドレス、ポート、ホスト ヘッダーなど) にはサイトにアクセスするために使用するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5d275-129">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="5d275-130">IIS では、サイトごとに複数の IIS バインディングを指定できるので、各スキームに複数のベース アドレスが定義されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5d275-130">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="5d275-131">サイトの下でホストされる WCF サービスでは、スキームごとに 1 つのベース アドレスへのバインドのみが許可されるため、プレフィックス フィルター機能を使用して、ホストされるサービスの必要なベース アドレスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5d275-131">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="5d275-132">IIS によって指定される受信ベース アドレスは、オプションのプレフィックス リスト フィルターに基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="5d275-132">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="5d275-133">たとえば、サイトには次のベース アドレスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5d275-133">For example, your site can contain the following base addresses:</span></span>
  
```
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="5d275-134">次の構成ファイルを使用して、appdomain レベルでプレフィックス フィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5d275-134">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
```xml  
<system.serviceModel>
  <serviceHostingEnvironment>
    <baseAddressPrefixFilters>
      <add prefix="net.tcp://test1.fabrikam.com:8000" />
      <add prefix="http://test2.fabrikam.com:9000" />
    </baseAddressPrefixFilters>
  </serviceHostingEnvironment>
</system.serviceModel>
```  
  
 <span data-ttu-id="5d275-135">この例では、`net.tcp://test1.fabrikam.com:8000` と `http://test2.fabrikam.com:9000` が、対応するスキームに渡される唯一のベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="5d275-135">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="5d275-136">既定では、プレフィックスを指定しない場合、すべてのアドレスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="5d275-136">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="5d275-137">プレフィックスだけを指定すると、そのスキームに一致するベース アドレスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="5d275-137">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5d275-138">フィルターでワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5d275-138">The filter does not support any wildcards.</span></span> <span data-ttu-id="5d275-139">また、IIS が提供する baseAddresses には、`baseAddressPrefixFilters` リストに存在しない他のスキームにバインドされたアドレスが指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d275-139">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="5d275-140">これらのアドレスはフィルターで除外されません。</span><span class="sxs-lookup"><span data-stu-id="5d275-140">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d275-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d275-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="5d275-142">ホスティング</span><span class="sxs-lookup"><span data-stu-id="5d275-142">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
