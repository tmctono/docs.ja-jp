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
ms.openlocfilehash: 19fa1561ca3acd845918d952379c5227121465b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174070"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="d4476-102">\<requiredRuntime> 要素</span><span class="sxs-lookup"><span data-stu-id="d4476-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="d4476-103">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4476-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="d4476-104">この要素は非推奨とされ、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="d4476-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="d4476-105">[`supportedRuntime`](supportedruntime-element.md)代わりに、要素を使用してください。</span><span class="sxs-lookup"><span data-stu-id="d4476-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a><span data-ttu-id="d4476-106">構文</span><span class="sxs-lookup"><span data-stu-id="d4476-106">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d4476-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="d4476-107">Attributes and elements</span></span>

<span data-ttu-id="d4476-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d4476-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d4476-109">属性</span><span class="sxs-lookup"><span data-stu-id="d4476-109">Attributes</span></span>

|<span data-ttu-id="d4476-110">属性</span><span class="sxs-lookup"><span data-stu-id="d4476-110">Attribute</span></span>|<span data-ttu-id="d4476-111">説明</span><span class="sxs-lookup"><span data-stu-id="d4476-111">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="d4476-112">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d4476-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d4476-113">このアプリケーションでサポートされている .NET Framework のバージョンを指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="d4476-113">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="d4476-114">文字列値は、.NET Framework のインストールルートの下にあるディレクトリ名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4476-114">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="d4476-115">文字列値の内容は解析されません。</span><span class="sxs-lookup"><span data-stu-id="d4476-115">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="d4476-116">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="d4476-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d4476-117">ランタイムスタートアップコードがレジストリを検索してランタイムバージョンを確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4476-117">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="d4476-118">セーフ属性</span><span class="sxs-lookup"><span data-stu-id="d4476-118">safemode attribute</span></span>

|<span data-ttu-id="d4476-119">値</span><span class="sxs-lookup"><span data-stu-id="d4476-119">Value</span></span>|<span data-ttu-id="d4476-120">[説明]</span><span class="sxs-lookup"><span data-stu-id="d4476-120">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="d4476-121">ランタイムスタートアップコードによって、レジストリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="d4476-121">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="d4476-122">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="d4476-122">This is the default value.</span></span>|
|`true`|<span data-ttu-id="d4476-123">ランタイムスタートアップコードでは、レジストリが検索されません。</span><span class="sxs-lookup"><span data-stu-id="d4476-123">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d4476-124">子要素</span><span class="sxs-lookup"><span data-stu-id="d4476-124">Child elements</span></span>

<span data-ttu-id="d4476-125">なし。</span><span class="sxs-lookup"><span data-stu-id="d4476-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d4476-126">親要素</span><span class="sxs-lookup"><span data-stu-id="d4476-126">Parent elements</span></span>

|<span data-ttu-id="d4476-127">要素</span><span class="sxs-lookup"><span data-stu-id="d4476-127">Element</span></span>|<span data-ttu-id="d4476-128">説明</span><span class="sxs-lookup"><span data-stu-id="d4476-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="d4476-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="d4476-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="d4476-130">要素が含まれてい `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4476-130">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d4476-131">解説</span><span class="sxs-lookup"><span data-stu-id="d4476-131">Remarks</span></span>

 <span data-ttu-id="d4476-132">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、要素を使用する必要があり `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4476-132">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="d4476-133">ランタイムのバージョン1.1 以降を使用してビルドされたアプリケーションでは、要素を使用する必要があり `<supportedRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4476-133">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="d4476-134">[Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)関数を使用して構成ファイルを指定する場合は、すべてのバージョンのランタイムで要素を使用する必要があり `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4476-134">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="d4476-135">`<supportedRuntime>` [Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)を使用する場合、要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="d4476-135">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="d4476-136">`version`属性文字列は、.NET Framework の指定したバージョンのインストールフォルダー名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4476-136">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="d4476-137">この文字列は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="d4476-137">This string is not interpreted.</span></span> <span data-ttu-id="d4476-138">ランタイムスタートアップコードが一致するフォルダーを見つけられない場合、ランタイムは読み込まれません。スタートアップコードによってエラーメッセージが表示され、終了します。</span><span class="sxs-lookup"><span data-stu-id="d4476-138">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="d4476-139">Microsoft Internet Explorer でホストされているアプリケーションのスタートアップコードは、要素を無視し `<requiredRuntime>` ます。</span><span class="sxs-lookup"><span data-stu-id="d4476-139">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="d4476-140">例</span><span class="sxs-lookup"><span data-stu-id="d4476-140">Example</span></span>

<span data-ttu-id="d4476-141">次の例は、構成ファイルでランタイムバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d4476-141">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="d4476-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="d4476-142">See also</span></span>

- [<span data-ttu-id="d4476-143">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="d4476-143">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d4476-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="d4476-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d4476-145">方法: .NET Framework 4 以降のバージョンをサポートするアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="d4476-145">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
