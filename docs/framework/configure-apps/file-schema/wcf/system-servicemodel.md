---
title: <system.serviceModel>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: 2125ce00b0e23f2e93ff251549f9c1276892b16b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399454"
---
# \<system.serviceModel>
<span data-ttu-id="8c8b6-102">この構成セクションには、すべての Windows Communication Foundation (WCF) ServiceModel 構成要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-102">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.serviceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="8c8b6-103">構文</span><span class="sxs-lookup"><span data-stu-id="8c8b6-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
  </behaviors>
  <bindings>
  </bindings>
  <client>
  </client>
  <comContracts>
  </comContracts>
  <commonBehaviors>
  </commonBehaviors>
  <diagnostics>
  </diagnostics>
  <extensions>
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>
  <serviceHostingEnvironment>
  </serviceHostingEnvironment>
  <services>
  </services>
  <standardEndpoints>
  </standardEndpoints>
  <tracking>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c8b6-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8c8b6-104">Attributes and Elements</span></span>  
 <span data-ttu-id="8c8b6-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c8b6-106">属性</span><span class="sxs-lookup"><span data-stu-id="8c8b6-106">Attributes</span></span>  
 <span data-ttu-id="8c8b6-107">なし</span><span class="sxs-lookup"><span data-stu-id="8c8b6-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8c8b6-108">子要素</span><span class="sxs-lookup"><span data-stu-id="8c8b6-108">Child Elements</span></span>  
  
|<span data-ttu-id="8c8b6-109">要素</span><span class="sxs-lookup"><span data-stu-id="8c8b6-109">Element</span></span>|<span data-ttu-id="8c8b6-110">説明</span><span class="sxs-lookup"><span data-stu-id="8c8b6-110">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors.md)|<span data-ttu-id="8c8b6-111">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-111">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="8c8b6-112">各コレクションは、エンドポイントとサービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-112">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="8c8b6-113">各動作要素は、その一意の `name` 属性で識別されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-113">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[\<bindings>](bindings.md)|<span data-ttu-id="8c8b6-114">このセクションには、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-114">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="8c8b6-115">各エントリは、その一意の `name` により識別されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-115">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="8c8b6-116">サービスは、`name` を使用してバインディングをリンクすることにより、バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-116">Services use bindings by linking them using the `name`.</span></span>|  
|[\<client>](client.md)|<span data-ttu-id="8c8b6-117">このセクションは、クライアントがサービスの接続に使用するエンドポイントの一覧を含みます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-117">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[\<comContracts>](comcontracts.md)|<span data-ttu-id="8c8b6-118">このセクションは、WCF と COM 相互運用が有効な COM コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-118">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[\<commonBehaviors>](commonbehaviors.md)|<span data-ttu-id="8c8b6-119">このセクションは、machine.config ファイルでだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-119">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="8c8b6-120">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-120">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="8c8b6-121">各コレクションは、コンピューター上のすべての WCF エンドポイントとサービスによって使用される動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-121">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="8c8b6-122">ある動作が `<commonBehaviors>` と `<behaviors>` の両方のセクションで定義されている場合は、\<behaviors> セクション内の動作が優先されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-122">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[\<diagnostics>](diagnostics.md)|<span data-ttu-id="8c8b6-123">このセクションには、WCF の診断機能の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-123">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="8c8b6-124">ユーザーはトレース、パフォーマンス カウンター、および WMI プロバイダーを有効または無効にしたり、カスタム メッセージ フィルターを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-124">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[\<extensions>](extensions-section.md)|<span data-ttu-id="8c8b6-125">このセクションには、拡張のコレクションが含まれています。これにより、ユーザー定義のバインディング、動作、およびその他の拡張機能を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-125">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="8c8b6-126">このセクションは、トランスポート プロトコル スキーム (http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピング セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-126">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[\<routing>](routing.md)|<span data-ttu-id="8c8b6-127">このセクションでは、受信メッセージを評価するときに使用する Windows Communication Foundation (WCF) の種類を決定するルーティングフィルターのセットと、 <xref:System.ServiceModel.Dispatcher.MessageFilter> フィルターが一致したときにメッセージを送信するターゲットエンドポイントを定義するルーティングテーブルを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-127">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[\<serviceHostingEnvironment>](servicehostingenvironment.md)|<span data-ttu-id="8c8b6-128">このセクションは、環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-128">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="8c8b6-129">このセクションが空の場合は、既定の型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-129">If this section is empty, the default type is used.</span></span>|  
|[\<services>](services.md)|<span data-ttu-id="8c8b6-130">このセクションには、サービスのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-130">The section contains a collection of services.</span></span> <span data-ttu-id="8c8b6-131">アセンブリで定義された各サービスの場合、この要素は、サービスの設定を指定する `service` 要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-131">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="8c8b6-132">このセクションは、再使用可能な構成済みのエンドポイントである標準エンドポイントのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-132">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="8c8b6-133">標準エンドポイントは、固定値に設定されたアドレス、バインディング、およびコントラクトの 1 つ以上の属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-133">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="8c8b6-134">たとえば、探索エンドポイントでは、コントラクトが固定されています。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-134">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="8c8b6-135">標準エンドポイントを使用して、カスタム バインドの定義と同様に新しいプロパティを指定して、サービス エンドポイントを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-135">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[\<tracking>](tracking-of-wcf.md)|<span data-ttu-id="8c8b6-136">このセクションでは、ワークフローサービスの追跡設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-136">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8c8b6-137">親要素</span><span class="sxs-lookup"><span data-stu-id="8c8b6-137">Parent Elements</span></span>  
  
|<span data-ttu-id="8c8b6-138">要素</span><span class="sxs-lookup"><span data-stu-id="8c8b6-138">Element</span></span>|<span data-ttu-id="8c8b6-139">説明</span><span class="sxs-lookup"><span data-stu-id="8c8b6-139">Description</span></span>|  
|-------------|-----------------|  
|\<configuration>|<span data-ttu-id="8c8b6-140">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-140">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c8b6-141">解説</span><span class="sxs-lookup"><span data-stu-id="8c8b6-141">Remarks</span></span>  
 <span data-ttu-id="8c8b6-142">WCF では、他の製品の構成セクションに要素を追加しません。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-142">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="8c8b6-143">WCF サービスは、構成ファイルのセクションで定義されてい `services` ます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-143">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="8c8b6-144">アセンブリには、任意の数のサービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-144">An assembly can contain any number of services.</span></span> <span data-ttu-id="8c8b6-145">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-145">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="8c8b6-146">セクションとその内容は、サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-146">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="8c8b6-147">サービスの `name` 属性だけが必須項目です。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-147">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="8c8b6-148">既定では、サービスの名前は、サービスの実装に使用される、基になる CLR 型を示します。ただし、<xref:System.ServiceModel.ServiceContractAttribute> の ConfigurationName プロパティを変更して、CLR 型要件をオーバーライドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-148">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="8c8b6-149">`behaviorConfiguration` 属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-149">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="8c8b6-150">サービスが使用するサービス動作を識別します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-150">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="8c8b6-151">この属性で指定された動作は、同じ構成ファイルの範囲内に定義されたサービス動作にリンクしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-151">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="8c8b6-152">各サービスでは、`endpoint` 要素で定義された 1 つまたは複数のエンドポイントが公開されます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-152">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="8c8b6-153">各エンドポイントには、独自のアドレスおよびバインディングがあります。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-153">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="8c8b6-154">構成ファイル内で使用されるすべてのバインディングは、そのファイルのスコープ内で定義される必要があります。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-154">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="8c8b6-155">バインディングは、`name` 属性と `bindingConfiguration` 属性の組み合わせによってエンドポイントにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-155">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="8c8b6-156">`binding` 属性は、バインディングが定義されているセクションで定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-156">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="8c8b6-157">`bindingConfiguration` 属性は、バインディング セクション内で使用される構成済みバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-157">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="8c8b6-158">バインディング セクションでは、複数の構成済みバインディングを定義できます。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-158">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c8b6-159">例</span><span class="sxs-lookup"><span data-stu-id="8c8b6-159">Example</span></span>  
 <span data-ttu-id="8c8b6-160">これは、WCF 構成ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="8c8b6-160">This is an example of a WCF configuration file.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <!-- List of Behaviors -->
    </behaviors>
    <client>
      <!-- List of Endpoints -->
    </client>
    <diagnostics wmiProviderEnabled="false"
                 performanceCountersEnabled="false"
                 tracingEnabled="false">
    </diagnostics>
    <serviceHostingEnvironment>
      <!-- List of entries -->
    </serviceHostingEnvironment>
    <comContracts>
      <!-- List of COM+ Contracts -->
    </comContracts>
    <services>
      <!-- List of Services -->
    </services>
    <bindings>
      <!-- List of Bindings -->
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="8c8b6-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="8c8b6-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
