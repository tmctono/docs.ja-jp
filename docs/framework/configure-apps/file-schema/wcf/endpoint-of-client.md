---
title: <endpoint> の <client>
ms.date: 03/30/2017
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
ms.openlocfilehash: f1ffbc1e8efac70523d7f631c8cf9ba9a1622bfc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855323"
---
# <a name="endpoint-of-client"></a><span data-ttu-id="7dcc9-102">\<クライアント > の\<エンドポイント ></span><span class="sxs-lookup"><span data-stu-id="7dcc9-102">\<endpoint> of \<client></span></span>
<span data-ttu-id="7dcc9-103">サーバーのサービス エンドポイントに接続するためにクライアントによって使用されるチャネル エンドポイントのコントラクト、バインディング、およびアドレスのプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-103">Specifies contract, binding, and address properties of the channel endpoint, which is used by clients to connect to service endpoints on the server.</span></span>  
  
<span data-ttu-id="7dcc9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7dcc9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7dcc9-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7dcc9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7dcc9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="7dcc9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7dcc9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<エンドポイント >**</span><span class="sxs-lookup"><span data-stu-id="7dcc9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dcc9-108">構文</span><span class="sxs-lookup"><span data-stu-id="7dcc9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dcc9-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7dcc9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7dcc9-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dcc9-111">属性</span><span class="sxs-lookup"><span data-stu-id="7dcc9-111">Attributes</span></span>  
  
|<span data-ttu-id="7dcc9-112">属性</span><span class="sxs-lookup"><span data-stu-id="7dcc9-112">Attribute</span></span>|<span data-ttu-id="7dcc9-113">説明</span><span class="sxs-lookup"><span data-stu-id="7dcc9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dcc9-114">address</span><span class="sxs-lookup"><span data-stu-id="7dcc9-114">address</span></span>|<span data-ttu-id="7dcc9-115">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-115">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7dcc9-116">エンドポイントのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-116">Specifies the address of the endpoint.</span></span> <span data-ttu-id="7dcc9-117">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-117">The default is an empty string.</span></span> <span data-ttu-id="7dcc9-118">アドレスは、絶対 URI にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-118">The address must be an absolute URI.</span></span>|  
|<span data-ttu-id="7dcc9-119">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dcc9-119">behaviorConfiguration</span></span>|<span data-ttu-id="7dcc9-120">エンドポイントのインスタンス化に使用される動作の動作名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-120">A string that contains the behavior name of the behavior to be used to instantiate the endpoint.</span></span> <span data-ttu-id="7dcc9-121">動作名は、サービスが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-121">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="7dcc9-122">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-122">The default is an empty string.</span></span>|  
|<span data-ttu-id="7dcc9-123">バインド</span><span class="sxs-lookup"><span data-stu-id="7dcc9-123">binding</span></span>|<span data-ttu-id="7dcc9-124">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-124">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7dcc9-125">使用するバインディングの種類を示す文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-125">A string that indicates the type of binding to use.</span></span> <span data-ttu-id="7dcc9-126">参照できるようにするには、種類は登録された構成セクションを持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-126">The type must have a registered configuration section in order to be referenced.</span></span> <span data-ttu-id="7dcc9-127">種類は、バインディングの種類の名前ではなくセクション名で登録されます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-127">The type is registered by section name, instead of by the type name of the binding.</span></span>|  
|<span data-ttu-id="7dcc9-128">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dcc9-128">bindingConfiguration</span></span>|<span data-ttu-id="7dcc9-129">任意。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-129">Optional.</span></span> <span data-ttu-id="7dcc9-130">エンドポイントがインスタンス化されるときに使用するバインディング構成の名前を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-130">A string that contains the name of the binding configuration to be used when the endpoint is instantiated.</span></span> <span data-ttu-id="7dcc9-131">バインド構成は、エンドポイントが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-131">The binding configuration must be in scope at the point the endpoint is defined.</span></span> <span data-ttu-id="7dcc9-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-132">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7dcc9-133">この属性は、構成ファイル内の特定のバインディング構成を参照するために、`binding` と組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-133">This attribute is used in conjunction with `binding` to reference a specific binding configuration in the configuration file.</span></span> <span data-ttu-id="7dcc9-134">カスタム バインドを使用しようとする場合にこの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-134">Set this attribute if you are attempting to use a custom binding.</span></span> <span data-ttu-id="7dcc9-135">そうでない場合は、例外がスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-135">Otherwise, an exception may be thrown.</span></span>|  
|<span data-ttu-id="7dcc9-136">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="7dcc9-136">contract</span></span>|<span data-ttu-id="7dcc9-137">必須の文字列属性です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-137">Required string attribute.</span></span><br /><br /> <span data-ttu-id="7dcc9-138">このエンドポイントが公開するコントラクトを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-138">A string that indicates which contract this endpoint is exposing.</span></span> <span data-ttu-id="7dcc9-139">アセンブリは、コントラクト型を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-139">The assembly must implement the contract type.</span></span>|  
|<span data-ttu-id="7dcc9-140">endpointConfiguration</span><span class="sxs-lookup"><span data-stu-id="7dcc9-140">endpointConfiguration</span></span>|<span data-ttu-id="7dcc9-141">この標準エンドポイントの追加の構成情報を参照する `kind` 属性によって設定される標準エンドポイントの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-141">A string that specifies the name of the standard endpoint that is set by the `kind` attribute, which references to the additional configuration information of this standard endpoint.</span></span> <span data-ttu-id="7dcc9-142">同じ名前を `<standardEndpoints>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-142">The same name must be defined in the `<standardEndpoints>` section.</span></span>|  
|<span data-ttu-id="7dcc9-143">kind</span><span class="sxs-lookup"><span data-stu-id="7dcc9-143">kind</span></span>|<span data-ttu-id="7dcc9-144">適用する標準エンドポイントの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-144">A string that specifies the type of standard endpoint applied.</span></span> <span data-ttu-id="7dcc9-145">種類は `<extensions>` セクションまたは machine.config に登録する必要があります。何も指定されていない場合は、共通のチャネル エンドポイントが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-145">The type must be registered in the `<extensions>` section or in machine.config. If nothing is specified, a common channel endpoint is created.</span></span>|  
|<span data-ttu-id="7dcc9-146">name</span><span class="sxs-lookup"><span data-stu-id="7dcc9-146">name</span></span>|<span data-ttu-id="7dcc9-147">省略可能な文字列属性。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-147">Optional string attribute.</span></span> <span data-ttu-id="7dcc9-148">この属性は、特定のコントラクトのエンドポイントを一意に識別します。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-148">This attribute uniquely identifies an endpoint for a given contract.</span></span> <span data-ttu-id="7dcc9-149">特定のコントラクトの種類に、複数のクライアントを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-149">You can define multiple clients for a given Contract type.</span></span> <span data-ttu-id="7dcc9-150">それぞれの定義は、一意の構成名で区別できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-150">Each definition must be differentiated by a unique configuration name.</span></span> <span data-ttu-id="7dcc9-151">この属性が省略されている場合、指定されたコントラクトの種類に関連する既定のエンドポイントとして、対応するエンドポイントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-151">If this attribute is omitted, the corresponding endpoint is used as the default endpoint associated with the specified Contract type.</span></span> <span data-ttu-id="7dcc9-152">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-152">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="7dcc9-153">バインディングの `name` 属性は、WSDL を介した定義エクスポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-153">The `name` attribute of a binding is used for definition export through WSDL.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dcc9-154">子要素</span><span class="sxs-lookup"><span data-stu-id="7dcc9-154">Child Elements</span></span>  
  
|<span data-ttu-id="7dcc9-155">要素</span><span class="sxs-lookup"><span data-stu-id="7dcc9-155">Element</span></span>|<span data-ttu-id="7dcc9-156">説明</span><span class="sxs-lookup"><span data-stu-id="7dcc9-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dcc9-157">\<headers></span><span class="sxs-lookup"><span data-stu-id="7dcc9-157">\<headers></span></span>](headers.md)|<span data-ttu-id="7dcc9-158">アドレス ヘッダーのコレクション。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-158">A collection of address headers.</span></span>|  
|[<span data-ttu-id="7dcc9-159">\<identity></span><span class="sxs-lookup"><span data-stu-id="7dcc9-159">\<identity></span></span>](identity.md)|<span data-ttu-id="7dcc9-160">メッセージを交換する他のエンドポイントによるエンドポイントの認証を可能にする ID です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-160">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dcc9-161">親要素</span><span class="sxs-lookup"><span data-stu-id="7dcc9-161">Parent Elements</span></span>  
  
|<span data-ttu-id="7dcc9-162">要素</span><span class="sxs-lookup"><span data-stu-id="7dcc9-162">Element</span></span>|<span data-ttu-id="7dcc9-163">説明</span><span class="sxs-lookup"><span data-stu-id="7dcc9-163">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dcc9-164">\<クライアント ></span><span class="sxs-lookup"><span data-stu-id="7dcc9-164">\<client></span></span>](client.md)|<span data-ttu-id="7dcc9-165">クライアントが接続可能なエンドポイントの一覧を定義する設定セクションです。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-165">A configuration section that defines a list of endpoints that a client can connect to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dcc9-166">例</span><span class="sxs-lookup"><span data-stu-id="7dcc9-166">Example</span></span>  
 <span data-ttu-id="7dcc9-167">これはチャネル エンドポイントの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="7dcc9-167">This is an example of a channel endpoint configuration.</span></span>  
  
```xml  
<endpoint address="/HelloWorld/"
          bindingConfiguration="usingDefaults"
          name="MyBinding"
          binding="customBinding"
          contract="HelloWorld">
</endpoint>
```  
  
## <a name="see-also"></a><span data-ttu-id="7dcc9-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dcc9-168">See also</span></span>

- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>
- <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>
- <xref:System.ServiceModel.Configuration.ChannelEndpointElement>
- [<span data-ttu-id="7dcc9-169">WCF クライアントの構成</span><span class="sxs-lookup"><span data-stu-id="7dcc9-169">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="7dcc9-170">クライアント</span><span class="sxs-lookup"><span data-stu-id="7dcc9-170">Clients</span></span>](../../../wcf/feature-details/clients.md)
