---
title: <PreferComInsteadOfManagedRemoting> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b0a394500dbea0d557a33ea8d2e169c2c6561f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674026"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="53168-102">\<PreferComInsteadOfManagedRemoting > 要素</span><span class="sxs-lookup"><span data-stu-id="53168-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="53168-103">かどうか、ランタイムが使用 COM 相互運用機能のリモート処理ではなくすべての呼び出しに対してアプリケーション ドメイン境界を越えてを指定します。</span><span class="sxs-lookup"><span data-stu-id="53168-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="53168-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="53168-104">\<configuration></span></span>  
<span data-ttu-id="53168-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="53168-105">\<runtime></span></span>  
<span data-ttu-id="53168-106">\<PreferComInsteadOfManagedRemoting ></span><span class="sxs-lookup"><span data-stu-id="53168-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53168-107">構文</span><span class="sxs-lookup"><span data-stu-id="53168-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53168-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53168-108">Attributes and Elements</span></span>  
 <span data-ttu-id="53168-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53168-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53168-110">属性</span><span class="sxs-lookup"><span data-stu-id="53168-110">Attributes</span></span>  
  
|<span data-ttu-id="53168-111">属性</span><span class="sxs-lookup"><span data-stu-id="53168-111">Attribute</span></span>|<span data-ttu-id="53168-112">説明</span><span class="sxs-lookup"><span data-stu-id="53168-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="53168-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="53168-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="53168-114">ランタイムがアプリケーション ドメイン境界を越えて、リモート処理ではなく COM 相互運用機能を使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="53168-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="53168-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="53168-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="53168-116">値</span><span class="sxs-lookup"><span data-stu-id="53168-116">Value</span></span>|<span data-ttu-id="53168-117">説明</span><span class="sxs-lookup"><span data-stu-id="53168-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="53168-118">ランタイムは、アプリケーション ドメイン境界を越えて、リモート処理を使用します。</span><span class="sxs-lookup"><span data-stu-id="53168-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="53168-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="53168-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="53168-120">ランタイムは、アプリケーション ドメイン境界を越えて、COM 相互運用機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="53168-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53168-121">子要素</span><span class="sxs-lookup"><span data-stu-id="53168-121">Child Elements</span></span>  
 <span data-ttu-id="53168-122">なし。</span><span class="sxs-lookup"><span data-stu-id="53168-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53168-123">親要素</span><span class="sxs-lookup"><span data-stu-id="53168-123">Parent Elements</span></span>  
  
|<span data-ttu-id="53168-124">要素</span><span class="sxs-lookup"><span data-stu-id="53168-124">Element</span></span>|<span data-ttu-id="53168-125">説明</span><span class="sxs-lookup"><span data-stu-id="53168-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="53168-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="53168-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="53168-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="53168-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53168-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="53168-128">Remarks</span></span>  
 <span data-ttu-id="53168-129">設定すると、`enabled`属性を`true`、次のように、ランタイム。</span><span class="sxs-lookup"><span data-stu-id="53168-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="53168-130">ランタイムは呼び出しません[iunknown::queryinterface](https://go.microsoft.com/fwlink/?LinkID=144867)の[IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)インターフェイスの場合に、 [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003)インターフェイスが COM インターフェイスを使用してドメインを入力します。</span><span class="sxs-lookup"><span data-stu-id="53168-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="53168-131">代わりに、構築、[ランタイム呼び出し可能ラッパー](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="53168-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="53168-132">受信すると、ランタイムは E_NOINTERFACE を返します、`QueryInterface`を呼び出し、 [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md)のいずれかのインターフェイス[COM 呼び出し可能ラッパー](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) このドメインで作成されています。</span><span class="sxs-lookup"><span data-stu-id="53168-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="53168-133">これら 2 つの動作では、アプリケーション ドメインの境界の使用 COM を越えてマネージ オブジェクトとリモート処理ではなく COM 相互運用機能の間のインターフェイスを COM 経由ですべての呼び出しを確認してください。</span><span class="sxs-lookup"><span data-stu-id="53168-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53168-134">例</span><span class="sxs-lookup"><span data-stu-id="53168-134">Example</span></span>  
 <span data-ttu-id="53168-135">次の例では、分離境界を越えて相互運用機能、ランタイムで COM を使用することを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="53168-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="53168-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="53168-136">See also</span></span>

- [<span data-ttu-id="53168-137">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="53168-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="53168-138">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="53168-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
