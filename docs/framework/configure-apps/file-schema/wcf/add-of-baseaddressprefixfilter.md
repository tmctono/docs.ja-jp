---
title: <add> の <baseAddressPrefixFilter>
ms.date: 03/30/2017
ms.assetid: b226bede-8459-4de9-b2ac-3d39604ce2bc
ms.openlocfilehash: dee2cd482efc841b7320ed2114a05000255466f3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850520"
---
# <a name="add-of-baseaddressprefixfilter"></a><span data-ttu-id="ac52d-102">\<baseAddressPrefixFilter > の\<> の追加</span><span class="sxs-lookup"><span data-stu-id="ac52d-102">\<add> of \<baseAddressPrefixFilter></span></span>
<span data-ttu-id="ac52d-103">IIS で Windows Communication Foundation (WCF) アプリケーションをホストするときに適切なインターネットインフォメーションサービス (IIS) バインドを選択するメカニズムを提供する、パススルーフィルターを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="ac52d-103">Represents a configuration element that specifies a pass-through filter, which provides a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
<span data-ttu-id="ac52d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ac52d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ac52d-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ac52d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ac52d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="ac52d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="ac52d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<baseAddressPrefixFilters >** ](baseaddressprefixfilters.md)</span><span class="sxs-lookup"><span data-stu-id="ac52d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddressPrefixFilters>**](baseaddressprefixfilters.md)</span></span>\
<span data-ttu-id="ac52d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<add>**</span><span class="sxs-lookup"><span data-stu-id="ac52d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac52d-109">構文</span><span class="sxs-lookup"><span data-stu-id="ac52d-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
  </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac52d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac52d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ac52d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac52d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac52d-112">属性</span><span class="sxs-lookup"><span data-stu-id="ac52d-112">Attributes</span></span>  
  
|<span data-ttu-id="ac52d-113">属性</span><span class="sxs-lookup"><span data-stu-id="ac52d-113">Attribute</span></span>|<span data-ttu-id="ac52d-114">説明</span><span class="sxs-lookup"><span data-stu-id="ac52d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac52d-115">prefix</span><span class="sxs-lookup"><span data-stu-id="ac52d-115">prefix</span></span>|<span data-ttu-id="ac52d-116">ベース アドレスの一部の一致に使用される URI。</span><span class="sxs-lookup"><span data-stu-id="ac52d-116">A URI that is used to match a part of a base address.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac52d-117">子要素</span><span class="sxs-lookup"><span data-stu-id="ac52d-117">Child Elements</span></span>  
 <span data-ttu-id="ac52d-118">なし。</span><span class="sxs-lookup"><span data-stu-id="ac52d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac52d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="ac52d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ac52d-120">要素</span><span class="sxs-lookup"><span data-stu-id="ac52d-120">Element</span></span>|<span data-ttu-id="ac52d-121">説明</span><span class="sxs-lookup"><span data-stu-id="ac52d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac52d-122">\<baseAddressPrefixFilters></span><span class="sxs-lookup"><span data-stu-id="ac52d-122">\<baseAddressPrefixFilters></span></span>](baseaddressprefixfilters.md)|<span data-ttu-id="ac52d-123">パススルーフィルターを指定する構成要素のコレクション。これは、IIS で Windows Communication Foundation (WCF) アプリケーションをホストするときに適切な IIS バインディングを選択する機構を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac52d-123">A collection of configuration elements that specify pass-through filters, which provide a mechanism to pick the appropriate IIS bindings when hosting a Windows Communication Foundation (WCF) application in IIS.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac52d-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="ac52d-124">Remarks</span></span>  
 <span data-ttu-id="ac52d-125">プレフィックス フィルターは、サービスによって使用される URI を、共有ホスティング プロバイダーが指定できるようにする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac52d-125">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="ac52d-126">これにより、共有ホストは、同じサイト上の同じスキームに対して、別々のベース アドレスを使用して複数のアプリケーションをホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac52d-126">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="ac52d-127">IIS Web サイトは、仮想ディレクトリを含む仮想アプリケーションのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="ac52d-127">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="ac52d-128">サイト内のアプリケーションに、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-128">The application in a site can be accessed through one or more IIS binding.</span></span> <span data-ttu-id="ac52d-129">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ac52d-129">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="ac52d-130">バインディング プロトコル (HTTP など) は通信を行うスキームを定義し、バインディング情報 (IP アドレス、ポート、ホスト ヘッダーなど) にはサイトにアクセスするために使用するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-130">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="ac52d-131">IIS では、サイトごとに複数の IIS バインディングを指定できるので、各スキームに複数のベース アドレスが定義されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ac52d-131">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="ac52d-132">サイトでホストされる WCF サービスでは、スキームごとに1つのベースアドレスにしかバインドできないため、プレフィックスフィルター機能を使用して、ホステッドサービスの必要なベースアドレスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-132">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="ac52d-133">IIS によって指定される受信ベース アドレスは、オプションのプレフィックス リスト フィルターに基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-133">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="ac52d-134">たとえば、サイトに次のベース アドレスが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="ac52d-134">For example, your site can contain the following base addresses.</span></span>  
  
```  
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="ac52d-135">次の構成ファイルを使用して、appdomain レベルでプレフィックス フィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-135">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="ac52d-136">この例では、`net.tcp://test1.fabrikam.com:8000` と `http://test2.fabrikam.com:9000` はそれぞれのスキームにおいて、そのまま渡すことができる唯一のベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ac52d-136">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="ac52d-137">既定では、プレフィックスを指定しない場合、すべてのアドレスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-137">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="ac52d-138">プレフィックスだけを指定すると、そのスキームに一致するベース アドレスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac52d-138">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac52d-139">フィルターでワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ac52d-139">The filter does not support any wildcards.</span></span> <span data-ttu-id="ac52d-140">また、IIS が提供する baseAddresses には、`baseAddressPrefixFilters` リストに存在しない他のスキームにバインドされたアドレスが指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac52d-140">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="ac52d-141">これらのアドレスはフィルターで除外されません。</span><span class="sxs-lookup"><span data-stu-id="ac52d-141">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac52d-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac52d-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="ac52d-143">ホスティング</span><span class="sxs-lookup"><span data-stu-id="ac52d-143">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
