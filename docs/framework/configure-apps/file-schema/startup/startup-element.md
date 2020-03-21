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
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153733"
---
# <a name="startup-element"></a><span data-ttu-id="2376f-102">\<スタートアップ>要素</span><span class="sxs-lookup"><span data-stu-id="2376f-102">\<startup> element</span></span>

<span data-ttu-id="2376f-103">共通言語ランタイムのスタートアップ情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="2376f-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="2376f-104">**\<構成>**</span><span class="sxs-lookup"><span data-stu-id="2376f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2376f-105">&nbsp;&nbsp;**\<スタートアップ>**</span><span class="sxs-lookup"><span data-stu-id="2376f-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="2376f-106">構文</span><span class="sxs-lookup"><span data-stu-id="2376f-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2376f-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="2376f-107">Attributes and elements</span></span>

 <span data-ttu-id="2376f-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2376f-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2376f-109">属性</span><span class="sxs-lookup"><span data-stu-id="2376f-109">Attributes</span></span>

|<span data-ttu-id="2376f-110">属性</span><span class="sxs-lookup"><span data-stu-id="2376f-110">Attribute</span></span>|<span data-ttu-id="2376f-111">説明</span><span class="sxs-lookup"><span data-stu-id="2376f-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="2376f-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="2376f-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2376f-113">.NET Framework 2.0 ランタイム アクティベーション ポリシーを有効にするか、.NET Framework 4 のライセンス認証ポリシーを使用するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2376f-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="2376f-114">属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="2376f-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="2376f-115">Value</span><span class="sxs-lookup"><span data-stu-id="2376f-115">Value</span></span>|<span data-ttu-id="2376f-116">説明</span><span class="sxs-lookup"><span data-stu-id="2376f-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="2376f-117">選択したランタイムに対して .NET Framework 2.0 ランタイム アクティベーション ポリシーを有効にします。 [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)</span><span class="sxs-lookup"><span data-stu-id="2376f-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="2376f-118">したがって、構成ファイルから CLR バージョン 4 以降を選択すると、以前のバージョンの .NET Framework で作成された混合モードアセンブリが、選択した CLR バージョンで読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2376f-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="2376f-119">この値を設定すると、CLR バージョン 1.1 または CLR バージョン 2.0 が同じプロセスに読み込まれるのを防ぎ、インプロセスのサイド バイ サイド機能を効果的に無効にします。</span><span class="sxs-lookup"><span data-stu-id="2376f-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="2376f-120">.NET Framework 4 以降の既定のアクティブ化ポリシーを使用すると、従来のランタイム アクティベーション手法で CLR バージョン 1.1 または 2.0 をプロセスに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2376f-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="2376f-121">この値を設定すると、.NET Framework 4 以降でビルドされていない限り、混在モードのアセンブリが .NET Framework 4 以降に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2376f-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="2376f-122">この値は既定値です。</span><span class="sxs-lookup"><span data-stu-id="2376f-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2376f-123">子要素</span><span class="sxs-lookup"><span data-stu-id="2376f-123">Child elements</span></span>

|<span data-ttu-id="2376f-124">要素</span><span class="sxs-lookup"><span data-stu-id="2376f-124">Element</span></span>|<span data-ttu-id="2376f-125">説明</span><span class="sxs-lookup"><span data-stu-id="2376f-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2376f-126">\<必要なランタイム></span><span class="sxs-lookup"><span data-stu-id="2376f-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="2376f-127">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="2376f-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="2376f-128">ランタイム バージョン 1.1 以降でビルドされたアプリケーションは**\<、サポートされているランタイム>** 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2376f-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="2376f-129">\<サポートされているランタイム></span><span class="sxs-lookup"><span data-stu-id="2376f-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="2376f-130">アプリケーションでサポートされる共通言語ランタイムのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="2376f-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="2376f-131">親要素</span><span class="sxs-lookup"><span data-stu-id="2376f-131">Parent elements</span></span>

|<span data-ttu-id="2376f-132">要素</span><span class="sxs-lookup"><span data-stu-id="2376f-132">Element</span></span>|<span data-ttu-id="2376f-133">説明</span><span class="sxs-lookup"><span data-stu-id="2376f-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2376f-134">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="2376f-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2376f-135">解説</span><span class="sxs-lookup"><span data-stu-id="2376f-135">Remarks</span></span>

 <span data-ttu-id="2376f-136">**\<サポートされているランタイム>** 要素は、バージョン 1.1 以降のランタイムを使用してビルドされたすべてのアプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2376f-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="2376f-137">ランタイムのバージョン 1.0 のみをサポートするように構築されたアプリケーションは**\<、requiredRuntime>** 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2376f-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="2376f-138">Internet Explorer でホストされているアプリケーションの**\<スタートアップ**コードは、スタートアップ>要素とその子要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="2376f-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="2376f-139">属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="2376f-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="2376f-140">この属性は、アプリケーションで[CorBindToRuntimeEx 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)などの従来のアクティブ化パスを使用し、それらのパスを以前のバージョンではなく CLR のバージョン 4 をアクティブにする場合、またはアプリケーションが .NET Framework 4 でビルドされているが、以前のバージョンの .NET Framework でビルドされた混合モード アセンブリに依存している場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2376f-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="2376f-141">これらのシナリオでは、属性を に`true`設定します。</span><span class="sxs-lookup"><span data-stu-id="2376f-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="2376f-142">CLR バージョン`true`1.1 または CLR バージョン 2.0 が同じプロセスに読み込まれるのを防ぐために属性を設定し、インプロセスのサイド バイ サイド機能を効果的に無効に[します (COM 相互運用機能のサイド バイ サイド実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))を参照)。</span><span class="sxs-lookup"><span data-stu-id="2376f-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="2376f-143">例</span><span class="sxs-lookup"><span data-stu-id="2376f-143">Example</span></span>

 <span data-ttu-id="2376f-144">次の例は、構成ファイルでランタイム バージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2376f-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2376f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="2376f-145">See also</span></span>

- [<span data-ttu-id="2376f-146">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="2376f-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2376f-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="2376f-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2376f-148">方法: .NET Framework 4 以降のバージョンをサポートするようにアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="2376f-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="2376f-149">[COM 相互運用機能の side-by-side 実行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2376f-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="2376f-150">インプロセスの side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="2376f-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
