---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 0b06d61a33cd6a704a5ab0f75d29bde3f72d77fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115857"
---
# <a name="servicemetadata"></a><span data-ttu-id="5ad7e-101">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="5ad7e-101">\<serviceMetadata></span></span>
<span data-ttu-id="5ad7e-102">サービス メタデータと関連情報の公開を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-102">Specifies the publication of service metadata and associated information.</span></span>  
  
<span data-ttu-id="5ad7e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5ad7e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5ad7e-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="5ad7e-104">\<behaviors></span></span>  
<span data-ttu-id="5ad7e-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="5ad7e-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="5ad7e-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ad7e-106">\<behavior></span></span>  
<span data-ttu-id="5ad7e-107">\<serviceMetadata></span><span class="sxs-lookup"><span data-stu-id="5ad7e-107">\<serviceMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad7e-108">構文</span><span class="sxs-lookup"><span data-stu-id="5ad7e-108">Syntax</span></span>  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ad7e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5ad7e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5ad7e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ad7e-111">属性</span><span class="sxs-lookup"><span data-stu-id="5ad7e-111">Attributes</span></span>  
  
|<span data-ttu-id="5ad7e-112">属性</span><span class="sxs-lookup"><span data-stu-id="5ad7e-112">Attribute</span></span>|<span data-ttu-id="5ad7e-113">説明</span><span class="sxs-lookup"><span data-stu-id="5ad7e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ad7e-114">externalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="5ad7e-114">externalMetadataLocation</span></span>|<span data-ttu-id="5ad7e-115">WSDL ファイルの位置を含む URI。これは、自動生成される WSDL の代わりに、WSDL 要求および MEX 要求に応答してユーザーに返されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-115">A Uri that contains the location of a WSDL file, which is returned to the user in response to WSDL and MEX requests instead of the auto-generated WSDL.</span></span> <span data-ttu-id="5ad7e-116">この属性が設定されていない場合は、既定の WSDL が返されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-116">When this attribute is not set, the default WSDL is returned.</span></span> <span data-ttu-id="5ad7e-117">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-117">The default is an empty string.</span></span>|  
|<span data-ttu-id="5ad7e-118">httpGetBinding</span><span class="sxs-lookup"><span data-stu-id="5ad7e-118">httpGetBinding</span></span>|<span data-ttu-id="5ad7e-119">HTTP GET 経由でメタデータを取得する場合に使用するバインディングの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-119">A string that specifies the type of the binding that will be used for metadata retrieval via HTTP GET.</span></span> <span data-ttu-id="5ad7e-120">この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-120">This setting is optional.</span></span> <span data-ttu-id="5ad7e-121">指定しない場合、既定のバインディングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-121">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="5ad7e-122"><xref:System.ServiceModel.Channels.IReplyChannel> をサポートする内部バインディング要素を使用したバインディングでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-122">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="5ad7e-123">さらに、バインディングの <xref:System.ServiceModel.Channels.MessageVersion> プロパティが <xref:System.ServiceModel.Channels.MessageVersion.None%2A> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-123">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="5ad7e-124">httpGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ad7e-124">httpGetBindingConfiguration</span></span>|<span data-ttu-id="5ad7e-125">このバインディングの追加の構成情報を参照する `httpGetBinding` 属性に指定されるバインディングの名前を設定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-125">A string that sets the name of the binding that is specified in the `httpGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="5ad7e-126">同じ名前を `<bindings>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-126">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="5ad7e-127">httpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="5ad7e-127">httpGetEnabled</span></span>|<span data-ttu-id="5ad7e-128">HTTP/Get 要求を使用した取得用にサービス メタデータを公開するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-128">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="5ad7e-129">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-129">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5ad7e-130">httpGetUrl 属性が指定されていない場合、メタデータが公開されるアドレスは、サービス アドレスに "?wsdl" を加えたものになります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-130">If the httpGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="5ad7e-131">たとえば、サービス アドレスが"http://localhost:8080/CalculatorService「,、Http/get メタデータ アドレスは」 http://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-131">For example, if the service address is "http://localhost:8080/CalculatorService", the HTTP/Get metadata address is "http://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="5ad7e-132">場合、このプロパティは`false`サービスのアドレスが HTTP または HTTPS に基づいていない、または"? wsdl"は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-132">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="5ad7e-133">httpGetUrl</span><span class="sxs-lookup"><span data-stu-id="5ad7e-133">httpGetUrl</span></span>|<span data-ttu-id="5ad7e-134">HTTP/Get 要求を使用した取得用にメタデータが公開されるアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-134">A Uri that specifies the address at which the metadata is published for retrieval using an HTTP/Get request.</span></span> <span data-ttu-id="5ad7e-135">相対 URI を指定した場合、サービスのベース アドレスに対する相対として処理されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-135">If a relative Uri is specified it will be treated as relative to the service’s base address.</span></span>|  
|<span data-ttu-id="5ad7e-136">httpsGetBinding</span><span class="sxs-lookup"><span data-stu-id="5ad7e-136">httpsGetBinding</span></span>|<span data-ttu-id="5ad7e-137">HTTPS GET 経由でメタデータを取得する場合に使用するバインディングの種類を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-137">A string that specifies the type of the binding that will be used for metadata retrieval via HTTPS GET.</span></span> <span data-ttu-id="5ad7e-138">この設定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-138">This setting is optional.</span></span> <span data-ttu-id="5ad7e-139">指定しない場合、既定のバインディングが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-139">If it is not specified, the default bindings will be used.</span></span><br /><br /> <span data-ttu-id="5ad7e-140"><xref:System.ServiceModel.Channels.IReplyChannel> をサポートする内部バインディング要素を使用したバインディングでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-140">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="5ad7e-141">さらに、バインディングの <xref:System.ServiceModel.Channels.MessageVersion> プロパティが <xref:System.ServiceModel.Channels.MessageVersion.None%2A> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-141">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>|  
|<span data-ttu-id="5ad7e-142">httpsGetBindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ad7e-142">httpsGetBindingConfiguration</span></span>|<span data-ttu-id="5ad7e-143">このバインディングの追加の構成情報を参照する `httpsGetBinding` 属性に指定されるバインディングの名前を設定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-143">A string that sets the name of the binding that is specified in the `httpsGetBinding` attribute, which references to the additional configuration information of this binding.</span></span> <span data-ttu-id="5ad7e-144">同じ名前を `<bindings>` セクションに定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-144">The same name must be defined in the `<bindings>` section.</span></span>|  
|<span data-ttu-id="5ad7e-145">httpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="5ad7e-145">httpsGetEnabled</span></span>|<span data-ttu-id="5ad7e-146">HTTPS/Get 要求を使用した取得用にサービス メタデータを公開するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-146">A Boolean value that specifies whether to publish service metadata for retrieval using an HTTPS/Get request.</span></span> <span data-ttu-id="5ad7e-147">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-147">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5ad7e-148">httpsGetUrl 属性が指定されていない場合、メタデータが公開されるアドレスは、サービス アドレスに "?wsdl" を加えたものになります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-148">If the httpsGetUrl attribute is not specified, the address at which the metadata is published is the service address plus a "?wsdl".</span></span> <span data-ttu-id="5ad7e-149">たとえば、サービス アドレスが"https://localhost:8080/CalculatorService「,、Http/get メタデータ アドレスは」 https://localhost:8080/CalculatorService?wsdl"。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-149">For example, if the service address is "https://localhost:8080/CalculatorService", the HTTP/Get metadata address is "https://localhost:8080/CalculatorService?wsdl".</span></span><br /><br /> <span data-ttu-id="5ad7e-150">場合、このプロパティは`false`サービスのアドレスが HTTP または HTTPS に基づいていない、または"? wsdl"は無視されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-150">If this property is `false`, or the address of the service is not based on HTTP or HTTPS, "?wsdl" is ignored.</span></span>|  
|<span data-ttu-id="5ad7e-151">httpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="5ad7e-151">httpsGetUrl</span></span>|<span data-ttu-id="5ad7e-152">HTTPS/Get 要求を使用した取得用にメタデータが公開されるアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-152">A Uri that specifies the address at which the metadata is published for retrieval using an HTTPS/Get request.</span></span>|  
|<span data-ttu-id="5ad7e-153">policyVersion</span><span class="sxs-lookup"><span data-stu-id="5ad7e-153">policyVersion</span></span>|<span data-ttu-id="5ad7e-154">使用する WS-Policy 仕様のバージョンを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-154">A string that specifies the version of the WS-Policy specification being used.</span></span> <span data-ttu-id="5ad7e-155">この属性は <xref:System.ServiceModel.Description.PolicyVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-155">This attribute is of type <xref:System.ServiceModel.Description.PolicyVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ad7e-156">子要素</span><span class="sxs-lookup"><span data-stu-id="5ad7e-156">Child Elements</span></span>  
 <span data-ttu-id="5ad7e-157">なし</span><span class="sxs-lookup"><span data-stu-id="5ad7e-157">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ad7e-158">親要素</span><span class="sxs-lookup"><span data-stu-id="5ad7e-158">Parent Elements</span></span>  
  
|<span data-ttu-id="5ad7e-159">要素</span><span class="sxs-lookup"><span data-stu-id="5ad7e-159">Element</span></span>|<span data-ttu-id="5ad7e-160">説明</span><span class="sxs-lookup"><span data-stu-id="5ad7e-160">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ad7e-161">\<behavior></span><span class="sxs-lookup"><span data-stu-id="5ad7e-161">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="5ad7e-162">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-162">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ad7e-163">Remarks</span><span class="sxs-lookup"><span data-stu-id="5ad7e-163">Remarks</span></span>  
 <span data-ttu-id="5ad7e-164">この構成要素を使用すると、サービスのメタデータ公開機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-164">This configuration element allows you to control the metadata publishing features of a service.</span></span> <span data-ttu-id="5ad7e-165">可能性のある機密性の高いサービス メタデータが誤って漏洩を防ぐためには、Windows Communication Foundation (WCF) サービスの既定の構成ではメタデータの公開を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-165">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for Windows Communication Foundation (WCF) services disables metadata publishing.</span></span> <span data-ttu-id="5ad7e-166">この動作は、既定の設定ではセキュリティで保護されますが、同時に、サービスの構成の中でメタデータ発行の動作が明示的に有効化されない限り、サービスの呼び出しに必要なクライアント コードをメタデータ インポート ツール (Svcutil.exe など) を使用して生成できないことも意味します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-166">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span> <span data-ttu-id="5ad7e-167">この構成要素を使用すると、サービスのこの公開動作を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-167">Using this configuration element, you can enable this publishing behavior for your service.</span></span>  
  
 <span data-ttu-id="5ad7e-168">この動作の構成の詳細な例を参照してください。[メタデータ公開動作](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-168">For a detailed example of configuring this behavior, see [Metadata Publishing Behavior](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).</span></span>  
  
 <span data-ttu-id="5ad7e-169">オプションの `httpGetBinding` 属性および `httpsGetBinding` 属性を使用すると、HTTP GET または HTTPS GET を介してメタデータを取得するバインディングを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-169">The optional `httpGetBinding` and `httpsGetBinding` attributes allow you to configure the bindings used for metadata retrieval via HTTP GET (or HTTPS GET).</span></span> <span data-ttu-id="5ad7e-170">これらの属性を指定しない場合、メタデータの取得には、適切な既定のバインディグ (HTTP の場合は `HttpTransportBindingElement`、HTTPS の場合は `HttpsTransportBindingElement`) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-170">If they are not specified, the default bindings (`HttpTransportBindingElement`, in the case of HTTP and `HttpsTransportBindingElement`, in the case of HTTPS) are used for metadata retrieval as appropriate.</span></span> <span data-ttu-id="5ad7e-171">これらの属性は、組み込みの WCF バインディングでは使用できないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-171">Notice that you cannot use these attributes with the built-in WCF bindings.</span></span> <span data-ttu-id="5ad7e-172"><xref:System.ServiceModel.Channels.IReplyChannel> をサポートする内部バインディング要素を使用したバインディングでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-172">Only bindings with inner binding elements that support <xref:System.ServiceModel.Channels.IReplyChannel> will be supported.</span></span> <span data-ttu-id="5ad7e-173">さらに、バインディングの <xref:System.ServiceModel.Channels.MessageVersion> プロパティが <xref:System.ServiceModel.Channels.MessageVersion.None%2A> である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-173">Additionally, the <xref:System.ServiceModel.Channels.MessageVersion> property of the binding must be <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span>  
  
 <span data-ttu-id="5ad7e-174">サービスが悪意のあるユーザーに公開されないようにするために、SSL over HTTP (HTTPS) 機構を使用して転送をセキュリティで保護できます。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-174">To reduce the exposure of a service to malicious users, it is possible to secure the transfer using the SSL over HTTP (HTTPS) mechanism.</span></span> <span data-ttu-id="5ad7e-175">転送を保護するには、まず、サービスをホストしているコンピューターの特定のポートに適切な X.509 証明書をバインドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-175">To do so, you must first bind a suitable X.509 certificate to a specific port on the computer that is hosting the service.</span></span> <span data-ttu-id="5ad7e-176">(詳細については、次を参照してください[Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。)。次に、この要素をサービス構成に追加し、`httpsGetEnabled` 属性を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-176">(For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Second, add this element to the service configuration and set the `httpsGetEnabled` attribute to `true`.</span></span> <span data-ttu-id="5ad7e-177">最後に、次の例に示すように、`httpsGetUrl` 属性をサービス メタデータ エンドポイントの URL に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-177">Finally, set the `httpsGetUrl` attribute to the URL of the service metadata endpoint, as shown in the following example.</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a><span data-ttu-id="5ad7e-178">例</span><span class="sxs-lookup"><span data-stu-id="5ad7e-178">Example</span></span>  
 <span data-ttu-id="5ad7e-179">次の例では、構成を使用してメタデータを公開するサービスを\<serviceMetadata > 要素。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-179">The following example configure a service to expose metadata by using the \<serviceMetadata> element.</span></span> <span data-ttu-id="5ad7e-180">さらに、`IMetadataExchange` コントラクトを WS-MetadataExchange (MEX) プロトコルの実装として公開するエンドポイントも構成します。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-180">It also configures an endpoint to expose the `IMetadataExchange` contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="5ad7e-181">この例では、`mexHttpBinding` を使用します。これは使いやすい標準バインドで、セキュリティ モードが `wsHttpBinding` に設定されている `None` と同等です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-181">The example uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="5ad7e-182">相対アドレスの"mex"が使用されるエンドポイントには、どのに対して解決とサービスのベース アドレスのエンドポイント アドレス `http://localhost/servicemodelsamples/service.svc/mex` です。</span><span class="sxs-lookup"><span data-stu-id="5ad7e-182">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of `http://localhost/servicemodelsamples/service.svc/mex`.</span></span>  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="5ad7e-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ad7e-183">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [<span data-ttu-id="5ad7e-184">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="5ad7e-184">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5ad7e-185">メタデータ公開動作</span><span class="sxs-lookup"><span data-stu-id="5ad7e-185">Metadata Publishing Behavior</span></span>](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
