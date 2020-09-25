---
title: <service>
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: dcc32f5aa055942408a3f01d37b5aa27ac0f51ee
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173771"
---
# \<service>

<span data-ttu-id="d3b90-101">`service` 要素には Windows Communication Foundation (WCF) サービスの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-101">The `service` element contains the settings for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="d3b90-102">また、サービスを公開するエンドポイントも含まれます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-102">It also contains endpoints that expose the service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<service>**  
  
## <a name="syntax"></a><span data-ttu-id="d3b90-103">構文</span><span class="sxs-lookup"><span data-stu-id="d3b90-103">Syntax</span></span>  
  
```xml  
<service behaviorConfiguration="String"
         name="String">
</service>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3b90-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d3b90-104">Attributes and Elements</span></span>  

 <span data-ttu-id="d3b90-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3b90-106">属性</span><span class="sxs-lookup"><span data-stu-id="d3b90-106">Attributes</span></span>  
  
|<span data-ttu-id="d3b90-107">属性</span><span class="sxs-lookup"><span data-stu-id="d3b90-107">Attribute</span></span>|<span data-ttu-id="d3b90-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="d3b90-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3b90-109">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3b90-109">behaviorConfiguration</span></span>|<span data-ttu-id="d3b90-110">サービスのインスタンス化に使用される動作の動作名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="d3b90-110">A string that contains the behavior name of the behavior to be used to instantiate the service.</span></span> <span data-ttu-id="d3b90-111">動作名は、サービスが定義される時点でスコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3b90-111">The behavior name must be in scope at the point the service is defined.</span></span> <span data-ttu-id="d3b90-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-112">The default value is an empty string.</span></span>|  
|<span data-ttu-id="d3b90-113">name</span><span class="sxs-lookup"><span data-stu-id="d3b90-113">name</span></span>|<span data-ttu-id="d3b90-114">インスタンス化するサービスの型を指定する必須の文字列属性。</span><span class="sxs-lookup"><span data-stu-id="d3b90-114">Required String attribute that specifies the type of the service to be instantiated.</span></span> <span data-ttu-id="d3b90-115">この設定は有効な型と同じでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="d3b90-115">This setting must equate to a valid type.</span></span> <span data-ttu-id="d3b90-116">形式は、`Namespace.Class.` です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-116">The format should be `Namespace.Class.`</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3b90-117">子要素</span><span class="sxs-lookup"><span data-stu-id="d3b90-117">Child Elements</span></span>  
  
|<span data-ttu-id="d3b90-118">要素</span><span class="sxs-lookup"><span data-stu-id="d3b90-118">Element</span></span>|<span data-ttu-id="d3b90-119">説明</span><span class="sxs-lookup"><span data-stu-id="d3b90-119">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="d3b90-120">このサービスを公開する `endpoint` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="d3b90-120">A collection of `endpoint` elements that expose this service.</span></span>|  
|[\<host>](host.md)|<span data-ttu-id="d3b90-121">このサービス インスタンスのホストを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-121">Specifies the host of this service instance.</span></span> <span data-ttu-id="d3b90-122">この要素は <xref:System.ServiceModel.Configuration.HostElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-122">This element is of type <xref:System.ServiceModel.Configuration.HostElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3b90-123">親要素</span><span class="sxs-lookup"><span data-stu-id="d3b90-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d3b90-124">要素</span><span class="sxs-lookup"><span data-stu-id="d3b90-124">Element</span></span>|<span data-ttu-id="d3b90-125">説明</span><span class="sxs-lookup"><span data-stu-id="d3b90-125">Description</span></span>|  
|-------------|-----------------|  
|[\<services>](services.md)|<span data-ttu-id="d3b90-126">すべての WCF 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-126">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3b90-127">解説</span><span class="sxs-lookup"><span data-stu-id="d3b90-127">Remarks</span></span>  

 <span data-ttu-id="d3b90-128">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-128">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d3b90-129">アセンブリには、任意の数のサービスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-129">An assembly can contain any number of services.</span></span> <span data-ttu-id="d3b90-130">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="d3b90-130">Each service has its own `service` configuration section.</span></span> <span data-ttu-id="d3b90-131">このセクションとその内容は、サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-131">This section and its content define the service contract, behavior, and endpoints of the particular service.</span></span>  
  
 <span data-ttu-id="d3b90-132">`behaviorConfiguration` 要素も省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-132">The `behaviorConfiguration` element is also optional.</span></span> <span data-ttu-id="d3b90-133">サービスが使用する動作を識別します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-133">It identifies the behavior the service uses.</span></span> <span data-ttu-id="d3b90-134">この属性で指定された動作は、同じ設定ファイルの範囲にある動作にリンクしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3b90-134">The behavior specified in this attribute must link to a behavior in scope in the same configuration file.</span></span>  
  
 <span data-ttu-id="d3b90-135">各サービスでは、固有のアドレスとバインディングを持つ 1 つまたは複数のエンドポイントが公開されます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-135">Each service exposes one or more endpoints, which has its own address and binding.</span></span> <span data-ttu-id="d3b90-136">構成ファイル内で使用されるすべてのバインディングは、そのファイルのスコープ内で定義される必要があります。</span><span class="sxs-lookup"><span data-stu-id="d3b90-136">All bindings used within the configuration file must be defined in the scope of the file.</span></span> <span data-ttu-id="d3b90-137">バインディングは、`name` 属性と `bindingConfiguration` 属性の組み合わせによってエンドポイントにリンクされます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-137">Binding are linked to endpoints through the combination of the attributes `name` and `bindingConfiguration`.</span></span> <span data-ttu-id="d3b90-138">`name` 属性は、バインディングが定義されているセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-138">The `name` attribute describes the section the binding is defined in.</span></span> <span data-ttu-id="d3b90-139">`bindingConfiguration` 属性は、バインディング セクション内の使用される構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="d3b90-139">The `bindingConfiguration` attribute defines which configuration within the binding section is used.</span></span> <span data-ttu-id="d3b90-140">バインディング セクションでは、複数の設定を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d3b90-140">A binding section can define several configurations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3b90-141">例</span><span class="sxs-lookup"><span data-stu-id="d3b90-141">Example</span></span>  

 <span data-ttu-id="d3b90-142">これはサービスの構成の例です。</span><span class="sxs-lookup"><span data-stu-id="d3b90-142">This is an example of a service configuration.</span></span>  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"
         name="HelloWorld">
  <endpoint address="/HelloWorld2/"
            name="test"
            bindingNamespace="http://www.cohowinery.com/"
            binding="basicHttpBinding"
            contract="IHelloWorld" />
</service>
```  
  
## <a name="see-also"></a><span data-ttu-id="d3b90-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3b90-143">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceElement>
- [<span data-ttu-id="d3b90-144">サービスの構成</span><span class="sxs-lookup"><span data-stu-id="d3b90-144">Configuring Services</span></span>](../../../wcf/configuring-services.md)
