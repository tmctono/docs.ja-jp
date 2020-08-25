---
title: <baseAddressPrefixFilters>
ms.date: 03/30/2017
ms.assetid: 8cab2a9a-c51f-4283-bb60-2ad0c274fd46
ms.openlocfilehash: 635e4f02f4d286b63c4f4845563ba1953d23592a
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811900"
---
# \<baseAddressPrefixFilters>
<span data-ttu-id="1caec-101">パススルーフィルターを指定する構成要素のコレクションを表します。パススルーフィルターは、IIS で Windows Communication Foundation (WCF) アプリケーションをホストするときに適切なインターネットインフォメーションサービス (IIS) バインドを選択するメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="1caec-101">Represents a collection of configuration elements that specify pass through filters, which provide a mechanism to pick the appropriate Internet Information Services (IIS) bindings when hosting the Windows Communication Foundation (WCF) application in IIS.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="1caec-102">\<baseAddressPrefixFilters> は "localhost" を認識しません。代わりに、完全修飾コンピューター名を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1caec-102">\<baseAddressPrefixFilters> does not recognize "localhost"; use the fully qualified machine name instead.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddressPrefixFilters>**  
  
## <a name="syntax"></a><span data-ttu-id="1caec-103">構文</span><span class="sxs-lookup"><span data-stu-id="1caec-103">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <baseAddressPrefixFilters>
    <add prefix="String" />
   </baseAddressPrefixFilters>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1caec-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1caec-104">Attributes and Elements</span></span>  
 <span data-ttu-id="1caec-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1caec-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1caec-106">属性</span><span class="sxs-lookup"><span data-stu-id="1caec-106">Attributes</span></span>  
 <span data-ttu-id="1caec-107">なし。</span><span class="sxs-lookup"><span data-stu-id="1caec-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1caec-108">子要素</span><span class="sxs-lookup"><span data-stu-id="1caec-108">Child Elements</span></span>  
  
|<span data-ttu-id="1caec-109">要素</span><span class="sxs-lookup"><span data-stu-id="1caec-109">Element</span></span>|<span data-ttu-id="1caec-110">説明</span><span class="sxs-lookup"><span data-stu-id="1caec-110">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddressprefixfilter.md)|<span data-ttu-id="1caec-111">サービス ホストによって使用されるベース アドレスのプレフィックス フィルターを指定する構成要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="1caec-111">Adds a configuration element that specifies a prefix filter for the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1caec-112">親要素</span><span class="sxs-lookup"><span data-stu-id="1caec-112">Parent Elements</span></span>  
  
|<span data-ttu-id="1caec-113">要素</span><span class="sxs-lookup"><span data-stu-id="1caec-113">Element</span></span>|<span data-ttu-id="1caec-114">説明</span><span class="sxs-lookup"><span data-stu-id="1caec-114">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="1caec-115">環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="1caec-115">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1caec-116">注釈</span><span class="sxs-lookup"><span data-stu-id="1caec-116">Remarks</span></span>  
 <span data-ttu-id="1caec-117">プレフィックス フィルターは、サービスによって使用される URI を、共有ホスティング プロバイダーが指定できるようにする手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1caec-117">A prefix filter provides a way for shared hosting providers to specify which URIs are to be used by the service.</span></span> <span data-ttu-id="1caec-118">これにより、共有ホストは、同じサイト上の同じスキームに対して、別々のベース アドレスを使用して複数のアプリケーションをホストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="1caec-118">It enables shared hosts to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="1caec-119">IIS Web サイトは、仮想ディレクトリを含む仮想アプリケーションのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="1caec-119">IIS Web sites are containers for virtual applications which contain virtual directories.</span></span> <span data-ttu-id="1caec-120">サイト内のアプリケーションには、1 つ以上の IIS バインディングからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1caec-120">The application in a site can be accessed through one or more IIS bindings.</span></span> <span data-ttu-id="1caec-121">IIS バインディングは、バインディング プロトコルとバインディング情報という 2 つの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="1caec-121">IIS bindings provide two pieces of information: binding protocol and binding information.</span></span> <span data-ttu-id="1caec-122">バインディング プロトコル (HTTP など) は通信を行うスキームを定義し、バインディング情報 (IP アドレス、ポート、ホスト ヘッダーなど) にはサイトにアクセスするために使用するデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1caec-122">Binding protocol (for example, HTTP) defines the scheme over which communication occurs, and binding information (for example, IP Address, Port, Hostheader) contains data used to access the site.</span></span>  
  
 <span data-ttu-id="1caec-123">IIS では、サイトごとに複数の IIS バインディングを指定できるので、各スキームに複数のベース アドレスが定義されることがあります。</span><span class="sxs-lookup"><span data-stu-id="1caec-123">IIS supports specifying multiple IIS bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="1caec-124">サイトでホストされる WCF サービスでは、スキームごとに1つのベースアドレスにしかバインドできないため、プレフィックスフィルター機能を使用して、ホステッドサービスの必要なベースアドレスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="1caec-124">Because a WCF service hosted under a site allows binding to only one base address for each scheme, you can use the prefix filter feature to pick the required base address of the hosted service.</span></span> <span data-ttu-id="1caec-125">IIS によって指定される受信ベース アドレスは、オプションのプレフィックス リスト フィルターに基づいてフィルター処理されます。</span><span class="sxs-lookup"><span data-stu-id="1caec-125">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list filter.</span></span>  
  
 <span data-ttu-id="1caec-126">たとえば、サイトに次のベースアドレスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="1caec-126">For example, your site can contain the following base addresses:</span></span>
  
```http
http://testl.fabrikam.com/Service.svc  
http://test2.fabrikam.com/Service.svc  
```  
  
 <span data-ttu-id="1caec-127">次の構成ファイルを使用して、appdomain レベルでプレフィックス フィルターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1caec-127">You can use the following configuration file to specify a prefix filter at the appdomain level.</span></span>  
  
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
  
 <span data-ttu-id="1caec-128">この例では、`net.tcp://test1.fabrikam.com:8000` と `http://test2.fabrikam.com:9000` が、対応するスキームに渡される唯一のベース アドレスです。</span><span class="sxs-lookup"><span data-stu-id="1caec-128">In this example, `net.tcp://test1.fabrikam.com:8000` and `http://test2.fabrikam.com:9000` are the only base addresses for their respective schemes, which are allowed to be passed through.</span></span>  
  
 <span data-ttu-id="1caec-129">既定では、プレフィックスを指定しない場合、すべてのアドレスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="1caec-129">By default, when prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="1caec-130">プレフィックスだけを指定すると、そのスキームに一致するベース アドレスを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1caec-130">Specifying the prefix only allows the matching base address for that scheme to be passed through.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1caec-131">フィルターでワイルドカードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="1caec-131">The filter does not support any wildcards.</span></span> <span data-ttu-id="1caec-132">また、IIS が提供する baseAddresses には、`baseAddressPrefixFilters` リストに存在しない他のスキームにバインドされたアドレスが指定される場合があります。</span><span class="sxs-lookup"><span data-stu-id="1caec-132">In addition, the baseAddresses supplied by IIS may have addresses bound to other schemes not present in the `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="1caec-133">これらのアドレスはフィルターで除外されません。</span><span class="sxs-lookup"><span data-stu-id="1caec-133">These addresses are not filtered out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1caec-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="1caec-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.BaseAddressPrefixFilterElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="1caec-135">ホスティング</span><span class="sxs-lookup"><span data-stu-id="1caec-135">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
