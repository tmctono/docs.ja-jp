---
title: <requiredRuntime> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697495"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="f2a41-102">\<requiredRuntime> 要素</span><span class="sxs-lookup"><span data-stu-id="f2a41-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="f2a41-103">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2a41-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="f2a41-104">この要素は非推奨とされ、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f2a41-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="f2a41-105">[`supportedRuntime`](supportedruntime-element.md)代わりに、要素を使用してください。</span><span class="sxs-lookup"><span data-stu-id="f2a41-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="f2a41-106">構文</span><span class="sxs-lookup"><span data-stu-id="f2a41-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f2a41-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f2a41-107">Attributes and elements</span></span>

<span data-ttu-id="f2a41-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f2a41-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f2a41-109">属性</span><span class="sxs-lookup"><span data-stu-id="f2a41-109">Attributes</span></span>

|<span data-ttu-id="f2a41-110">属性</span><span class="sxs-lookup"><span data-stu-id="f2a41-110">Attribute</span></span>|<span data-ttu-id="f2a41-111">説明</span><span class="sxs-lookup"><span data-stu-id="f2a41-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="f2a41-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="f2a41-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f2a41-113">このアプリケーションでサポートされている .NET Framework のバージョンを指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="f2a41-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="f2a41-114">文字列値は、.NET Framework のインストールルートの下にあるディレクトリ名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a41-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="f2a41-115">文字列値の内容は解析されません。</span><span class="sxs-lookup"><span data-stu-id="f2a41-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="f2a41-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="f2a41-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="f2a41-117">ランタイムスタートアップコードがレジストリを検索してランタイムバージョンを確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2a41-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="f2a41-118">セーフ属性</span><span class="sxs-lookup"><span data-stu-id="f2a41-118">safemode attribute</span></span>

|<span data-ttu-id="f2a41-119">値</span><span class="sxs-lookup"><span data-stu-id="f2a41-119">Value</span></span>|<span data-ttu-id="f2a41-120">Description</span><span class="sxs-lookup"><span data-stu-id="f2a41-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="f2a41-121">ランタイムスタートアップコードによって、レジストリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="f2a41-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="f2a41-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="f2a41-123">ランタイムスタートアップコードでは、レジストリが検索されません。</span><span class="sxs-lookup"><span data-stu-id="f2a41-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f2a41-124">子要素</span><span class="sxs-lookup"><span data-stu-id="f2a41-124">Child elements</span></span>

<span data-ttu-id="f2a41-125">なし。</span><span class="sxs-lookup"><span data-stu-id="f2a41-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f2a41-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f2a41-126">Parent elements</span></span>

|<span data-ttu-id="f2a41-127">要素</span><span class="sxs-lookup"><span data-stu-id="f2a41-127">Element</span></span>|<span data-ttu-id="f2a41-128">Description</span><span class="sxs-lookup"><span data-stu-id="f2a41-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f2a41-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f2a41-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="f2a41-130">要素が含まれてい `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f2a41-131">解説</span><span class="sxs-lookup"><span data-stu-id="f2a41-131">Remarks</span></span>
 <span data-ttu-id="f2a41-132">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、要素を使用する必要があり `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="f2a41-133">ランタイムのバージョン1.1 以降を使用してビルドされたアプリケーションでは、要素を使用する必要があり `<supportedRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="f2a41-134">[Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)関数を使用して構成ファイルを指定する場合は、すべてのバージョンのランタイムで要素を使用する必要があり `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="f2a41-135">`<supportedRuntime>` [Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)を使用する場合、要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="f2a41-136">`version`属性文字列は、.NET Framework の指定したバージョンのインストールフォルダー名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2a41-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="f2a41-137">この文字列は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="f2a41-137">This string is not interpreted.</span></span> <span data-ttu-id="f2a41-138">ランタイムスタートアップコードが一致するフォルダーを見つけられない場合、ランタイムは読み込まれません。スタートアップコードによってエラーメッセージが表示され、終了します。</span><span class="sxs-lookup"><span data-stu-id="f2a41-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="f2a41-139">Microsoft Internet Explorer でホストされているアプリケーションのスタートアップコードは、要素を無視し `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="f2a41-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="f2a41-140">例</span><span class="sxs-lookup"><span data-stu-id="f2a41-140">Example</span></span>

<span data-ttu-id="f2a41-141">次の例は、構成ファイルでランタイムバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f2a41-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f2a41-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2a41-142">See also</span></span>

- [<span data-ttu-id="f2a41-143">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="f2a41-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f2a41-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f2a41-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f2a41-145">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="f2a41-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
