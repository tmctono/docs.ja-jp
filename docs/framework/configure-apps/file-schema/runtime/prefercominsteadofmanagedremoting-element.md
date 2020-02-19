---
title: <PreferComInsteadOfManagedRemoting> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452254"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="5004f-102">\<PreferComInsteadOfManagedRemoting > 要素</span><span class="sxs-lookup"><span data-stu-id="5004f-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="5004f-103">アプリケーションドメインの境界を越えたすべての呼び出しに対して、ランタイムがリモート処理の代わりに COM 相互運用を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5004f-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
<span data-ttu-id="5004f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5004f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5004f-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5004f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5004f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<PreferComInsteadOfManagedRemoting >**</span><span class="sxs-lookup"><span data-stu-id="5004f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5004f-107">構文</span><span class="sxs-lookup"><span data-stu-id="5004f-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5004f-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="5004f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5004f-109">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5004f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5004f-110">属性</span><span class="sxs-lookup"><span data-stu-id="5004f-110">Attributes</span></span>  
  
|<span data-ttu-id="5004f-111">属性</span><span class="sxs-lookup"><span data-stu-id="5004f-111">Attribute</span></span>|<span data-ttu-id="5004f-112">説明</span><span class="sxs-lookup"><span data-stu-id="5004f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5004f-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5004f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5004f-114">アプリケーションドメインの境界を越えて、ランタイムがリモート処理ではなく COM 相互運用を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="5004f-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5004f-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="5004f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5004f-116">値</span><span class="sxs-lookup"><span data-stu-id="5004f-116">Value</span></span>|<span data-ttu-id="5004f-117">説明</span><span class="sxs-lookup"><span data-stu-id="5004f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5004f-118">ランタイムは、アプリケーションドメインの境界を越えてリモート処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="5004f-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="5004f-119">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="5004f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5004f-120">ランタイムは、アプリケーションドメインの境界を越えて COM 相互運用を使用します。</span><span class="sxs-lookup"><span data-stu-id="5004f-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5004f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="5004f-121">Child Elements</span></span>  
 <span data-ttu-id="5004f-122">[なし]。</span><span class="sxs-lookup"><span data-stu-id="5004f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5004f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5004f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5004f-124">要素</span><span class="sxs-lookup"><span data-stu-id="5004f-124">Element</span></span>|<span data-ttu-id="5004f-125">説明</span><span class="sxs-lookup"><span data-stu-id="5004f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5004f-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5004f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5004f-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5004f-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5004f-128">コメント</span><span class="sxs-lookup"><span data-stu-id="5004f-128">Remarks</span></span>  
 <span data-ttu-id="5004f-129">`enabled` 属性を `true`に設定すると、ランタイムは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="5004f-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="5004f-130">[Iunknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)インターフェイスが COM インターフェイス経由でドメインに入るとき、ランタイムは[Imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスに対して[iunknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="5004f-130">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="5004f-131">代わりに、オブジェクトをラップする[ランタイム呼び出し可能ラッパー](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) を構築します。</span><span class="sxs-lookup"><span data-stu-id="5004f-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="5004f-132">ランタイムは、このドメインで作成されたすべての[COM 呼び出し可能ラッパー](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) に対して[Imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスの `QueryInterface` 呼び出しを受け取ったときに、E_NOINTERFACE を返します。</span><span class="sxs-lookup"><span data-stu-id="5004f-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="5004f-133">これらの2つの動作により、アプリケーションドメインの境界を越えたマネージオブジェクト間の COM インターフェイス経由のすべての呼び出しで、リモート処理ではなく COM と COM の相互運用が使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="5004f-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5004f-134">例</span><span class="sxs-lookup"><span data-stu-id="5004f-134">Example</span></span>  
 <span data-ttu-id="5004f-135">次の例では、ランタイムが分離の境界を越えて COM 相互運用機能を使用するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5004f-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5004f-136">参照</span><span class="sxs-lookup"><span data-stu-id="5004f-136">See also</span></span>

- [<span data-ttu-id="5004f-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5004f-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5004f-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5004f-138">Configuration File Schema</span></span>](../index.md)
