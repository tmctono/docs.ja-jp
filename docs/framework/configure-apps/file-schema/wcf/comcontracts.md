---
title: <comContracts>
ms.date: 03/30/2017
ms.assetid: 42e74148-223d-4888-a8ed-1d928527eb09
ms.openlocfilehash: d061d48374a8745dc61e1ca156e4fcbbccee5ef7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919476"
---
# <a name="comcontracts"></a><span data-ttu-id="c7d53-101">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="c7d53-101">\<comContracts></span></span>
<span data-ttu-id="c7d53-102">`comContracts` 構成セクションには、COM+ 統合サービス コントラクトのさまざまなプロパティを指定できる要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-102">The `comContracts` configuration section contains elements that allow you to specify various properties of a COM+ integration service contract.</span></span>  
  
## <a name="specifying-namespace-and-contract"></a><span data-ttu-id="c7d53-103">名前空間およびコントラクトの指定</span><span class="sxs-lookup"><span data-stu-id="c7d53-103">Specifying Namespace and Contract</span></span>  
 <span data-ttu-id="c7d53-104">現在、com + 統合サービスコントラクトは`http://tempuri.org`名前空間に限定されており、コントラクト名はサポートする COM インターフェイスから派生します。</span><span class="sxs-lookup"><span data-stu-id="c7d53-104">COM+ integration service contracts are currently restricted to the `http://tempuri.org` namespace, and contract name is derived from the supporting COM interface.</span></span> <span data-ttu-id="c7d53-105">ただし、構成ファイルの `comContracts` セクションを使用して候補を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-105">You can, however, specify alternatives by using the `comContracts` section in the configuration file.</span></span>  
  
 <span data-ttu-id="c7d53-106">たとえば、次の構成を使用して、サービス コントラクトの名前空間とコントラクト名、およびセッションの多いバインディングで使用させるオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-106">For example, you can use the following configuration to specify the namespace and contract name of the service contract, as well as an option to enforce usage on sessionful bindings.</span></span>  
  
```xml  
<comContracts>
  <comContract contract="{5163B1E7-F0CF-4B6A-9A02-4AB654F34284}"
               namespace="http://tempuri.org/5163B1E7-F0CF-4B6A-9A02-4AB654F34284"
               name="_Broker"
               requireSession="true">
  </comContract>
</comContracts>
```  
  
 <span data-ttu-id="c7d53-107">サービスが初期化される場合、指定した名前空間およびコントラクト名が、生成されるサービスの説明に適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-107">When the service is initialized, the specified namespaces and contract names are applied to the generated service descriptions.</span></span>  
  
 <span data-ttu-id="c7d53-108">このセクションが空の場合、サービスの初期化によって、サポートしている COM インターフェイス ID から取得された既定の名前空間およびコントラクト名が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-108">When this section is empty, the service initialization applies a default namespace and contract name taken from the supporting COM interface ID.</span></span>  
  
 <span data-ttu-id="c7d53-109">また、 [ \<exposedMethod >](exposedmethod.md)要素を使用して、com + コンポーネントのインターフェイスが Web サービスとして公開されるときに公開される com + メソッドを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-109">In addition, you can use the [\<exposedMethod>](exposedmethod.md) element to specify COM+ methods that are exposed when the interface on a COM+ component is exposed as a Web service.</span></span> <span data-ttu-id="c7d53-110">また、 [ \<persistabletypes >](persistabletypes.md)を使用して、統合で使用される持続可能な型を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-110">You can also use the [\<persistableTypes>](persistabletypes.md) to specify persistable types used in integration.</span></span> <span data-ttu-id="c7d53-111">最後に、 [ \<userdefinedtype >](userdefinedtype.md)要素を使用して、サービスコントラクトに含めるユーザー定義型 (UDT) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c7d53-111">Finally, you can use the [\<userDefinedType>](userdefinedtype.md) element to include User Defined Types (UDT) that are to be included in the service contract.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d53-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7d53-112">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComContractElementCollection>
- <xref:System.ServiceModel.Configuration.ComContractElement>
- [<span data-ttu-id="c7d53-113">\<exposedMethod></span><span class="sxs-lookup"><span data-stu-id="c7d53-113">\<exposedMethod></span></span>](exposedmethod.md)
- [<span data-ttu-id="c7d53-114">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="c7d53-114">\<persistableTypes></span></span>](persistabletypes.md)
- [<span data-ttu-id="c7d53-115">\<userDefinedType></span><span class="sxs-lookup"><span data-stu-id="c7d53-115">\<userDefinedType></span></span>](userdefinedtype.md)
- [<span data-ttu-id="c7d53-116">\<comContract></span><span class="sxs-lookup"><span data-stu-id="c7d53-116">\<comContract></span></span>](comcontract.md)
- [<span data-ttu-id="c7d53-117">COM+ アプリケーションとの統合</span><span class="sxs-lookup"><span data-stu-id="c7d53-117">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="c7d53-118">方法: COM + サービス設定の構成</span><span class="sxs-lookup"><span data-stu-id="c7d53-118">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
