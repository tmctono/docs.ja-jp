---
title: <startup> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: cd91abb288c1cfb281f17f2fce95d4956908468f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550847"
---
# <a name="startup-element"></a><span data-ttu-id="b5bdd-102">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-102">\<startup> element</span></span>

<span data-ttu-id="b5bdd-103">共通言語ランタイムのスタートアップ情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-103">Specifies common language runtime startup information.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<startup>**  

## <a name="syntax"></a><span data-ttu-id="b5bdd-104">構文</span><span class="sxs-lookup"><span data-stu-id="b5bdd-104">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b5bdd-105">属性と要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-105">Attributes and elements</span></span>

 <span data-ttu-id="b5bdd-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b5bdd-107">属性</span><span class="sxs-lookup"><span data-stu-id="b5bdd-107">Attributes</span></span>

|<span data-ttu-id="b5bdd-108">属性</span><span class="sxs-lookup"><span data-stu-id="b5bdd-108">Attribute</span></span>|<span data-ttu-id="b5bdd-109">説明</span><span class="sxs-lookup"><span data-stu-id="b5bdd-109">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="b5bdd-110">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b5bdd-111">.NET Framework 2.0 ランタイムアクティブ化ポリシーを有効にするか、.NET Framework 4 のアクティブ化ポリシーを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-111">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b5bdd-112">useLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="b5bdd-112">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="b5bdd-113">[値]</span><span class="sxs-lookup"><span data-stu-id="b5bdd-113">Value</span></span>|<span data-ttu-id="b5bdd-114">説明</span><span class="sxs-lookup"><span data-stu-id="b5bdd-114">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="b5bdd-115">選択したランタイムの .NET Framework 2.0 ランタイムアクティブ化ポリシーを有効にします。これは、CLR バージョン2.0 ではなく、レガシランタイムアクティブ化手法 ( [Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)など) を構成ファイルから選択されたランタイムにバインドするためです。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-115">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="b5bdd-116">したがって、CLR バージョン4以降が構成ファイルから選択されている場合、以前のバージョンの .NET Framework で作成された混合モードアセンブリは、選択した CLR バージョンで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-116">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="b5bdd-117">この値を設定すると、CLR バージョン1.1 または CLR バージョン2.0 を同じプロセスに読み込むことができなくなり、インプロセスサイドバイサイド機能が実質的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-117">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="b5bdd-118">.NET Framework 4 以降の既定のアクティブ化ポリシーを使用します。これは、従来のランタイムアクティブ化手法で CLR バージョン1.1 または2.0 をプロセスに読み込むことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-118">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="b5bdd-119">この値を設定すると、.NET Framework 4 以降でビルドされた場合を除き、混合モードのアセンブリが .NET Framework 4 以降に読み込まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-119">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="b5bdd-120">この値が既定値です。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-120">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b5bdd-121">子要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-121">Child elements</span></span>

|<span data-ttu-id="b5bdd-122">要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-122">Element</span></span>|<span data-ttu-id="b5bdd-123">説明</span><span class="sxs-lookup"><span data-stu-id="b5bdd-123">Description</span></span>|
|-------------|-----------------|
|[\<requiredRuntime>](requiredruntime-element.md)|<span data-ttu-id="b5bdd-124">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-124">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="b5bdd-125">ランタイムバージョン1.1 以降でビルドされたアプリケーションでは、要素を使用する必要があり **\<supportedRuntime>** ます。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-125">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[\<supportedRuntime>](supportedruntime-element.md)|<span data-ttu-id="b5bdd-126">アプリケーションでサポートされる共通言語ランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-126">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b5bdd-127">親要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-127">Parent elements</span></span>

|<span data-ttu-id="b5bdd-128">要素</span><span class="sxs-lookup"><span data-stu-id="b5bdd-128">Element</span></span>|<span data-ttu-id="b5bdd-129">説明</span><span class="sxs-lookup"><span data-stu-id="b5bdd-129">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b5bdd-130">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b5bdd-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="b5bdd-131">Remarks</span></span>

 <span data-ttu-id="b5bdd-132">要素は、 **\<supportedRuntime>** ランタイムのバージョン1.1 以降を使用してビルドされたすべてのアプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-132">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="b5bdd-133">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、要素を使用する必要があり **\<requiredRuntime>** ます。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-133">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="b5bdd-134">Microsoft Internet Explorer でホストされているアプリケーションのスタートアップコードは、 **\<startup>** 要素とその子要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-134">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b5bdd-135">UseLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="b5bdd-135">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="b5bdd-136">この属性は、アプリケーションが [Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)などの従来のアクティブ化パスを使用していて、以前のバージョンではなく CLR のバージョン4をアクティブ化する必要がある場合、またはアプリケーションが .NET Framework 4 でビルドされていて、以前のバージョンの .NET Framework でビルドされた混合モードのアセンブリに依存している場合</span><span class="sxs-lookup"><span data-stu-id="b5bdd-136">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="b5bdd-137">これらのシナリオでは、属性をに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-137">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="b5bdd-138">属性をに設定すると、 `true` clr バージョン1.1 または clr バージョン2.0 が同じプロセスに読み込むことができなくなります。つまり、インプロセスサイドバイサイドの機能が実質的に無効になります (「 [COM 相互運用機能の side-by-side 実行](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-138">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="b5bdd-139">例</span><span class="sxs-lookup"><span data-stu-id="b5bdd-139">Example</span></span>

 <span data-ttu-id="b5bdd-140">次の例は、構成ファイルでランタイムバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b5bdd-140">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b5bdd-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5bdd-141">See also</span></span>

- [<span data-ttu-id="b5bdd-142">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b5bdd-142">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b5bdd-143">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b5bdd-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b5bdd-144">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="b5bdd-144">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="b5bdd-145">[COM 相互運用機能の side-by-side 実行](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b5bdd-145">[Side-by-Side Execution for COM Interop](/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="b5bdd-146">インプロセスの side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="b5bdd-146">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
