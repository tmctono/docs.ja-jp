---
title: <comContract>
ms.date: 03/30/2017
ms.assetid: 3f8e1c0c-cfdf-4c79-ac65-c64e9323a51c
ms.openlocfilehash: 8694f83a731363f83cb09de43214eb4b211ef5ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704285"
---
# <a name="comcontract"></a><span data-ttu-id="92262-101">\<comContract></span><span class="sxs-lookup"><span data-stu-id="92262-101">\<comContract></span></span>
<span data-ttu-id="92262-102">COM+ 統合サービス コントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="92262-102">Specifies a COM+ integration service contract.</span></span>  
  
 <span data-ttu-id="92262-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="92262-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="92262-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="92262-104">\<comContracts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92262-105">構文</span><span class="sxs-lookup"><span data-stu-id="92262-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92262-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="92262-106">Attributes and Elements</span></span>  
 <span data-ttu-id="92262-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="92262-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92262-108">属性</span><span class="sxs-lookup"><span data-stu-id="92262-108">Attributes</span></span>  
  
|<span data-ttu-id="92262-109">属性</span><span class="sxs-lookup"><span data-stu-id="92262-109">Attribute</span></span>|<span data-ttu-id="92262-110">説明</span><span class="sxs-lookup"><span data-stu-id="92262-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="92262-111">コントラクト</span><span class="sxs-lookup"><span data-stu-id="92262-111">contract</span></span>|<span data-ttu-id="92262-112">コントラクトの種類を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="92262-112">A string that contains the contract type.</span></span>|  
|<span data-ttu-id="92262-113">name</span><span class="sxs-lookup"><span data-stu-id="92262-113">name</span></span>|<span data-ttu-id="92262-114">コントラクト名を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="92262-114">A string that contains the contract name.</span></span>|  
|<span data-ttu-id="92262-115">namespace</span><span class="sxs-lookup"><span data-stu-id="92262-115">namespace</span></span>|<span data-ttu-id="92262-116">コントラクトの名前空間を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="92262-116">A string that contains the contract namespace.</span></span>|  
|<span data-ttu-id="92262-117">requiresSession</span><span class="sxs-lookup"><span data-stu-id="92262-117">requiresSession</span></span>|<span data-ttu-id="92262-118">コントラクトをセッションの多いバインディングでのみ使用できるかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="92262-118">A Boolean value that specifies whether the contract can only be used on sessionful bindings.</span></span> <span data-ttu-id="92262-119">サービスが初期化される場合、統合ランタイムは、この設定が、使用されるバインディングの種類と一貫していることを保証します。</span><span class="sxs-lookup"><span data-stu-id="92262-119">When the service is initialized, the integration runtime ensures that this setting is consistent with the type of binding to be used.</span></span> <span data-ttu-id="92262-120">コントラクト内の 1 つ以上のバインディングが競合する場合は、例外が生成されます。</span><span class="sxs-lookup"><span data-stu-id="92262-120">An exception is generated if one or more of the bindings for the contract are in conflict.</span></span> <span data-ttu-id="92262-121">このプロパティが `false` で、一方向のチャネルを使用し、いずれかの [out] パラメーターが存在する場合は、例外も発生します。</span><span class="sxs-lookup"><span data-stu-id="92262-121">If this property is `false`, and a one-way channel is in use and there are any [out] parameters, an exception is also generated.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92262-122">子要素</span><span class="sxs-lookup"><span data-stu-id="92262-122">Child Elements</span></span>  
  
|<span data-ttu-id="92262-123">要素</span><span class="sxs-lookup"><span data-stu-id="92262-123">Element</span></span>|<span data-ttu-id="92262-124">説明</span><span class="sxs-lookup"><span data-stu-id="92262-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92262-125">persistableTypes</span><span class="sxs-lookup"><span data-stu-id="92262-125">persistableTypes</span></span>|<span data-ttu-id="92262-126">すべての永続型。</span><span class="sxs-lookup"><span data-stu-id="92262-126">All the persistable types.</span></span>|  
|<span data-ttu-id="92262-127">userDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="92262-127">userDefinedTypes</span></span>|<span data-ttu-id="92262-128">サービス コントラクトに含まれるユーザー定義型 (UDT) のコレクション。</span><span class="sxs-lookup"><span data-stu-id="92262-128">A collection of User Defined Types (UDT) that is to be included in the service contract.</span></span>|  
|<span data-ttu-id="92262-129">exposedMethods</span><span class="sxs-lookup"><span data-stu-id="92262-129">exposedMethods</span></span>|<span data-ttu-id="92262-130">COM+ コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM+ メソッドのコレクション。</span><span class="sxs-lookup"><span data-stu-id="92262-130">A collection of COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92262-131">親要素</span><span class="sxs-lookup"><span data-stu-id="92262-131">Parent Elements</span></span>  
  
|<span data-ttu-id="92262-132">要素</span><span class="sxs-lookup"><span data-stu-id="92262-132">Element</span></span>|<span data-ttu-id="92262-133">説明</span><span class="sxs-lookup"><span data-stu-id="92262-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="92262-134">comContracts</span><span class="sxs-lookup"><span data-stu-id="92262-134">comContracts</span></span>|<span data-ttu-id="92262-135">`comContract` 要素のコレクションを含みます。</span><span class="sxs-lookup"><span data-stu-id="92262-135">Contains a collection of `comContract` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92262-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="92262-136">Remarks</span></span>  
 <span data-ttu-id="92262-137">COM + 統合サービス コントラクトは、現在に制限されて、`http://tempuri.org`名前空間、およびコントラクト名がサポートする COM インターフェイスから派生します。</span><span class="sxs-lookup"><span data-stu-id="92262-137">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="92262-138">ただし、構成ファイルの `comContracts` セクションと `comContract` 要素を使用して代替を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="92262-138">You can, however, specify alternatives by using the `comContracts` section, as well as the `comContract` element in the configuration file.</span></span> <span data-ttu-id="92262-139">たとえば、次の構成を使用して、名前空間、コントラクト名、組み込まれるユーザー定義型、およびサービス コントラクトのその他の設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="92262-139">For example, you can use the following configuration to specify the namespace, contract name, and user defined types to be included, as well as other settings for a service contract.</span></span>  
  
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
  
 <span data-ttu-id="92262-140">サービスが初期化される場合、指定した名前空間およびコントラクト名が、生成されるサービスの説明に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92262-140">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92262-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="92262-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="92262-142">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="92262-142">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="92262-143">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="92262-143">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="92262-144">方法: COM + サービス設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="92262-144">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
