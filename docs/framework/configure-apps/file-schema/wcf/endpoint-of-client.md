---
title: <endpoint> の <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: 3af41ad5b5681b08aac44d984372ab5ac66caf5e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231202"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="ed4e8-102">\<エンドポイント > の\<クライアント ></span><span class="sxs-lookup"><span data-stu-id="ed4e8-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="ed4e8-103">サーバーのサービス エンドポイントに接続するためにクライアントによって使用されるチャネル エンドポイントのコントラクト、バインディング、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
 <span data-ttu-id="ed4e8-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ed4e8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ed4e8-105">\<client></span><span class="sxs-lookup"><span data-stu-id="ed4e8-105">\<client></span></span>  
<span data-ttu-id="ed4e8-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="ed4e8-106">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed4e8-107">構文</span><span class="sxs-lookup"><span data-stu-id="ed4e8-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed4e8-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ed4e8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ed4e8-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed4e8-110">属性</span><span class="sxs-lookup"><span data-stu-id="ed4e8-110">Attributes</span></span>  
  
|<span data-ttu-id="ed4e8-111">属性</span><span class="sxs-lookup"><span data-stu-id="ed4e8-111">Attribute</span></span>|<span data-ttu-id="ed4e8-112">説明</span><span class="sxs-lookup"><span data-stu-id="ed4e8-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed4e8-113">アドレス</span><span class="sxs-lookup"><span data-stu-id="ed4e8-113">address</span></span>|<span data-ttu-id="ed4e8-114">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-114">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed4e8-115">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-115">Specifies the address of the endpoint.</span></span> <span data-ttu-id="ed4e8-116">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-116">The default is an empty string.</span></span> <span data-ttu-id="ed4e8-117">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-117">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="ed4e8-118">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed4e8-118">behaviorConfiguration</span></span>|<span data-ttu-id="ed4e8-119">エンドポイントのインスタンス化に使用される動作の動作名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-119">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="ed4e8-120">動作名は、サービスが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-120">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="ed4e8-121">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-121">The default is an empty string.</span></span>|  
|<span data-ttu-id="ed4e8-122">バインド</span><span class="sxs-lookup"><span data-stu-id="ed4e8-122">binding</span></span>|<span data-ttu-id="ed4e8-123">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-123">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed4e8-124">使用するバインディングの種類を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-124">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="ed4e8-125">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-125">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="ed4e8-126">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-126">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="ed4e8-127">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed4e8-127">bindingConfiguration</span></span>|<span data-ttu-id="ed4e8-128">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-128">Optional.</span></span> <span data-ttu-id="ed4e8-129">エンドポイントがインスタンス化されるときに使用するバインディング構成の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-129">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="ed4e8-130">バインド構成は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-130">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="ed4e8-131">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-131">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ed4e8-132">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-132">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="ed4e8-133">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-133">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="ed4e8-134">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-134">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="ed4e8-135">コントラクト</span><span class="sxs-lookup"><span data-stu-id="ed4e8-135">contract</span></span>|<span data-ttu-id="ed4e8-136">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-136">Required string attribute.</span></span><br /><br /> <span data-ttu-id="ed4e8-137">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-137">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="ed4e8-138">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-138">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="ed4e8-139">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="ed4e8-139">endpointConfiguration</span></span>|<span data-ttu-id="ed4e8-140">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-140">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="ed4e8-141">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-141">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="ed4e8-142">kind</span><span class="sxs-lookup"><span data-stu-id="ed4e8-142">kind</span></span>|<span data-ttu-id="ed4e8-143">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-143">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="ed4e8-144">種類は `<extensions>` セクションまたは machine.config に登録する必要があります。何も指定されていない場合は、共通のチャネル エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-144">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="ed4e8-145">name</span><span class="sxs-lookup"><span data-stu-id="ed4e8-145">name</span></span>|<span data-ttu-id="ed4e8-146">省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-146">Optional string attribute.</span></span> <span data-ttu-id="ed4e8-147">この属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-147">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="ed4e8-148">特定のコントラクトの種類に、複数のクライアントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-148">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="ed4e8-149">それぞれの定義は、一意の構成名で区別できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-149">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="ed4e8-150">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-150">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="ed4e8-151">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-151">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="ed4e8-152">バインディングの `name` 属性は、WSDL を介した定義エクスポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-152">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed4e8-153">子要素</span><span class="sxs-lookup"><span data-stu-id="ed4e8-153">Child Elements</span></span>  
  
|<span data-ttu-id="ed4e8-154">要素</span><span class="sxs-lookup"><span data-stu-id="ed4e8-154">Element</span></span>|<span data-ttu-id="ed4e8-155">説明</span><span class="sxs-lookup"><span data-stu-id="ed4e8-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed4e8-156">\<headers></span><span class="sxs-lookup"><span data-stu-id="ed4e8-156">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="ed4e8-157">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-157">A collection of address headers.</span></span>|  
|[<span data-ttu-id="ed4e8-158">\<identity></span><span class="sxs-lookup"><span data-stu-id="ed4e8-158">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ed4e8-159">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-159">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ed4e8-160">親要素</span><span class="sxs-lookup"><span data-stu-id="ed4e8-160">Parent Elements</span></span>  
  
|<span data-ttu-id="ed4e8-161">要素</span><span class="sxs-lookup"><span data-stu-id="ed4e8-161">Element</span></span>|<span data-ttu-id="ed4e8-162">説明</span><span class="sxs-lookup"><span data-stu-id="ed4e8-162">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed4e8-163">\<client></span><span class="sxs-lookup"><span data-stu-id="ed4e8-163">\<client></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|<span data-ttu-id="ed4e8-164">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-164">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ed4e8-165">例</span><span class="sxs-lookup"><span data-stu-id="ed4e8-165">Example</span></span>  
 <span data-ttu-id="ed4e8-166">これはチャネル エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="ed4e8-166">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="ed4e8-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="ed4e8-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="ed4e8-168">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="ed4e8-168">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ed4e8-169">クライアント</span><span class="sxs-lookup"><span data-stu-id="ed4e8-169">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
