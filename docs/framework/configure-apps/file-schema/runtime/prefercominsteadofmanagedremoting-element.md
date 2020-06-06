---
title: <PreferComInsteadOfManagedRemoting> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
ms.openlocfilehash: 1376df4efd56734f2b8da9bd76033afcce8a285b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "77452254"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="b7ecf-102">\<PreferComInsteadOfManagedRemoting> 要素</span><span class="sxs-lookup"><span data-stu-id="b7ecf-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="b7ecf-103">アプリケーションドメインの境界を越えたすべての呼び出しに対して、ランタイムがリモート処理の代わりに COM 相互運用を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<PreferComInsteadOfManagedRemoting>**  
  
## <a name="syntax"></a><span data-ttu-id="b7ecf-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7ecf-104">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7ecf-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b7ecf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b7ecf-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7ecf-107">属性</span><span class="sxs-lookup"><span data-stu-id="b7ecf-107">Attributes</span></span>  
  
|<span data-ttu-id="b7ecf-108">属性</span><span class="sxs-lookup"><span data-stu-id="b7ecf-108">Attribute</span></span>|<span data-ttu-id="b7ecf-109">説明</span><span class="sxs-lookup"><span data-stu-id="b7ecf-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b7ecf-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7ecf-111">アプリケーションドメインの境界を越えて、ランタイムがリモート処理ではなく COM 相互運用を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-111">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b7ecf-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="b7ecf-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="b7ecf-113">値</span><span class="sxs-lookup"><span data-stu-id="b7ecf-113">Value</span></span>|<span data-ttu-id="b7ecf-114">Description</span><span class="sxs-lookup"><span data-stu-id="b7ecf-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b7ecf-115">ランタイムは、アプリケーションドメインの境界を越えてリモート処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-115">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="b7ecf-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b7ecf-117">ランタイムは、アプリケーションドメインの境界を越えて COM 相互運用を使用します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-117">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7ecf-118">子要素</span><span class="sxs-lookup"><span data-stu-id="b7ecf-118">Child Elements</span></span>  
 <span data-ttu-id="b7ecf-119">なし。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7ecf-120">親要素</span><span class="sxs-lookup"><span data-stu-id="b7ecf-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b7ecf-121">要素</span><span class="sxs-lookup"><span data-stu-id="b7ecf-121">Element</span></span>|<span data-ttu-id="b7ecf-122">Description</span><span class="sxs-lookup"><span data-stu-id="b7ecf-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7ecf-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b7ecf-124">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7ecf-125">解説</span><span class="sxs-lookup"><span data-stu-id="b7ecf-125">Remarks</span></span>  
 <span data-ttu-id="b7ecf-126">属性をに設定すると `enabled` `true` 、ランタイムは次のように動作します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-126">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
- <span data-ttu-id="b7ecf-127">[Iunknown](/windows/win32/api/unknwn/nn-unknwn-iunknown)インターフェイスが COM インターフェイス経由でドメインに入るとき、ランタイムは[Imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスに対して[iunknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q))を呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-127">The runtime does not call [IUnknown::QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="b7ecf-128">代わりに、オブジェクトをラップする[ランタイム呼び出し可能ラッパー](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) を構築します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-128">Instead, it constructs a [Runtime Callable Wrapper](../../../../standard/native-interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
- <span data-ttu-id="b7ecf-129">ランタイムは、 `QueryInterface` このドメインで作成されたすべての[COM 呼び出し可能ラッパー](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) に対して[imanagedobject](../../../unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスの呼び出しを受信したときに、E_NOINTERFACE を返します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-129">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../standard/native-interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="b7ecf-130">これらの2つの動作により、アプリケーションドメインの境界を越えたマネージオブジェクト間の COM インターフェイス経由のすべての呼び出しで、リモート処理ではなく COM と COM の相互運用が使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-130">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7ecf-131">例</span><span class="sxs-lookup"><span data-stu-id="b7ecf-131">Example</span></span>  
 <span data-ttu-id="b7ecf-132">次の例では、ランタイムが分離の境界を越えて COM 相互運用機能を使用するように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b7ecf-132">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7ecf-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7ecf-133">See also</span></span>

- [<span data-ttu-id="b7ecf-134">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b7ecf-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b7ecf-135">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b7ecf-135">Configuration File Schema</span></span>](../index.md)
