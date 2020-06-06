---
title: <endpoint> の <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855323"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="57fab-102">\<endpoint> の \<client></span><span class="sxs-lookup"><span data-stu-id="57fab-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="57fab-103">サーバーのサービス エンドポイントに接続するためにクライアントによって使用されるチャネル エンドポイントのコントラクト、バインディング、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="57fab-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="57fab-104">構文</span><span class="sxs-lookup"><span data-stu-id="57fab-104">Syntax</span></span>  
  
```xml  
<endpoint address="String"
          behaviorConfiguration="String"
          binding="String"
          bindingConfiguration="String"
          contract="String"
          endpointConfiguration="String"
          kind="String"
          name="String">
</endpoint>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57fab-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="57fab-105">Attributes and Elements</span></span>  
 <span data-ttu-id="57fab-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57fab-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57fab-107">属性</span><span class="sxs-lookup"><span data-stu-id="57fab-107">Attributes</span></span>  
  
|<span data-ttu-id="57fab-108">属性</span><span class="sxs-lookup"><span data-stu-id="57fab-108">Attribute</span></span>|<span data-ttu-id="57fab-109">説明</span><span class="sxs-lookup"><span data-stu-id="57fab-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57fab-110">address</span><span class="sxs-lookup"><span data-stu-id="57fab-110">address</span></span>|<span data-ttu-id="57fab-111">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="57fab-111">Required string attribute.</span></span><br /><br /> <span data-ttu-id="57fab-112">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="57fab-112">Specifies the address of the endpoint.</span></span> <span data-ttu-id="57fab-113">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="57fab-113">The default is an empty string.</span></span> <span data-ttu-id="57fab-114">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-114">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="57fab-115">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="57fab-115">behaviorConfiguration</span></span>|<span data-ttu-id="57fab-116">エンドポイントのインスタンス化に使用される動作の動作名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-116">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="57fab-117">動作名は、サービスが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-117">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="57fab-118">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="57fab-118">The default is an empty string.</span></span>|  
|<span data-ttu-id="57fab-119">binding</span><span class="sxs-lookup"><span data-stu-id="57fab-119">binding</span></span>|<span data-ttu-id="57fab-120">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="57fab-120">Required string attribute.</span></span><br /><br /> <span data-ttu-id="57fab-121">使用するバインディングの種類を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-121">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="57fab-122">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-122">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="57fab-123">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="57fab-123">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="57fab-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="57fab-124">bindingConfiguration</span></span>|<span data-ttu-id="57fab-125">省略可能。</span><span class="sxs-lookup"><span data-stu-id="57fab-125">Optional.</span></span> <span data-ttu-id="57fab-126">エンドポイントがインスタンス化されるときに使用するバインディング構成の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-126">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="57fab-127">バインド構成は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-127">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="57fab-128">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="57fab-128">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="57fab-129">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="57fab-129">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="57fab-130">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="57fab-130">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="57fab-131">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="57fab-131">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="57fab-132">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="57fab-132">contract</span></span>|<span data-ttu-id="57fab-133">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="57fab-133">Required string attribute.</span></span><br /><br /> <span data-ttu-id="57fab-134">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-134">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="57fab-135">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-135">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="57fab-136">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="57fab-136">endpointConfiguration</span></span>|<span data-ttu-id="57fab-137">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-137">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="57fab-138">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-138">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="57fab-139">kind</span><span class="sxs-lookup"><span data-stu-id="57fab-139">kind</span></span>|<span data-ttu-id="57fab-140">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="57fab-140">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="57fab-141">この型は、セクションまたは machine.config に登録する必要があり `<extensions>` ます。何も指定されていない場合は、共通のチャネルエンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="57fab-141">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="57fab-142">name</span><span class="sxs-lookup"><span data-stu-id="57fab-142">name</span></span>|<span data-ttu-id="57fab-143">省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="57fab-143">Optional string attribute.</span></span> <span data-ttu-id="57fab-144">この属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="57fab-144">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="57fab-145">特定のコントラクトの種類に、複数のクライアントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="57fab-145">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="57fab-146">それぞれの定義は、一意の構成名で区別できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57fab-146">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="57fab-147">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="57fab-147">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="57fab-148">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="57fab-148">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="57fab-149">バインディングの `name` 属性は、WSDL を介した定義エクスポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="57fab-149">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57fab-150">子要素</span><span class="sxs-lookup"><span data-stu-id="57fab-150">Child Elements</span></span>  
  
|<span data-ttu-id="57fab-151">要素</span><span class="sxs-lookup"><span data-stu-id="57fab-151">Element</span></span>|<span data-ttu-id="57fab-152">Description</span><span class="sxs-lookup"><span data-stu-id="57fab-152">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="57fab-153">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="57fab-153">A collection of address headers.</span></span>|  
|[\<identity>](identity.md)|<span data-ttu-id="57fab-154">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="57fab-154">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57fab-155">親要素</span><span class="sxs-lookup"><span data-stu-id="57fab-155">Parent Elements</span></span>  
  
|<span data-ttu-id="57fab-156">要素</span><span class="sxs-lookup"><span data-stu-id="57fab-156">Element</span></span>|<span data-ttu-id="57fab-157">Description</span><span class="sxs-lookup"><span data-stu-id="57fab-157">Description</span></span>|  
|-------------|-----------------|  
|[\<client>](client.md)|<span data-ttu-id="57fab-158">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="57fab-158">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57fab-159">例</span><span class="sxs-lookup"><span data-stu-id="57fab-159">Example</span></span>  
 <span data-ttu-id="57fab-160">これはチャネル エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="57fab-160">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="57fab-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="57fab-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="57fab-162">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="57fab-162">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="57fab-163">クライアント</span><span class="sxs-lookup"><span data-stu-id="57fab-163">Clients</span></span>](../../../wcf/feature-details/clients.md)
