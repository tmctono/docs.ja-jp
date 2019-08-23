---
title: <endpoint> 要素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: 71ddb3b860870ee8feeeb36c3f64fa7bfebb0f10
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925823"
---
# <a name="endpoint-element"></a><span data-ttu-id="cd3d0-102">\<エンドポイント > 要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-102">\<endpoint> element</span></span>
<span data-ttu-id="cd3d0-103">サービスの公開に使用されるサービス エンドポイントのバインディング、コントラクト、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
 <span data-ttu-id="cd3d0-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="cd3d0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cd3d0-105">\<サービス ></span><span class="sxs-lookup"><span data-stu-id="cd3d0-105">\<service></span></span>  
<span data-ttu-id="cd3d0-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="cd3d0-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd3d0-107">構文</span><span class="sxs-lookup"><span data-stu-id="cd3d0-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd3d0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cd3d0-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd3d0-110">属性</span><span class="sxs-lookup"><span data-stu-id="cd3d0-110">Attributes</span></span>  
  
|<span data-ttu-id="cd3d0-111">属性</span><span class="sxs-lookup"><span data-stu-id="cd3d0-111">Attribute</span></span>|<span data-ttu-id="cd3d0-112">説明</span><span class="sxs-lookup"><span data-stu-id="cd3d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd3d0-113">address</span><span class="sxs-lookup"><span data-stu-id="cd3d0-113">address</span></span>|<span data-ttu-id="cd3d0-114">エンドポイントのアドレスを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-114">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="cd3d0-115">アドレスは、絶対または相対アドレスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-115">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="cd3d0-116">相対アドレスが提供されている場合、ホストは、そのバインディングで使用されるトランスポート スキームに適したベース アドレスが提供されることを想定します。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-116">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="cd3d0-117">アドレスが構成されていない場合、ベース アドレスはそのエンドポイントのアドレスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-117">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="cd3d0-118">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="cd3d0-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="cd3d0-119">behaviorConfiguration</span></span>|<span data-ttu-id="cd3d0-120">エンドポイントで使用される動作の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-120">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="cd3d0-121">バインド</span><span class="sxs-lookup"><span data-stu-id="cd3d0-121">binding</span></span>|<span data-ttu-id="cd3d0-122">使用するバインディングの種類を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-122">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="cd3d0-123">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-123">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="cd3d0-124">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-124">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="cd3d0-125">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="cd3d0-125">bindingConfiguration</span></span>|<span data-ttu-id="cd3d0-126">エンドポイントがインスタンス化されるときに使用するバインディングのバインディング名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-126">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="cd3d0-127">バインディング名は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-127">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="cd3d0-128">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="cd3d0-129">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="cd3d0-130">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="cd3d0-131">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="cd3d0-132">bindingName</span><span class="sxs-lookup"><span data-stu-id="cd3d0-132">bindingName</span></span>|<span data-ttu-id="cd3d0-133">WSDL を介した定義エクスポートに使用するバインディングの一意の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-133">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="cd3d0-134">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="cd3d0-135">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="cd3d0-135">bindingNamespace</span></span>|<span data-ttu-id="cd3d0-136">WSDL を介した定義エクスポートに使用するバインディングの名前空間の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-136">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="cd3d0-137">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-137">The default is an empty string.</span></span>|  
|<span data-ttu-id="cd3d0-138">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="cd3d0-138">contract</span></span>|<span data-ttu-id="cd3d0-139">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-139">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="cd3d0-140">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-140">The assembly must implement the contract type.</span></span> <span data-ttu-id="cd3d0-141">サービス実装が単一のコントラクトの型を実装する場合は、このプロパティを省略できます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-141">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="cd3d0-142">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-142">The default is an empty string.</span></span>|  
|<span data-ttu-id="cd3d0-143">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="cd3d0-143">endpointConfiguration</span></span>|<span data-ttu-id="cd3d0-144">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-144">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="cd3d0-145">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-145">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="cd3d0-146">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="cd3d0-146">isSystemEndpoint</span></span>|<span data-ttu-id="cd3d0-147">インフラストラクチャ エンドポイントであるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-147">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="cd3d0-148">kind</span><span class="sxs-lookup"><span data-stu-id="cd3d0-148">kind</span></span>|<span data-ttu-id="cd3d0-149">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-149">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="cd3d0-150">種類は `<extensions>` セクションまたは machine.config に登録する必要があります。何も指定されていない場合は、共通のサービス エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-150">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="cd3d0-151">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="cd3d0-151">listenUriMode</span></span>|<span data-ttu-id="cd3d0-152">リッスンするサービスに提供される `ListenUri` をトランスポートが処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-152">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="cd3d0-153">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-153">Valid values are</span></span><br /><br /> <span data-ttu-id="cd3d0-154">-Explicit</span><span class="sxs-lookup"><span data-stu-id="cd3d0-154">-   Explicit</span></span><br /><span data-ttu-id="cd3d0-155">-一意</span><span class="sxs-lookup"><span data-stu-id="cd3d0-155">-   Unique</span></span><br /><br /> <span data-ttu-id="cd3d0-156">既定値は Explicit です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-156">The default value is Explicit.</span></span>|  
|<span data-ttu-id="cd3d0-157">listenUri</span><span class="sxs-lookup"><span data-stu-id="cd3d0-157">listenUri</span></span>|<span data-ttu-id="cd3d0-158">サービス エンドポイントがリッスンする URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-158">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="cd3d0-159">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-159">The default is an empty string.</span></span>|  
|<span data-ttu-id="cd3d0-160">name</span><span class="sxs-lookup"><span data-stu-id="cd3d0-160">name</span></span>|<span data-ttu-id="cd3d0-161">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-161">Optional attribute.</span></span> <span data-ttu-id="cd3d0-162">サービス エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-162">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="cd3d0-163">既定値は、バインディング名とコントラクトの説明の名前を連結した値です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-163">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="cd3d0-164">サービスには複数のエンドポイントが存在する場合があるため、エンドポイントの `name` 属性はサービスの名前とは異なります。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-164">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd3d0-165">子要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-165">Child Elements</span></span>  
  
|<span data-ttu-id="cd3d0-166">要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-166">Element</span></span>|<span data-ttu-id="cd3d0-167">説明</span><span class="sxs-lookup"><span data-stu-id="cd3d0-167">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd3d0-168">\<headers></span><span class="sxs-lookup"><span data-stu-id="cd3d0-168">\<headers></span></span>](headers.md)|<span data-ttu-id="cd3d0-169">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-169">A collection of address headers.</span></span>|  
|[<span data-ttu-id="cd3d0-170">\<identity></span><span class="sxs-lookup"><span data-stu-id="cd3d0-170">\<identity></span></span>](identity.md)|<span data-ttu-id="cd3d0-171">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-171">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd3d0-172">親要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-172">Parent Elements</span></span>  
  
|<span data-ttu-id="cd3d0-173">要素</span><span class="sxs-lookup"><span data-stu-id="cd3d0-173">Element</span></span>|<span data-ttu-id="cd3d0-174">説明</span><span class="sxs-lookup"><span data-stu-id="cd3d0-174">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd3d0-175">\<service></span><span class="sxs-lookup"><span data-stu-id="cd3d0-175">\<service></span></span>](service.md)|<span data-ttu-id="cd3d0-176">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-176">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd3d0-177">例</span><span class="sxs-lookup"><span data-stu-id="cd3d0-177">Example</span></span>  
 <span data-ttu-id="cd3d0-178">これはサービス エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="cd3d0-178">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cd3d0-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="cd3d0-179">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="cd3d0-180">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="cd3d0-180">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="cd3d0-181">方法: 構成にサービスエンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="cd3d0-181">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
