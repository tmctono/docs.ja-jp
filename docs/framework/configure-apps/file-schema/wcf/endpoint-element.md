---
title: <endpoint> 要素
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: befebc090900576b1e0f7ca679e1f5f5cd15af9a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183807"
---
# <a name="endpoint-element"></a><span data-ttu-id="4c80d-102">\<endpoint> 要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-102">\<endpoint> element</span></span>

<span data-ttu-id="4c80d-103">サービスの公開に使用されるサービス エンドポイントのバインディング、コントラクト、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="4c80d-103">Specifies binding, contract, and address properties for a service endpoint, which is used to expose services.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="4c80d-104">構文</span><span class="sxs-lookup"><span data-stu-id="4c80d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c80d-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4c80d-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c80d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c80d-107">属性</span><span class="sxs-lookup"><span data-stu-id="4c80d-107">Attributes</span></span>  
  
|<span data-ttu-id="4c80d-108">属性</span><span class="sxs-lookup"><span data-stu-id="4c80d-108">Attribute</span></span>|<span data-ttu-id="4c80d-109">説明</span><span class="sxs-lookup"><span data-stu-id="4c80d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c80d-110">address</span><span class="sxs-lookup"><span data-stu-id="4c80d-110">address</span></span>|<span data-ttu-id="4c80d-111">エンドポイントのアドレスを含む文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-111">A string that contains the address of the endpoint.</span></span> <span data-ttu-id="4c80d-112">アドレスは、絶対または相対アドレスとして指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-112">The address can be specified as an absolute or relative address.</span></span> <span data-ttu-id="4c80d-113">相対アドレスが提供されている場合、ホストは、そのバインディングで使用されるトランスポート スキームに適したベース アドレスが提供されることを想定します。</span><span class="sxs-lookup"><span data-stu-id="4c80d-113">If a relative address is provided, the host is expected to provide a base address appropriate for the transport scheme used in the binding.</span></span> <span data-ttu-id="4c80d-114">アドレスが構成されていない場合、ベース アドレスはそのエンドポイントのアドレスと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-114">If an address is not configured, the base address is assumed to be the address for that endpoint.</span></span><br /><br /> <span data-ttu-id="4c80d-115">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-115">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c80d-116">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c80d-116">behaviorConfiguration</span></span>|<span data-ttu-id="4c80d-117">エンドポイントで使用される動作の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-117">A string that contains the name of the behavior to be used in the endpoint.</span></span>|  
|<span data-ttu-id="4c80d-118">binding</span><span class="sxs-lookup"><span data-stu-id="4c80d-118">binding</span></span>|<span data-ttu-id="4c80d-119">使用するバインディングの種類を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="4c80d-119">Required string attribute that specifies the type of binding to use.</span></span> <span data-ttu-id="4c80d-120">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-120">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="4c80d-121">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-121">The type is the registered by section name, rather than by the type name of the binding.</span></span>|  
|<span data-ttu-id="4c80d-122">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c80d-122">bindingConfiguration</span></span>|<span data-ttu-id="4c80d-123">エンドポイントがインスタンス化されるときに使用するバインディングのバインディング名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-123">A string that specifies the binding name of the binding to use when the endpoint is instantiated.</span></span> <span data-ttu-id="4c80d-124">バインディング名は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-124">The binding name must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="4c80d-125">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-125">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4c80d-126">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-126">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="4c80d-127">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="4c80d-127">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="4c80d-128">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-128">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="4c80d-129">bindingName</span><span class="sxs-lookup"><span data-stu-id="4c80d-129">bindingName</span></span>|<span data-ttu-id="4c80d-130">WSDL を介した定義エクスポートに使用するバインディングの一意の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-130">A string that specifies the unique qualified name of the binding for definition export through WSDL.</span></span> <span data-ttu-id="4c80d-131">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c80d-132">bindingNamespace</span><span class="sxs-lookup"><span data-stu-id="4c80d-132">bindingNamespace</span></span>|<span data-ttu-id="4c80d-133">WSDL を介した定義エクスポートに使用するバインディングの名前空間の修飾名を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-133">A string that specifies the qualified name of the namespace of the binding for definition export through WSDL.</span></span> <span data-ttu-id="4c80d-134">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-134">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c80d-135">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="4c80d-135">contract</span></span>|<span data-ttu-id="4c80d-136">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-136">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="4c80d-137">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-137">The assembly must implement the contract type.</span></span> <span data-ttu-id="4c80d-138">サービス実装が単一のコントラクトの型を実装する場合は、このプロパティを省略できます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-138">If a service implementation implements a single contract type, then this property can be omitted.</span></span> <span data-ttu-id="4c80d-139">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-139">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c80d-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="4c80d-140">endpointConfiguration</span></span>|<span data-ttu-id="4c80d-141">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="4c80d-142">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="4c80d-143">isSystemEndpoint</span><span class="sxs-lookup"><span data-stu-id="4c80d-143">isSystemEndpoint</span></span>|<span data-ttu-id="4c80d-144">インフラストラクチャ エンドポイントであるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="4c80d-144">A Boolean value that specifies whether an endpoint is an infrastructure endpoint.</span></span>|  
|<span data-ttu-id="4c80d-145">kind</span><span class="sxs-lookup"><span data-stu-id="4c80d-145">kind</span></span>|<span data-ttu-id="4c80d-146">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-146">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="4c80d-147">`<extensions>` セクションまたは machine.config に種類を登録する必要があります。何も指定していない場合は、共通のサービス エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4c80d-147">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common service endpoint is created.</span></span>|  
|<span data-ttu-id="4c80d-148">listenUriMode</span><span class="sxs-lookup"><span data-stu-id="4c80d-148">listenUriMode</span></span>|<span data-ttu-id="4c80d-149">リッスンするサービスに提供される `ListenUri` をトランスポートが処理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c80d-149">Specifies how the transport treats the `ListenUri` provided for the service to listen on.</span></span> <span data-ttu-id="4c80d-150">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4c80d-150">Valid values are</span></span><br /><br /> <span data-ttu-id="4c80d-151">-Explicit</span><span class="sxs-lookup"><span data-stu-id="4c80d-151">-   Explicit</span></span><br /><span data-ttu-id="4c80d-152">-一意</span><span class="sxs-lookup"><span data-stu-id="4c80d-152">-   Unique</span></span><br /><br /> <span data-ttu-id="4c80d-153">既定値は Explicit です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-153">The default value is Explicit.</span></span>|  
|<span data-ttu-id="4c80d-154">listenUri</span><span class="sxs-lookup"><span data-stu-id="4c80d-154">listenUri</span></span>|<span data-ttu-id="4c80d-155">サービス エンドポイントがリッスンする URI を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-155">A string that specifies the URI at which the service endpoint listens.</span></span> <span data-ttu-id="4c80d-156">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-156">The default is an empty string.</span></span>|  
|<span data-ttu-id="4c80d-157">name</span><span class="sxs-lookup"><span data-stu-id="4c80d-157">name</span></span>|<span data-ttu-id="4c80d-158">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-158">Optional attribute.</span></span> <span data-ttu-id="4c80d-159">サービス エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="4c80d-159">A string that specifies the name the service endpoint.</span></span> <span data-ttu-id="4c80d-160">既定値は、バインディング名とコントラクトの説明の名前を連結した値です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-160">The default value is the concatenation of the binding name and the contract description name.</span></span> <span data-ttu-id="4c80d-161">サービスには複数のエンドポイントが存在する場合があるため、エンドポイントの `name` 属性はサービスの名前とは異なります。</span><span class="sxs-lookup"><span data-stu-id="4c80d-161">Services may have multiple endpoints, so the endpoint’s `name` attribute is distinct from the name of the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c80d-162">子要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-162">Child Elements</span></span>  
  
|<span data-ttu-id="4c80d-163">要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-163">Element</span></span>|<span data-ttu-id="4c80d-164">説明</span><span class="sxs-lookup"><span data-stu-id="4c80d-164">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="4c80d-165">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="4c80d-165">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="4c80d-166">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-166">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c80d-167">親要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-167">Parent Elements</span></span>  
  
|<span data-ttu-id="4c80d-168">要素</span><span class="sxs-lookup"><span data-stu-id="4c80d-168">Element</span></span>|<span data-ttu-id="4c80d-169">説明</span><span class="sxs-lookup"><span data-stu-id="4c80d-169">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="4c80d-170">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="4c80d-170">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c80d-171">例</span><span class="sxs-lookup"><span data-stu-id="4c80d-171">Example</span></span>  

 <span data-ttu-id="4c80d-172">これはサービス エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="4c80d-172">This is an example of a service endpoint configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4c80d-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c80d-173">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceEndpointElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.Description.ServiceEndpoint>
- [<span data-ttu-id="4c80d-174">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="4c80d-174">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="4c80d-175">方法: 構成にサービス エンドポイントを作成する</span><span class="sxs-lookup"><span data-stu-id="4c80d-175">How to: Create a Service Endpoint in Configuration</span></span>](../../../wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
