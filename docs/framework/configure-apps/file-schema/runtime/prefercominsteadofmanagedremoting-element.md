---
title: <PreferComInsteadOfManagedRemoting> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d793c8d84a15f554ada78f3c0dd1f0e936893fd4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252408"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="ca14e-102">\<PreferComInsteadOfManagedRemoting > 要素</span><span class="sxs-lookup"><span data-stu-id="ca14e-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="ca14e-103">アプリケーションドメインの境界を越えたすべての呼び出しに対して、ランタイムがリモート処理の代わりに COM 相互運用を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="ca14e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca14e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca14e-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca14e-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ca14e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**</span><span class="sxs-lookup"><span data-stu-id="ca14e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca14e-107">構文</span><span class="sxs-lookup"><span data-stu-id="ca14e-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca14e-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca14e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ca14e-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca14e-110">属性</span><span class="sxs-lookup"><span data-stu-id="ca14e-110">Attributes</span></span>  
  
|<span data-ttu-id="ca14e-111">属性</span><span class="sxs-lookup"><span data-stu-id="ca14e-111">Attribute</span></span>|<span data-ttu-id="ca14e-112">説明</span><span class="sxs-lookup"><span data-stu-id="ca14e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ca14e-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ca14e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ca14e-114">アプリケーションドメインの境界を越えて、ランタイムがリモート処理ではなく COM 相互運用を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ca14e-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="ca14e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ca14e-116">値</span><span class="sxs-lookup"><span data-stu-id="ca14e-116">Value</span></span>|<span data-ttu-id="ca14e-117">説明</span><span class="sxs-lookup"><span data-stu-id="ca14e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="ca14e-118">ランタイムは、アプリケーションドメインの境界を越えてリモート処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="ca14e-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="ca14e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="ca14e-120">ランタイムは、アプリケーションドメインの境界を越えて COM 相互運用を使用します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca14e-121">子要素</span><span class="sxs-lookup"><span data-stu-id="ca14e-121">Child Elements</span></span>  
 <span data-ttu-id="ca14e-122">なし。</span><span class="sxs-lookup"><span data-stu-id="ca14e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca14e-123">親要素</span><span class="sxs-lookup"><span data-stu-id="ca14e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ca14e-124">要素</span><span class="sxs-lookup"><span data-stu-id="ca14e-124">Element</span></span>|<span data-ttu-id="ca14e-125">説明</span><span class="sxs-lookup"><span data-stu-id="ca14e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ca14e-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ca14e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ca14e-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca14e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca14e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="ca14e-128">Remarks</span></span>  
 <span data-ttu-id="ca14e-129">`enabled`属性をに設定すると`true`、ランタイムは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="ca14e-130">[Iunknown](https://go.microsoft.com/fwlink/?LinkId=148003)インターフェイスが COM インターフェイス経由でドメインに入るとき、ランタイムは[Imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスに対して[iunknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867)を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="ca14e-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="ca14e-131">代わりに、オブジェクトをラップする[ランタイム呼び出し可能ラッパー](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) を構築します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="ca14e-132">ランタイムは、このドメインで作成さ`QueryInterface`れたすべての[COM 呼び出し可能ラッパー](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) に対して[imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスの呼び出しを受信すると、E_NOINTERFACE を返します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="ca14e-133">これらの2つの動作により、アプリケーションドメインの境界を越えたマネージオブジェクト間の COM インターフェイス経由のすべての呼び出しで、リモート処理ではなく COM と COM の相互運用が使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="ca14e-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca14e-134">例</span><span class="sxs-lookup"><span data-stu-id="ca14e-134">Example</span></span>  
 <span data-ttu-id="ca14e-135">次の例では、ランタイムが分離の境界を越えて COM 相互運用機能を使用するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ca14e-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca14e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca14e-136">See also</span></span>

- [<span data-ttu-id="ca14e-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ca14e-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ca14e-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ca14e-138">Configuration File Schema</span></span>](../index.md)
