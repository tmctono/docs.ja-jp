---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 35596f32bf0e0de9081bc0d4c33fb370c7ab708b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173784"
---
# \<comContract>

<span data-ttu-id="2a1eb-101">COM+ 統合サービス コントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-101">Specifies a COM+ integration service contract.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<comContract>**  
  
## <a name="syntax"></a><span data-ttu-id="2a1eb-102">構文</span><span class="sxs-lookup"><span data-stu-id="2a1eb-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract contract="String"
               namespace="String"
               name="String"
               requireSession="Boolean">
    <exposedMethods>
      <exposedMethod name="String" />
    </exposedMethods>
    <userDefinedTypes>
      <userDefinedType name="String"
                       typeLibID="String"
                       typeLibVersion="String"
                       typeDefID="String">
      </userDefinedType>
    </userDefinedTypes>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a1eb-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2a1eb-103">Attributes and Elements</span></span>  

 <span data-ttu-id="2a1eb-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a1eb-105">属性</span><span class="sxs-lookup"><span data-stu-id="2a1eb-105">Attributes</span></span>  
  
|<span data-ttu-id="2a1eb-106">属性</span><span class="sxs-lookup"><span data-stu-id="2a1eb-106">Attribute</span></span>|<span data-ttu-id="2a1eb-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="2a1eb-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2a1eb-108">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="2a1eb-108">contract</span></span>|<span data-ttu-id="2a1eb-109">コントラクトの種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-109">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="2a1eb-110">name</span><span class="sxs-lookup"><span data-stu-id="2a1eb-110">name</span></span>|<span data-ttu-id="2a1eb-111">コントラクト名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-111">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="2a1eb-112">namespace</span><span class="sxs-lookup"><span data-stu-id="2a1eb-112">namespace</span></span>|<span data-ttu-id="2a1eb-113">コントラクトの名前空間を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-113">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="2a1eb-114">requiresSession</span><span class="sxs-lookup"><span data-stu-id="2a1eb-114">requiresSession</span></span>|<span data-ttu-id="2a1eb-115">コントラクトをセッションの多いバインディングでのみ使用できるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-115">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="2a1eb-116">サービスが初期化される場合、統合ランタイムは、この設定が、使用されるバインディングの種類と一貫していることを保証します。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-116">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="2a1eb-117">コントラクト内の 1 つ以上のバインディングが競合する場合は、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-117">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="2a1eb-118">このプロパティが `false` で、一方向のチャネルを使用し、いずれかの [out] パラメーターが存在する場合は、例外も発生します。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-118">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a1eb-119">子要素</span><span class="sxs-lookup"><span data-stu-id="2a1eb-119">Child Elements</span></span>  
  
|<span data-ttu-id="2a1eb-120">要素</span><span class="sxs-lookup"><span data-stu-id="2a1eb-120">Element</span></span>|<span data-ttu-id="2a1eb-121">説明</span><span class="sxs-lookup"><span data-stu-id="2a1eb-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a1eb-122">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="2a1eb-122">persistableTypes</span></span>|<span data-ttu-id="2a1eb-123">すべての永続型。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-123">All the persistable types.</span></span>|  
|<span data-ttu-id="2a1eb-124">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="2a1eb-124">userDefinedTypes</span></span>|<span data-ttu-id="2a1eb-125">サービス コントラクトに含まれるユーザー定義型 (UDT) のコレクション。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-125">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="2a1eb-126">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="2a1eb-126">exposedMethods</span></span>|<span data-ttu-id="2a1eb-127">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドのコレクション。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-127">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a1eb-128">親要素</span><span class="sxs-lookup"><span data-stu-id="2a1eb-128">Parent Elements</span></span>  
  
|<span data-ttu-id="2a1eb-129">要素</span><span class="sxs-lookup"><span data-stu-id="2a1eb-129">Element</span></span>|<span data-ttu-id="2a1eb-130">説明</span><span class="sxs-lookup"><span data-stu-id="2a1eb-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a1eb-131">comContracts</span><span class="sxs-lookup"><span data-stu-id="2a1eb-131">comContracts</span></span>|<span data-ttu-id="2a1eb-132">`comContract` 要素のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-132">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a1eb-133">解説</span><span class="sxs-lookup"><span data-stu-id="2a1eb-133">Remarks</span></span>  

 <span data-ttu-id="2a1eb-134">現在、COM + 統合サービスコントラクトは名前空間に限定され `http://tempuri.org` ており、コントラクト名はサポートする COM インターフェイスから派生します。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-134">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="2a1eb-135">ただし、構成ファイルの `comContracts` セクションと `comContract` 要素を使用して代替を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-135">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="2a1eb-136">たとえば、次の構成を使用して、名前空間、コントラクト名、組み込まれるユーザー定義型、およびサービス コントラクトのその他の設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-136">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
    <exposedMethods>
      <exposedMethod name="BuyStock" />
      <exposedMethod name="SellStock" />
      <exposedMethod name="ExecuteTransaction" />
    </exposedMethods>
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="2a1eb-137">サービスが初期化される場合、指定した名前空間およびコントラクト名が、生成されるサービスの説明に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2a1eb-137">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a1eb-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a1eb-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="2a1eb-139">COM + アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="2a1eb-139">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="2a1eb-140">方法: COM+ サービス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="2a1eb-140">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
