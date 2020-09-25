---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: 404cc66ce423ba947c2817b56bebb4daf341ef0b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176046"
---
# \<comContracts>

<span data-ttu-id="ac043-101">`comContracts` 構成セクションには、COM+ 統合サービス コントラクトのさまざまなプロパティを指定できる要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac043-101">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="ac043-102">名前空間およびコントラクトの指定</span><span class="sxs-lookup"><span data-stu-id="ac043-102">Specifying Namespace and Contract</span></span>  

 <span data-ttu-id="ac043-103">現在、COM + 統合サービスコントラクトは名前空間に限定され `http://tempuri.org` ており、コントラクト名はサポートする COM インターフェイスから派生します。</span><span class="sxs-lookup"><span data-stu-id="ac043-103">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="ac043-104">ただし、構成ファイルの `comContracts` セクションを使用して候補を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="ac043-104">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="ac043-105">たとえば、次の構成を使用して、サービス コントラクトの名前空間とコントラクト名、およびセッションの多いバインディングで使用させるオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac043-105">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="ac043-106">サービスが初期化される場合、指定した名前空間およびコントラクト名が、生成されるサービスの説明に適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac043-106">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="ac043-107">このセクションが空の場合、サービスの初期化によって、サポートしている COM インターフェイス ID から取得された既定の名前空間およびコントラクト名が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac043-107">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="ac043-108">また、要素を使用し [\<exposedMethod>](exposedmethod.md) て、COM + コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される COM + メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac043-108">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="ac043-109">また、を使用して、 [\<persistableTypes>](persistabletypes.md) 統合で使用される持続可能な型を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac043-109">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="ac043-110">最後に、要素を使用して、 [\<userDefinedType>](userdefinedtype.md) サービスコントラクトに含めるユーザー定義型 (UDT) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ac043-110">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac043-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac043-111">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [\<exposedMethod>](exposedmethod.md)
- [\<persistableTypes>](persistabletypes.md)
- [\<userDefinedType>](userdefinedtype.md)
- [\<comContract>](comcontract.md)
- [<span data-ttu-id="ac043-112">COM + アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="ac043-112">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ac043-113">方法: COM+ サービス設定を構成する</span><span class="sxs-lookup"><span data-stu-id="ac043-113">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
