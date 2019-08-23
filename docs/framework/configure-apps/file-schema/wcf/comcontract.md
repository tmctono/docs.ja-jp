---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: ef980c86efad4fda86cf62148e50688fd22afe49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926101"
---
# <a name="comcontract"></a><span data-ttu-id="72cac-101">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="72cac-101">\<comContract></span></span>
<span data-ttu-id="72cac-102">COM+ 統合サービス コントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="72cac-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="72cac-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="72cac-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="72cac-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="72cac-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72cac-105">構文</span><span class="sxs-lookup"><span data-stu-id="72cac-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72cac-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="72cac-106">Attributes and Elements</span></span>  
 <span data-ttu-id="72cac-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="72cac-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72cac-108">属性</span><span class="sxs-lookup"><span data-stu-id="72cac-108">Attributes</span></span>  
  
|<span data-ttu-id="72cac-109">属性</span><span class="sxs-lookup"><span data-stu-id="72cac-109">Attribute</span></span>|<span data-ttu-id="72cac-110">説明</span><span class="sxs-lookup"><span data-stu-id="72cac-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72cac-111">コントラクト (contract)</span><span class="sxs-lookup"><span data-stu-id="72cac-111">contract</span></span>|<span data-ttu-id="72cac-112">コントラクトの種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="72cac-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="72cac-113">name</span><span class="sxs-lookup"><span data-stu-id="72cac-113">name</span></span>|<span data-ttu-id="72cac-114">コントラクト名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="72cac-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="72cac-115">名前空間</span><span class="sxs-lookup"><span data-stu-id="72cac-115">namespace</span></span>|<span data-ttu-id="72cac-116">コントラクトの名前空間を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="72cac-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="72cac-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="72cac-117">requiresSession</span></span>|<span data-ttu-id="72cac-118">コントラクトをセッションの多いバインディングでのみ使用できるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="72cac-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="72cac-119">サービスが初期化される場合、統合ランタイムは、この設定が、使用されるバインディングの種類と一貫していることを保証します。</span><span class="sxs-lookup"><span data-stu-id="72cac-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="72cac-120">コントラクト内の 1 つ以上のバインディングが競合する場合は、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="72cac-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="72cac-121">このプロパティが `false` で、一方向のチャネルを使用し、いずれかの [out] パラメーターが存在する場合は、例外も発生します。</span><span class="sxs-lookup"><span data-stu-id="72cac-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72cac-122">子要素</span><span class="sxs-lookup"><span data-stu-id="72cac-122">Child Elements</span></span>  
  
|<span data-ttu-id="72cac-123">要素</span><span class="sxs-lookup"><span data-stu-id="72cac-123">Element</span></span>|<span data-ttu-id="72cac-124">説明</span><span class="sxs-lookup"><span data-stu-id="72cac-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72cac-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="72cac-125">persistableTypes</span></span>|<span data-ttu-id="72cac-126">すべての永続型。</span><span class="sxs-lookup"><span data-stu-id="72cac-126">All the persistable types.</span></span>|  
|<span data-ttu-id="72cac-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="72cac-127">userDefinedTypes</span></span>|<span data-ttu-id="72cac-128">サービス コントラクトに含まれるユーザー定義型 (UDT) のコレクション。</span><span class="sxs-lookup"><span data-stu-id="72cac-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="72cac-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="72cac-129">exposedMethods</span></span>|<span data-ttu-id="72cac-130">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドのコレクション。</span><span class="sxs-lookup"><span data-stu-id="72cac-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72cac-131">親要素</span><span class="sxs-lookup"><span data-stu-id="72cac-131">Parent Elements</span></span>  
  
|<span data-ttu-id="72cac-132">要素</span><span class="sxs-lookup"><span data-stu-id="72cac-132">Element</span></span>|<span data-ttu-id="72cac-133">説明</span><span class="sxs-lookup"><span data-stu-id="72cac-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="72cac-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="72cac-134">comContracts</span></span>|<span data-ttu-id="72cac-135">`comContract` 要素のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="72cac-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72cac-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="72cac-136">Remarks</span></span>  
 <span data-ttu-id="72cac-137">現在、com + 統合サービスコントラクトは`http://tempuri.org`名前空間に限定されており、コントラクト名はサポートする COM インターフェイスから派生します。</span><span class="sxs-lookup"><span data-stu-id="72cac-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="72cac-138">ただし、構成ファイルの `comContracts` セクションと `comContract` 要素を使用して代替を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="72cac-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="72cac-139">たとえば、次の構成を使用して、名前空間、コントラクト名、組み込まれるユーザー定義型、およびサービス コントラクトのその他の設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="72cac-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="72cac-140">サービスが初期化される場合、指定した名前空間およびコントラクト名が、生成されるサービスの説明に適用されます。</span><span class="sxs-lookup"><span data-stu-id="72cac-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72cac-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="72cac-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="72cac-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="72cac-142">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="72cac-143">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="72cac-143">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="72cac-144">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="72cac-144">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
