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
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699412"
---
# <a name="startup-element"></a><span data-ttu-id="0f7f6-102">\<startup> 要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-102">\<startup> element</span></span>

<span data-ttu-id="0f7f6-103">共通言語ランタイムのスタートアップ情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="0f7f6-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0f7f6-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="0f7f6-105">&nbsp;&nbsp; **\<startup>**</span><span class="sxs-lookup"><span data-stu-id="0f7f6-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="0f7f6-106">構文</span><span class="sxs-lookup"><span data-stu-id="0f7f6-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f7f6-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-107">Attributes and elements</span></span>

 <span data-ttu-id="0f7f6-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f7f6-109">属性</span><span class="sxs-lookup"><span data-stu-id="0f7f6-109">Attributes</span></span>

|<span data-ttu-id="0f7f6-110">属性</span><span class="sxs-lookup"><span data-stu-id="0f7f6-110">Attribute</span></span>|<span data-ttu-id="0f7f6-111">説明</span><span class="sxs-lookup"><span data-stu-id="0f7f6-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="0f7f6-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0f7f6-113">.NET Framework 2.0 ランタイムアクティブ化ポリシーを有効にするか、.NET Framework 4 のアクティブ化ポリシーを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="0f7f6-114">useLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="0f7f6-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="0f7f6-115">値</span><span class="sxs-lookup"><span data-stu-id="0f7f6-115">Value</span></span>|<span data-ttu-id="0f7f6-116">説明</span><span class="sxs-lookup"><span data-stu-id="0f7f6-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="0f7f6-117">選択したランタイムの .NET Framework 2.0 ランタイムアクティブ化ポリシーを有効にします。これは、レガシランタイムアクティベーション手法 ( [Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)など) を CLR ではなく構成ファイルから選択されたランタイムにバインドするために使用します。バージョン2.0。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="0f7f6-118">したがって、CLR バージョン4以降が構成ファイルから選択されている場合、以前のバージョンの .NET Framework で作成された混合モードアセンブリは、選択した CLR バージョンで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="0f7f6-119">この値を設定すると、CLR バージョン1.1 または CLR バージョン2.0 を同じプロセスに読み込むことができなくなり、インプロセスサイドバイサイド機能が実質的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="0f7f6-120">.NET Framework 4 以降の既定のアクティブ化ポリシーを使用します。これは、従来のランタイムアクティブ化手法で CLR バージョン1.1 または2.0 をプロセスに読み込むことができるようにするためです。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="0f7f6-121">この値を設定すると、.NET Framework 4 以降でビルドされた場合を除き、混合モードのアセンブリが .NET Framework 4 以降に読み込まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="0f7f6-122">この値が既定値です。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0f7f6-123">子要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-123">Child elements</span></span>

|<span data-ttu-id="0f7f6-124">要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-124">Element</span></span>|<span data-ttu-id="0f7f6-125">説明</span><span class="sxs-lookup"><span data-stu-id="0f7f6-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f7f6-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="0f7f6-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="0f7f6-127">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="0f7f6-128">ランタイムバージョン1.1 以降でビルドされたアプリケーションでは、 **\<supportedRuntime >** 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="0f7f6-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="0f7f6-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="0f7f6-130">アプリケーションでサポートされる共通言語ランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="0f7f6-131">親要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-131">Parent elements</span></span>

|<span data-ttu-id="0f7f6-132">要素</span><span class="sxs-lookup"><span data-stu-id="0f7f6-132">Element</span></span>|<span data-ttu-id="0f7f6-133">説明</span><span class="sxs-lookup"><span data-stu-id="0f7f6-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0f7f6-134">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0f7f6-135">コメント</span><span class="sxs-lookup"><span data-stu-id="0f7f6-135">Remarks</span></span>

 <span data-ttu-id="0f7f6-136">**@No__t-1supportedRuntime >** 要素は、ランタイムのバージョン1.1 以降を使用してビルドされたすべてのアプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="0f7f6-137">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、 **@no__t 1requiredRuntime >** 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="0f7f6-138">Microsoft Internet Explorer でホストされているアプリケーションのスタートアップコードは、 **\<startup >** 要素とその子要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="0f7f6-139">UseLegacyV2RuntimeActivationPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="0f7f6-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="0f7f6-140">この属性は、アプリケーションが[Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)などの従来のアクティブ化パスを使用していて、以前のバージョンではなく CLR のバージョン4をアクティブ化する必要がある場合、またはアプリケーションが .net でビルドされている場合に便利です。Framework 4 では、以前のバージョンの .NET Framework でビルドされた混合モードのアセンブリに依存しています。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="0f7f6-141">これらのシナリオでは、属性を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="0f7f6-142">属性を `true` に設定すると、CLR バージョン1.1 または CLR バージョン2.0 が同じプロセスに読み込まれないため、インプロセスサイドバイサイドの機能が実質的に無効になります (「 [COM 相互運用機能の Side-by-side 実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="0f7f6-143">例</span><span class="sxs-lookup"><span data-stu-id="0f7f6-143">Example</span></span>

 <span data-ttu-id="0f7f6-144">次の例は、構成ファイルでランタイムバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f7f6-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0f7f6-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f7f6-145">See also</span></span>

- [<span data-ttu-id="0f7f6-146">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f7f6-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0f7f6-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="0f7f6-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0f7f6-148">2 つのオブジェクトが等しいかどうかをテストする方法.NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="0f7f6-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="0f7f6-149">[COM 相互運用のサイドバイサイド実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0f7f6-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="0f7f6-150">インプロセスの side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="0f7f6-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
