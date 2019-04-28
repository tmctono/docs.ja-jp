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
ms.openlocfilehash: c176f7f470cc65bb135e5f92935102e09c7e8485
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758445"
---
# <a name="systemservicemodel"></a><span data-ttu-id="67a17-102">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="67a17-102">\<system.serviceModel></span></span>
<span data-ttu-id="67a17-103">この構成セクションには、すべての Windows Communication Foundation (WCF) ServiceModel 構成要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67a17-103">This configuration section contains all the Windows Communication Foundation (WCF) ServiceModel configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a17-104">構文</span><span class="sxs-lookup"><span data-stu-id="67a17-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67a17-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="67a17-105">Attributes and Elements</span></span>  
 <span data-ttu-id="67a17-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="67a17-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67a17-107">属性</span><span class="sxs-lookup"><span data-stu-id="67a17-107">Attributes</span></span>  
 <span data-ttu-id="67a17-108">なし</span><span class="sxs-lookup"><span data-stu-id="67a17-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="67a17-109">子要素</span><span class="sxs-lookup"><span data-stu-id="67a17-109">Child Elements</span></span>  
  
|<span data-ttu-id="67a17-110">要素</span><span class="sxs-lookup"><span data-stu-id="67a17-110">Element</span></span>|<span data-ttu-id="67a17-111">説明</span><span class="sxs-lookup"><span data-stu-id="67a17-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67a17-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="67a17-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|<span data-ttu-id="67a17-113">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-113">This section defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="67a17-114">各コレクションは、エンドポイントとサービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-114">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="67a17-115">各動作要素は、その一意の `name` 属性で識別されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-115">Each behavior element is identified by its unique `name` attribute.</span></span>|  
|[<span data-ttu-id="67a17-116">\<bindings></span><span class="sxs-lookup"><span data-stu-id="67a17-116">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="67a17-117">このセクションには、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-117">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="67a17-118">各エントリは、その一意の `name` により識別されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-118">Each entry is identified by its unique `name`.</span></span> <span data-ttu-id="67a17-119">サービスは、`name` を使用してバインディングをリンクすることにより、バインディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="67a17-119">Services use bindings by linking them using the `name`.</span></span>|  
|[<span data-ttu-id="67a17-120">\<client></span><span class="sxs-lookup"><span data-stu-id="67a17-120">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="67a17-121">このセクションは、クライアントがサービスの接続に使用するエンドポイントの一覧を含みます。</span><span class="sxs-lookup"><span data-stu-id="67a17-121">This section contains a list of endpoints a client uses to connect to a service.</span></span>|  
|[<span data-ttu-id="67a17-122">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="67a17-122">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|<span data-ttu-id="67a17-123">このセクションは、WCF と COM 相互運用が有効な COM コントラクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-123">This section defines COM contracts enabled for WCF and COM interop.</span></span>|  
|[<span data-ttu-id="67a17-124">\<commonBehaviors></span><span class="sxs-lookup"><span data-stu-id="67a17-124">\<commonBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|<span data-ttu-id="67a17-125">このセクションは、machine.config ファイルでだけ定義できます。</span><span class="sxs-lookup"><span data-stu-id="67a17-125">This section can only be defined in the machine.config file.</span></span> <span data-ttu-id="67a17-126">このセクションは、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-126">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="67a17-127">各コレクションは、それぞれのすべての WCF エンドポイントと、コンピューター上のサービスで使用された動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-127">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span>  <span data-ttu-id="67a17-128">両方で、動作が定義されている場合`<commonBehaviors>`と`<behaviors>`での動作、\<動作 > セクションが優先されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-128">If a behavior is defined in both `<commonBehaviors>` and `<behaviors>` sections, the behavior in the \<behaviors> section is given preference.</span></span>|  
|[<span data-ttu-id="67a17-129">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="67a17-129">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="67a17-130">このセクションには、WCF の診断機能の設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="67a17-130">This section contains settings for the diagnostics features of WCF.</span></span> <span data-ttu-id="67a17-131">ユーザーはトレース、パフォーマンス カウンター、および WMI プロバイダーを有効または無効にしたり、カスタム メッセージ フィルターを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="67a17-131">The user can enable/disable tracing, performance counters, and the WMI provider, and can add custom message filters.</span></span>|  
|[<span data-ttu-id="67a17-132">\<extensions></span><span class="sxs-lookup"><span data-stu-id="67a17-132">\<extensions></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|<span data-ttu-id="67a17-133">このセクションには、拡張のコレクションが含まれています。これにより、ユーザー定義のバインディング、動作、およびその他の拡張機能を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="67a17-133">This section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>|  
|[<span data-ttu-id="67a17-134">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="67a17-134">\<protocolMapping></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|<span data-ttu-id="67a17-135">このセクションでは、トランスポート プロトコル スキーム (など、http、net.tcp、net.pipe など) と WCF バインディング間の既定のプロトコル マッピングのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-135">This section defines a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span>|  
|[<span data-ttu-id="67a17-136">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="67a17-136">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="67a17-137">このセクションでは、Windows Communication Foundation (WCF) の種類を指定するルーティング フィルター セットを定義します<xref:System.ServiceModel.Dispatcher.MessageFilter>受信メッセージの評価とルーティング テーブルをときにメッセージを送信するターゲット エンドポイントを定義するときに使用される、。フィルターに一致します。</span><span class="sxs-lookup"><span data-stu-id="67a17-137">This section defines a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
|[<span data-ttu-id="67a17-138">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="67a17-138">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="67a17-139">このセクションは、環境をホストするサービスがインスタンス化する特定のトランスポートの型を定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-139">This section defines what type the service hosting environment instantiates for a particular transport.</span></span> <span data-ttu-id="67a17-140">このセクションが空の場合は、既定の型が使用されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-140">If this section is empty, the default type is used.</span></span>|  
|[<span data-ttu-id="67a17-141">\<services></span><span class="sxs-lookup"><span data-stu-id="67a17-141">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|<span data-ttu-id="67a17-142">このセクションには、サービスのコレクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="67a17-142">The section contains a collection of services.</span></span> <span data-ttu-id="67a17-143">アセンブリで定義された各サービスの場合、この要素は、サービスの設定を指定する `service` 要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="67a17-143">For each service defined in the assembly, this element contains a `service` element specifying settings for the service.</span></span>|  
|[<span data-ttu-id="67a17-144">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="67a17-144">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="67a17-145">このセクションは、再使用可能な構成済みのエンドポイントである標準エンドポイントのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-145">This section defines a collection of standard endpoints, which are reusable preconfigured endpoints.</span></span> <span data-ttu-id="67a17-146">標準エンドポイントは、固定値に設定されたアドレス、バインディング、およびコントラクトの 1 つ以上の属性を持ちます。</span><span class="sxs-lookup"><span data-stu-id="67a17-146">A standard endpoint will have one or more of the address, binding and contract attributes set to a fixed value.</span></span> <span data-ttu-id="67a17-147">たとえば、探索エンドポイントでは、コントラクトが固定されています。</span><span class="sxs-lookup"><span data-stu-id="67a17-147">For example, in the discovery endpoint the contract is fixed.</span></span> <span data-ttu-id="67a17-148">標準エンドポイントを使用して、カスタム バインドの定義と同様に新しいプロパティを指定して、サービス エンドポイントを拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="67a17-148">You can also use standard endpoints to extend service endpoint with new properties similar to defining custom bindings.</span></span>|
|[<span data-ttu-id="67a17-149">\<tracking></span><span class="sxs-lookup"><span data-stu-id="67a17-149">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tracking-of-wcf.md)|<span data-ttu-id="67a17-150">このセクションでは、ワークフロー サービスの追跡設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-150">This section defines tracking settings for a workflow service.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="67a17-151">親要素</span><span class="sxs-lookup"><span data-stu-id="67a17-151">Parent Elements</span></span>  
  
|<span data-ttu-id="67a17-152">要素</span><span class="sxs-lookup"><span data-stu-id="67a17-152">Element</span></span>|<span data-ttu-id="67a17-153">説明</span><span class="sxs-lookup"><span data-stu-id="67a17-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67a17-154">\<configuration></span><span class="sxs-lookup"><span data-stu-id="67a17-154">\<configuration></span></span>|<span data-ttu-id="67a17-155">.NET 構成ファイルのすべての構成要素のルート要素。</span><span class="sxs-lookup"><span data-stu-id="67a17-155">The root element for all configuration elements in a .NET configuration file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67a17-156">Remarks</span><span class="sxs-lookup"><span data-stu-id="67a17-156">Remarks</span></span>  
 <span data-ttu-id="67a17-157">WCF では、他の製品の構成セクションに要素を追加しません。</span><span class="sxs-lookup"><span data-stu-id="67a17-157">WCF does not add elements to the configuration sections of other products.</span></span>  
  
 <span data-ttu-id="67a17-158">WCF サービスが定義されている、`services`構成ファイルのセクション。</span><span class="sxs-lookup"><span data-stu-id="67a17-158">WCF services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="67a17-159">アセンブリには、任意の数のサービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="67a17-159">An assembly can contain any number of services.</span></span> <span data-ttu-id="67a17-160">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="67a17-160">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="67a17-161">セクションとその内容は、サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-161">The section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="67a17-162">サービスの `name` 属性だけが必須項目です。</span><span class="sxs-lookup"><span data-stu-id="67a17-162">Only a service's `name` attribute is required.</span></span>  <span data-ttu-id="67a17-163">既定では、サービスの名前は、サービスの実装に使用される、基になる CLR 型を示します。ただし、<xref:System.ServiceModel.ServiceContractAttribute> の ConfigurationName プロパティを変更して、CLR 型要件をオーバーライドすることもできます。</span><span class="sxs-lookup"><span data-stu-id="67a17-163">By default, a service's name describes the underlying CLR type used to implement a service; however, you may change the ConfigurationName property on a <xref:System.ServiceModel.ServiceContractAttribute> to override the CLR type requirement.</span></span>  
  
 <span data-ttu-id="67a17-164">`behaviorConfiguration` 属性は省略できます。</span><span class="sxs-lookup"><span data-stu-id="67a17-164">The `behaviorConfiguration` attribute is optional.</span></span> <span data-ttu-id="67a17-165">サービスが使用するサービス動作を識別します。</span><span class="sxs-lookup"><span data-stu-id="67a17-165">It identifies the service behavior used by a service.</span></span> <span data-ttu-id="67a17-166">この属性で指定された動作は、同じ構成ファイルの範囲内に定義されたサービス動作にリンクしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a17-166">The behavior specified by this attribute must link to a service behavior defined in the scope of the same configuration file (i.e. the same file or a parent file).</span></span>  
  
 <span data-ttu-id="67a17-167">各サービスでは、`endpoint` 要素で定義された 1 つまたは複数のエンドポイントが公開されます。</span><span class="sxs-lookup"><span data-stu-id="67a17-167">Each service exposes one or more endpoints defined in an `endpoint` element.</span></span> <span data-ttu-id="67a17-168">各エンドポイントには、独自のアドレスおよびバインディングがあります。</span><span class="sxs-lookup"><span data-stu-id="67a17-168">Each endpoint has its own address and binding.</span></span> <span data-ttu-id="67a17-169">構成ファイル内で使用されるすべてのバインディングは、そのファイルのスコープ内で定義される必要があります。</span><span class="sxs-lookup"><span data-stu-id="67a17-169">All bindings used within the configuration file must be defined in the scope of the file.</span></span>  
  
 <span data-ttu-id="67a17-170">バインディングは、`name` 属性と `bindingConfiguration` 属性の組み合わせによってエンドポイントにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="67a17-170">Bindings are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="67a17-171">`binding` 属性は、バインディングが定義されているセクションで定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-171">The `binding` attribute defines in which section the binding is defined.</span></span> <span data-ttu-id="67a17-172">`bindingConfiguration` 属性は、バインディング セクション内で使用される構成済みバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="67a17-172">The `bindingConfiguration` attribute defines which configured binding within the binding section is used.</span></span> <span data-ttu-id="67a17-173">バインディング セクションでは、複数の構成済みバインディングを定義できます。</span><span class="sxs-lookup"><span data-stu-id="67a17-173">A binding section can define several configured bindings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67a17-174">例</span><span class="sxs-lookup"><span data-stu-id="67a17-174">Example</span></span>  
 <span data-ttu-id="67a17-175">これは、WCF 構成ファイルの例です。</span><span class="sxs-lookup"><span data-stu-id="67a17-175">This is an example of a WCF configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="67a17-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="67a17-176">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
