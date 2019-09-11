---
title: <endpoint> 要素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: fb9d3bf9b5f1a742abcc70d78af026c179ec4c4d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855383"
---
# <a name="endpoint-element"></a><span data-ttu-id="49f65-102">\<エンドポイント > 要素</span><span class="sxs-lookup"><span data-stu-id="49f65-102">\<endpoint> element</span></span>
<span data-ttu-id="49f65-103">サービスの公開に使用されるサービス エンドポイントのバインディング、コントラクト、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="49f65-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
<span data-ttu-id="49f65-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="49f65-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="49f65-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="49f65-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="49f65-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="49f65-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="49f65-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="49f65-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="49f65-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<エンドポイント >**</span><span class="sxs-lookup"><span data-stu-id="49f65-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f65-109">構文</span><span class="sxs-lookup"><span data-stu-id="49f65-109">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          bindingName="String"
          bindingNamespace="String"
          contract="String"
          endpointConfiguration="String"
          isSystemEndpoint="Boolean"
          kind="String"
          listenUriMode="Explicit/Unique"
          listenUri="Uri">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49f65-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="49f65-110">Attributes and Elements</span></span>  
 <span data-ttu-id="49f65-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="49f65-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49f65-112">属性</span><span class="sxs-lookup"><span data-stu-id="49f65-112">Attributes</span></span>  
  
|<span data-ttu-id="49f65-113">属性</span><span class="sxs-lookup"><span data-stu-id="49f65-113">Attribute</span></span>|<span data-ttu-id="49f65-114">説明</span><span class="sxs-lookup"><span data-stu-id="49f65-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="49f65-115">address</span><span class="sxs-lookup"><span data-stu-id="49f65-115">address</span></span>|<span data-ttu-id="49f65-116">エンドポイントのアドレスを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-116">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="49f65-117">アドレスは、絶対または相対アドレスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="49f65-117">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="49f65-118">相対アドレスが提供されている場合、ホストは、そのバインディングで使用されるトランスポート スキームに適したベース アドレスが提供されることを想定します。</span><span class="sxs-lookup"><span data-stu-id="49f65-118">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="49f65-119">アドレスが構成されていない場合、ベース アドレスはそのエンドポイントのアドレスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="49f65-119">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="49f65-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="49f65-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="49f65-121">behaviorConfiguration</span></span>|<span data-ttu-id="49f65-122">エンドポイントで使用される動作の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-122">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="49f65-123">バインド</span><span class="sxs-lookup"><span data-stu-id="49f65-123">binding</span></span>|<span data-ttu-id="49f65-124">使用するバインディングの種類を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="49f65-124">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="49f65-125">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f65-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="49f65-126">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="49f65-126">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="49f65-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="49f65-127">bindingConfiguration</span></span>|<span data-ttu-id="49f65-128">エンドポイントがインスタンス化されるときに使用するバインディングのバインディング名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-128">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="49f65-129">バインディング名は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f65-129">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="49f65-130">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-130">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="49f65-131">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="49f65-131">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="49f65-132">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="49f65-132">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="49f65-133">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="49f65-133">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="49f65-134">bindingName</span><span class="sxs-lookup"><span data-stu-id="49f65-134">bindingName</span></span>|<span data-ttu-id="49f65-135">WSDL を介した定義エクスポートに使用するバインディングの一意の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-135">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="49f65-136">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-136">The default is an empty string.</span></span>|  
|<span data-ttu-id="49f65-137">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="49f65-137">bindingNamespace</span></span>|<span data-ttu-id="49f65-138">WSDL を介した定義エクスポートに使用するバインディングの名前空間の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-138">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="49f65-139">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="49f65-140">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="49f65-140">contract</span></span>|<span data-ttu-id="49f65-141">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-141">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="49f65-142">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f65-142">The assembly must implement the contract type.</span></span> <span data-ttu-id="49f65-143">サービス実装が単一のコントラクトの型を実装する場合は、このプロパティを省略できます。</span><span class="sxs-lookup"><span data-stu-id="49f65-143">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="49f65-144">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-144">The default is an empty string.</span></span>|  
|<span data-ttu-id="49f65-145">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="49f65-145">endpointConfiguration</span></span>|<span data-ttu-id="49f65-146">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-146">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="49f65-147">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49f65-147">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="49f65-148">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="49f65-148">isSystemEndpoint</span></span>|<span data-ttu-id="49f65-149">インフラストラクチャ エンドポイントであるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="49f65-149">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="49f65-150">kind</span><span class="sxs-lookup"><span data-stu-id="49f65-150">kind</span></span>|<span data-ttu-id="49f65-151">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-151">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="49f65-152">種類は `<extensions>` セクションまたは machine.config に登録する必要があります。何も指定されていない場合は、共通のサービス エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="49f65-152">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="49f65-153">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="49f65-153">listenUriMode</span></span>|<span data-ttu-id="49f65-154">リッスンするサービスに提供される `ListenUri` をトランスポートが処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="49f65-154">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="49f65-155">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="49f65-155">Valid values are</span></span><br /><br /> <span data-ttu-id="49f65-156">-Explicit</span><span class="sxs-lookup"><span data-stu-id="49f65-156">-   Explicit</span></span><br /><span data-ttu-id="49f65-157">-一意</span><span class="sxs-lookup"><span data-stu-id="49f65-157">-   Unique</span></span><br /><br /> <span data-ttu-id="49f65-158">既定値は Explicit です。</span><span class="sxs-lookup"><span data-stu-id="49f65-158">The default value is Explicit.</span></span>|  
|<span data-ttu-id="49f65-159">listenUri</span><span class="sxs-lookup"><span data-stu-id="49f65-159">listenUri</span></span>|<span data-ttu-id="49f65-160">サービス エンドポイントがリッスンする URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-160">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="49f65-161">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="49f65-161">The default is an empty string.</span></span>|  
|<span data-ttu-id="49f65-162">name</span><span class="sxs-lookup"><span data-stu-id="49f65-162">name</span></span>|<span data-ttu-id="49f65-163">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="49f65-163">Optional attribute.</span></span> <span data-ttu-id="49f65-164">サービス エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="49f65-164">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="49f65-165">既定値は、バインディング名とコントラクトの説明の名前を連結した値です。</span><span class="sxs-lookup"><span data-stu-id="49f65-165">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="49f65-166">サービスには複数のエンドポイントが存在する場合があるため、エンドポイントの `name` 属性はサービスの名前とは異なります。</span><span class="sxs-lookup"><span data-stu-id="49f65-166">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="49f65-167">子要素</span><span class="sxs-lookup"><span data-stu-id="49f65-167">Child Elements</span></span>  
  
|<span data-ttu-id="49f65-168">要素</span><span class="sxs-lookup"><span data-stu-id="49f65-168">Element</span></span>|<span data-ttu-id="49f65-169">説明</span><span class="sxs-lookup"><span data-stu-id="49f65-169">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49f65-170">\<headers></span><span class="sxs-lookup"><span data-stu-id="49f65-170">\<headers></span></span>](headers.md)|<span data-ttu-id="49f65-171">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="49f65-171">A collection of address headers.</span></span>|  
|[<span data-ttu-id="49f65-172">\<identity></span><span class="sxs-lookup"><span data-stu-id="49f65-172">\<identity></span></span>](identity.md)|<span data-ttu-id="49f65-173">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="49f65-173">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49f65-174">親要素</span><span class="sxs-lookup"><span data-stu-id="49f65-174">Parent Elements</span></span>  
  
|<span data-ttu-id="49f65-175">要素</span><span class="sxs-lookup"><span data-stu-id="49f65-175">Element</span></span>|<span data-ttu-id="49f65-176">説明</span><span class="sxs-lookup"><span data-stu-id="49f65-176">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49f65-177">\<service></span><span class="sxs-lookup"><span data-stu-id="49f65-177">\<service></span></span>](service.md)|<span data-ttu-id="49f65-178">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="49f65-178">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49f65-179">例</span><span class="sxs-lookup"><span data-stu-id="49f65-179">Example</span></span>  
 <span data-ttu-id="49f65-180">これはサービス エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="49f65-180">This is an example of a service endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          bindingName="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
  <headers>
    <region xmlns="http://tempuri.org/">EastCoast</region>
    <member xmlns="http://tempuri.org/">Gold</member>
  </headers>
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="49f65-181">関連項目</span><span class="sxs-lookup"><span data-stu-id="49f65-181">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="49f65-182">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="49f65-182">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="49f65-183">方法: 構成にサービスエンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="49f65-183">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
