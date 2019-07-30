---
title: <PreferComInsteadOfManagedRemoting> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7a558af17493c955b4f148d0abf7f42c9dd6f8
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629433"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="9b663-102">\<PreferComInsteadOfManagedRemoting > 要素</span><span class="sxs-lookup"><span data-stu-id="9b663-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="9b663-103">アプリケーションドメインの境界を越えたすべての呼び出しに対して、ランタイムがリモート処理の代わりに COM 相互運用を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="9b663-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="9b663-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9b663-104">\<configuration></span></span>  
<span data-ttu-id="9b663-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="9b663-105">\<runtime></span></span>  
<span data-ttu-id="9b663-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="9b663-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b663-107">構文</span><span class="sxs-lookup"><span data-stu-id="9b663-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b663-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9b663-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9b663-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b663-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b663-110">属性</span><span class="sxs-lookup"><span data-stu-id="9b663-110">Attributes</span></span>  
  
|<span data-ttu-id="9b663-111">属性</span><span class="sxs-lookup"><span data-stu-id="9b663-111">Attribute</span></span>|<span data-ttu-id="9b663-112">説明</span><span class="sxs-lookup"><span data-stu-id="9b663-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9b663-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="9b663-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b663-114">アプリケーションドメインの境界を越えて、ランタイムがリモート処理ではなく COM 相互運用を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9b663-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9b663-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="9b663-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="9b663-116">値</span><span class="sxs-lookup"><span data-stu-id="9b663-116">Value</span></span>|<span data-ttu-id="9b663-117">説明</span><span class="sxs-lookup"><span data-stu-id="9b663-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="9b663-118">ランタイムは、アプリケーションドメインの境界を越えてリモート処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b663-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="9b663-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="9b663-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="9b663-120">ランタイムは、アプリケーションドメインの境界を越えて COM 相互運用を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b663-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b663-121">子要素</span><span class="sxs-lookup"><span data-stu-id="9b663-121">Child Elements</span></span>  
 <span data-ttu-id="9b663-122">なし。</span><span class="sxs-lookup"><span data-stu-id="9b663-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b663-123">親要素</span><span class="sxs-lookup"><span data-stu-id="9b663-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9b663-124">要素</span><span class="sxs-lookup"><span data-stu-id="9b663-124">Element</span></span>|<span data-ttu-id="9b663-125">説明</span><span class="sxs-lookup"><span data-stu-id="9b663-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b663-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="9b663-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b663-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b663-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b663-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="9b663-128">Remarks</span></span>  
 <span data-ttu-id="9b663-129">`enabled`属性をに設定すると`true`、ランタイムは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="9b663-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="9b663-130">[Iunknown](https://go.microsoft.com/fwlink/?LinkId=148003)インターフェイスが COM インターフェイス経由でドメインに入るとき、ランタイムは[Imanagedobject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスに対して[iunknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867)を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="9b663-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="9b663-131">代わりに、オブジェクトをラップする[ランタイム呼び出し可能ラッパー](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) を構築します。</span><span class="sxs-lookup"><span data-stu-id="9b663-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="9b663-132">ランタイムは、このドメインで作成さ`QueryInterface`れたすべての[COM 呼び出し可能ラッパー](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) に対して[imanagedobject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスの呼び出しを受信すると、E_NOINTERFACE を返します。</span><span class="sxs-lookup"><span data-stu-id="9b663-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="9b663-133">これらの2つの動作により、アプリケーションドメインの境界を越えたマネージオブジェクト間の COM インターフェイス経由のすべての呼び出しで、リモート処理ではなく COM と COM の相互運用が使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b663-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b663-134">例</span><span class="sxs-lookup"><span data-stu-id="9b663-134">Example</span></span>  
 <span data-ttu-id="9b663-135">次の例では、ランタイムが分離の境界を越えて COM 相互運用機能を使用するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9b663-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b663-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b663-136">See also</span></span>

- [<span data-ttu-id="9b663-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b663-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="9b663-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="9b663-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
