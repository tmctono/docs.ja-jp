---
title: <supportedRuntime>configuration 要素-.NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: ecbe73593e5b8b87909499f6fff7e865e29b1ec8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "82796042"
---
# <a name="supportedruntime-element"></a><span data-ttu-id="f3b6e-102">\<supportedRuntime> 要素</span><span class="sxs-lookup"><span data-stu-id="f3b6e-102">\<supportedRuntime> element</span></span>

<span data-ttu-id="f3b6e-103">アプリケーションがサポートする共通言語ランタイムバージョンと、オプションで .NET Framework バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-103">Specifies which common language runtime version and, optionally, .NET Framework version the application supports.</span></span>  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a><span data-ttu-id="f3b6e-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3b6e-104">Syntax</span></span>

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a><span data-ttu-id="f3b6e-105">属性</span><span class="sxs-lookup"><span data-stu-id="f3b6e-105">Attributes</span></span>

|<span data-ttu-id="f3b6e-106">属性</span><span class="sxs-lookup"><span data-stu-id="f3b6e-106">Attribute</span></span>|<span data-ttu-id="f3b6e-107">説明</span><span class="sxs-lookup"><span data-stu-id="f3b6e-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="f3b6e-108">**version**</span><span class="sxs-lookup"><span data-stu-id="f3b6e-108">**version**</span></span>|<span data-ttu-id="f3b6e-109">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-109">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f3b6e-110">このアプリケーションがサポートする共通言語ランタイム (CLR: Common Language Runtime) のバージョンを指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-110">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="f3b6e-111">属性の有効な値については、「 `version` [ランタイムバージョン」の値](#version)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-111">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="f3b6e-112">**注:** .NET Framework 3.5 では、"*runtime version*" の値は*major*という形式になります。*minor*。*ビルド*。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-112">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="f3b6e-113">.NET Framework 4 以降では、メジャーバージョン番号とマイナーバージョン番号 ("v v4.0.30319" の代わりに "v4.0") のみが必要です。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-113">Beginning with the .NET Framework 4, only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="f3b6e-114">短い文字列を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-114">The shorter string is recommended.</span></span>|
|<span data-ttu-id="f3b6e-115">**sku**</span><span class="sxs-lookup"><span data-stu-id="f3b6e-115">**sku**</span></span>|<span data-ttu-id="f3b6e-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f3b6e-117">在庫管理単位 (SKU) を指定する文字列の値。SKU はこのアプリケーションがサポートする .NET Framework リリースを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-117">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="f3b6e-118">.NET Framework 4.0 以降では、`sku` 属性の使用が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-118">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="f3b6e-119">この属性が指定される場合は、アプリケーションが対象とする .NET Framework のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-119">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="f3b6e-120">Sku 属性の有効な値については、「 [sku id」の値](#sku)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-120">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3b6e-121">解説</span><span class="sxs-lookup"><span data-stu-id="f3b6e-121">Remarks</span></span>

<span data-ttu-id="f3b6e-122">**\<supportedRuntime>** アプリケーション構成ファイルに要素が存在しない場合は、アプリケーションのビルドに使用されるランタイムのバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-122">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>

<span data-ttu-id="f3b6e-123">要素は、 **\<supportedRuntime>** ランタイムのバージョン1.1 以降を使用してビルドされたすべてのアプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-123">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="f3b6e-124">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、要素を使用する必要があり [\<requiredRuntime>](requiredruntime-element.md) ます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-124">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](requiredruntime-element.md) element.</span></span>

> [!NOTE]
> <span data-ttu-id="f3b6e-125">[Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)関数を使用して構成ファイルを指定する場合は、すべてのバージョンのランタイムで要素を使用する必要があり `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-125">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="f3b6e-126">`<supportedRuntime>` [Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)を使用する場合、要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-126">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="f3b6e-127">NET Framework 1.1 から 3.5 までのランタイムの複数のバージョンをサポートするアプリケーションでは、ランタイムの複数のバージョンをサポートする場合は、最初の要素で最も優先度の高いバージョンを指定し、最後の要素で最も優先度の低いバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-127">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="f3b6e-128">.NET Framework 4.0 以降のバージョンをサポートするアプリの場合、 `version` 属性は、.NET Framework 4 以降のバージョンに共通する CLR バージョンを示し、属性は、 `sku` アプリが対象とする1つの .NET Framework バージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-128">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates the single .NET Framework version that the app targets.</span></span>

<span data-ttu-id="f3b6e-129">属性を **\<supportedRuntime>** 持つ要素 `sku` が構成ファイル内に存在し、インストールされている .NET Framework バージョンが指定したサポートされているバージョンより低い場合、アプリケーションの実行は失敗し、サポートされているバージョンをインストールするよう求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-129">If the **\<supportedRuntime>** element with the `sku` attribute is present in the configuration file and the installed .NET Framework version is lower then the specified supported version, the application fails to run and instead displays a message asking to install the supported version.</span></span> <span data-ttu-id="f3b6e-130">それ以外の場合は、インストールされている任意のバージョンでアプリケーションを実行しようとしますが、そのバージョンと完全に互換性がないと、予期しない動作をする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-130">Otherwise, the application attempts to run on any installed version, but it may behave unexpectedly if it is not fully compatible with that version.</span></span> <span data-ttu-id="f3b6e-131">.NET Framework のバージョン間の互換性の違いについては、.NET Framework の「[アプリケーションの互換性](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)」を参照してください。そのため、エラー診断を容易にするために、この要素をアプリケーション構成ファイルに含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-131">(For compatibility differences between versions of .NET Framework, see [Application compatibility in the .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Therefore, we recommend that you include this element in the application configuration file for easier error diagnostics.</span></span> <span data-ttu-id="f3b6e-132">(Visual Studio によって自動的に生成された構成ファイルは、新しいプロジェクトを作成するときに自動的に生成されます)。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-132">(The configuration file automatically generated by Visual Studio when creating a new project already contains it.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="f3b6e-133">アプリケーションでレガシアクティブ化パスを使用する場合は、 [Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)など、以前のバージョンではなく CLR のバージョン4をアクティブ化する場合、またはアプリケーションが .NET Framework 4 でビルドされていても、以前のバージョンの .NET Framework でビルドされた混在モードのアセンブリに依存している場合は、サポートされるランタイムの一覧で .NET Framework 4 を指定するだけでは不十分です</span><span class="sxs-lookup"><span data-stu-id="f3b6e-133">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the .NET Framework 4 in the list of supported runtimes.</span></span> <span data-ttu-id="f3b6e-134">さらに、構成ファイルの[ \<startup> 要素](startup-element.md)で、属性をに設定する必要があり `useLegacyV2RuntimeActivationPolicy` `true` ます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-134">In addition, in the [\<startup> element](startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="f3b6e-135">ただし、この属性をに設定すると、 `true` 以前のバージョンの .NET Framework でビルドされたすべてのコンポーネントが、ビルドされたランタイムではなく、.NET Framework 4 を使用して実行されることになります。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-135">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the .NET Framework 4 instead of the runtimes they were built with.</span></span>

<span data-ttu-id="f3b6e-136">アプリケーションは、そのアプリケーションを実行できる .NET Framework のすべてのバージョンでテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-136">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>

<a name="version"></a>
## <a name="runtime-version-values"></a><span data-ttu-id="f3b6e-137">"ランタイム バージョン" の値</span><span class="sxs-lookup"><span data-stu-id="f3b6e-137">"runtime version" values</span></span>
<span data-ttu-id="f3b6e-138">属性は、 `runtime` 特定のアプリケーションに必要な共通言語ランタイム (CLR) のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-138">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="f3b6e-139">すべての .NET Framework v4. x バージョンで CLR が指定されていることに注意してください `v4.0` 。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-139">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="f3b6e-140">次の表に、属性の*ランタイムバージョン*の値の有効な値を示し `version` ます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-140">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>

|<span data-ttu-id="f3b6e-141">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="f3b6e-141">.NET Framework version</span></span>|<span data-ttu-id="f3b6e-142">`version` 属性</span><span class="sxs-lookup"><span data-stu-id="f3b6e-142">`version` attribute</span></span>|
|----------------------------|-------------------------|
|<span data-ttu-id="f3b6e-143">1.0</span><span class="sxs-lookup"><span data-stu-id="f3b6e-143">1.0</span></span>|<span data-ttu-id="f3b6e-144">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-144">"v1.0.3705"</span></span>|
|<span data-ttu-id="f3b6e-145">1.1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-145">1.1</span></span>|<span data-ttu-id="f3b6e-146">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-146">"v1.1.4322"</span></span>|
|<span data-ttu-id="f3b6e-147">2.0</span><span class="sxs-lookup"><span data-stu-id="f3b6e-147">2.0</span></span>|<span data-ttu-id="f3b6e-148">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-148">"v2.0.50727"</span></span>|
|<span data-ttu-id="f3b6e-149">3.0</span><span class="sxs-lookup"><span data-stu-id="f3b6e-149">3.0</span></span>|<span data-ttu-id="f3b6e-150">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-150">"v2.0.50727"</span></span>|
|<span data-ttu-id="f3b6e-151">3.5</span><span class="sxs-lookup"><span data-stu-id="f3b6e-151">3.5</span></span>|<span data-ttu-id="f3b6e-152">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-152">"v2.0.50727"</span></span>|
|<span data-ttu-id="f3b6e-153">4.0-4.8</span><span class="sxs-lookup"><span data-stu-id="f3b6e-153">4.0-4.8</span></span>|<span data-ttu-id="f3b6e-154">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-154">"v4.0"</span></span>|

## <a name="sku-id-values"></a><a name="sku"></a><span data-ttu-id="f3b6e-155">"sku id" の値</span><span class="sxs-lookup"><span data-stu-id="f3b6e-155">"sku id" values</span></span>

<span data-ttu-id="f3b6e-156">属性は、 `sku` ターゲットフレームワークモニカー (TFM) を使用して、アプリが対象として実行する必要がある .NET Framework のバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-156">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="f3b6e-157">次の表に、属性でサポートされている有効な値 `sku` を示します。 .NET Framework 4 から始まります。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-157">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>

|<span data-ttu-id="f3b6e-158">.NET Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="f3b6e-158">.NET Framework version</span></span>|<span data-ttu-id="f3b6e-159">`sku` 属性</span><span class="sxs-lookup"><span data-stu-id="f3b6e-159">`sku` attribute</span></span>|
|----------------------------|---------------------|
|<span data-ttu-id="f3b6e-160">4.0</span><span class="sxs-lookup"><span data-stu-id="f3b6e-160">4.0</span></span>|<span data-ttu-id="f3b6e-161">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-161">".NETFramework,Version=v4.0"</span></span>|
|<span data-ttu-id="f3b6e-162">4.0、Client Profile</span><span class="sxs-lookup"><span data-stu-id="f3b6e-162">4.0, Client Profile</span></span>|<span data-ttu-id="f3b6e-163">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-163">".NETFramework,Version=v4.0,Profile=Client"</span></span>|
|<span data-ttu-id="f3b6e-164">4.0、プラットフォームの更新プログラム 1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-164">4.0, platform update 1</span></span>|<span data-ttu-id="f3b6e-165">".NETFramework、Version = v 4.0.1 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-165">".NETFramework,Version=v4.0.1"</span></span>|
|<span data-ttu-id="f3b6e-166">4.0、Client Profile、更新プログラム 1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-166">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="f3b6e-167">".NETFramework、Version = v 4.0.1、Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-167">".NETFramework,Version=v4.0.1,Profile=Client"</span></span>|
|<span data-ttu-id="f3b6e-168">4.0、プラットフォームの更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="f3b6e-168">4.0, platform update 2</span></span>|<span data-ttu-id="f3b6e-169">".NETFramework、Version = v 4.0.2 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-169">".NETFramework,Version=v4.0.2"</span></span>|
|<span data-ttu-id="f3b6e-170">4.0、Client Profile、更新プログラム 2</span><span class="sxs-lookup"><span data-stu-id="f3b6e-170">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="f3b6e-171">".NETFramework、Version = v 4.0.2、Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-171">".NETFramework,Version=v4.0.2,Profile=Client"</span></span>|
|<span data-ttu-id="f3b6e-172">4.0、プラットフォームの更新プログラム 3</span><span class="sxs-lookup"><span data-stu-id="f3b6e-172">4.0, platform update 3</span></span>|<span data-ttu-id="f3b6e-173">".NETFramework、Version = v 4.0.3 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-173">".NETFramework,Version=v4.0.3"</span></span>|
|<span data-ttu-id="f3b6e-174">4.0、Client Profile、更新プログラム 3</span><span class="sxs-lookup"><span data-stu-id="f3b6e-174">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="f3b6e-175">".NETFramework、Version = v 4.0.3、Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-175">".NETFramework,Version=v4.0.3,Profile=Client"</span></span>|
|<span data-ttu-id="f3b6e-176">4.5</span><span class="sxs-lookup"><span data-stu-id="f3b6e-176">4.5</span></span>|<span data-ttu-id="f3b6e-177">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-177">".NETFramework,Version=v4.5"</span></span>|
|<span data-ttu-id="f3b6e-178">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-178">4.5.1</span></span>|<span data-ttu-id="f3b6e-179">".NETFramework,Version=v4.5.1"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-179">".NETFramework,Version=v4.5.1"</span></span>|
|<span data-ttu-id="f3b6e-180">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f3b6e-180">4.5.2</span></span>|<span data-ttu-id="f3b6e-181">".NETFramework,Version=v4.5.2"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-181">".NETFramework,Version=v4.5.2"</span></span>|
|<span data-ttu-id="f3b6e-182">4.6</span><span class="sxs-lookup"><span data-stu-id="f3b6e-182">4.6</span></span>|<span data-ttu-id="f3b6e-183">".NETFramework,Version=v4.6"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-183">".NETFramework,Version=v4.6"</span></span>|
|<span data-ttu-id="f3b6e-184">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-184">4.6.1</span></span>|<span data-ttu-id="f3b6e-185">".NETFramework,Version=v4.6.1"</span><span class="sxs-lookup"><span data-stu-id="f3b6e-185">".NETFramework,Version=v4.6.1"</span></span>|
|<span data-ttu-id="f3b6e-186">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f3b6e-186">4.6.2</span></span>|<span data-ttu-id="f3b6e-187">".NETFramework、Version = v 4.6.2 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-187">".NETFramework,Version=v4.6.2"</span></span>|
|<span data-ttu-id="f3b6e-188">4.7</span><span class="sxs-lookup"><span data-stu-id="f3b6e-188">4.7</span></span>|<span data-ttu-id="f3b6e-189">".NETFramework バージョン = v1.0 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-189">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="f3b6e-190">4.7.1</span><span class="sxs-lookup"><span data-stu-id="f3b6e-190">4.7.1</span></span>|<span data-ttu-id="f3b6e-191">".NETFramework、Version = v 4.7.1 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-191">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="f3b6e-192">4.7.2</span><span class="sxs-lookup"><span data-stu-id="f3b6e-192">4.7.2</span></span>|<span data-ttu-id="f3b6e-193">".NETFramework、Version = v 4.7.2 "</span><span class="sxs-lookup"><span data-stu-id="f3b6e-193">".NETFramework,Version=v4.7.2"</span></span>|
|<span data-ttu-id="f3b6e-194">4.8</span><span class="sxs-lookup"><span data-stu-id="f3b6e-194">4.8</span></span>|<span data-ttu-id="f3b6e-195">".NETFramework バージョン = v1.0</span><span class="sxs-lookup"><span data-stu-id="f3b6e-195">".NETFramework,Version=v4.8"</span></span>|

## <a name="example"></a><span data-ttu-id="f3b6e-196">例</span><span class="sxs-lookup"><span data-stu-id="f3b6e-196">Example</span></span>

<span data-ttu-id="f3b6e-197">サポートされているランタイムのバージョンを構成ファイルで指定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-197">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="f3b6e-198">構成ファイルは、アプリが .NET Framework 4.7 を対象としていることを示します。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-198">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f3b6e-199">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="f3b6e-199">Configuration file</span></span>

<span data-ttu-id="f3b6e-200">この要素は、アプリケーション構成ファイルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3b6e-200">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3b6e-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3b6e-201">See also</span></span>

- [<span data-ttu-id="f3b6e-202">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f3b6e-202">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f3b6e-203">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f3b6e-203">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f3b6e-204">インプロセスの side-by-side 実行</span><span class="sxs-lookup"><span data-stu-id="f3b6e-204">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
