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
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697495"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="380c4-102">\<requiredRuntime > 要素</span><span class="sxs-lookup"><span data-stu-id="380c4-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="380c4-103">バージョン 1.0 の共通言語ランタイムのみがアプリケーションでサポートされることを指定します。</span><span class="sxs-lookup"><span data-stu-id="380c4-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="380c4-104">この要素は非推奨とされ、使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="380c4-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="380c4-105">代わりに、 [`supportedRuntime`](supportedruntime-element.md)要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="380c4-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="380c4-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="380c4-107">&nbsp;&nbsp;[ **\<スタートアップ >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="380c4-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="380c4-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="380c4-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="380c4-109">構文</span><span class="sxs-lookup"><span data-stu-id="380c4-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="380c4-110">属性と要素</span><span class="sxs-lookup"><span data-stu-id="380c4-110">Attributes and elements</span></span>

<span data-ttu-id="380c4-111">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="380c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="380c4-112">属性</span><span class="sxs-lookup"><span data-stu-id="380c4-112">Attributes</span></span>

|<span data-ttu-id="380c4-113">属性</span><span class="sxs-lookup"><span data-stu-id="380c4-113">Attribute</span></span>|<span data-ttu-id="380c4-114">説明</span><span class="sxs-lookup"><span data-stu-id="380c4-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="380c4-115">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="380c4-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="380c4-116">このアプリケーションでサポートされている .NET Framework のバージョンを指定する文字列値。</span><span class="sxs-lookup"><span data-stu-id="380c4-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="380c4-117">文字列値は、.NET Framework のインストールルートの下にあるディレクトリ名と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="380c4-118">文字列値の内容は解析されません。</span><span class="sxs-lookup"><span data-stu-id="380c4-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="380c4-119">省略可能な属性です。</span><span class="sxs-lookup"><span data-stu-id="380c4-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="380c4-120">ランタイムスタートアップコードがレジストリを検索してランタイムバージョンを確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="380c4-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="380c4-121">セーフ属性</span><span class="sxs-lookup"><span data-stu-id="380c4-121">safemode attribute</span></span>

|<span data-ttu-id="380c4-122">値</span><span class="sxs-lookup"><span data-stu-id="380c4-122">Value</span></span>|<span data-ttu-id="380c4-123">説明</span><span class="sxs-lookup"><span data-stu-id="380c4-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="380c4-124">ランタイムスタートアップコードによって、レジストリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="380c4-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="380c4-125">これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="380c4-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="380c4-126">ランタイムスタートアップコードでは、レジストリが検索されません。</span><span class="sxs-lookup"><span data-stu-id="380c4-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="380c4-127">子要素</span><span class="sxs-lookup"><span data-stu-id="380c4-127">Child elements</span></span>

<span data-ttu-id="380c4-128">[なし]。</span><span class="sxs-lookup"><span data-stu-id="380c4-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="380c4-129">親要素</span><span class="sxs-lookup"><span data-stu-id="380c4-129">Parent elements</span></span>

|<span data-ttu-id="380c4-130">要素</span><span class="sxs-lookup"><span data-stu-id="380c4-130">Element</span></span>|<span data-ttu-id="380c4-131">説明</span><span class="sxs-lookup"><span data-stu-id="380c4-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="380c4-132">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="380c4-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="380c4-133">`<requiredRuntime>`要素を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="380c4-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="380c4-134">コメント</span><span class="sxs-lookup"><span data-stu-id="380c4-134">Remarks</span></span>
 <span data-ttu-id="380c4-135">ランタイムのバージョン1.0 のみをサポートするようにビルドされたアプリケーションでは、`<requiredRuntime>` 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="380c4-136">ランタイムのバージョン1.1 以降を使用してビルドされたアプリケーションでは、`<supportedRuntime>` 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="380c4-137">[Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)関数を使用して構成ファイルを指定する場合は、すべてのバージョンのランタイムに対して `<requiredRuntime>` 要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="380c4-138">[Corbindtoruntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)を使用する場合、`<supportedRuntime>` 要素は無視されます。</span><span class="sxs-lookup"><span data-stu-id="380c4-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="380c4-139">`version` 属性文字列は、.NET Framework の指定したバージョンのインストールフォルダー名と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="380c4-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="380c4-140">この文字列は解釈されません。</span><span class="sxs-lookup"><span data-stu-id="380c4-140">This string is not interpreted.</span></span> <span data-ttu-id="380c4-141">ランタイムスタートアップコードが一致するフォルダーを見つけられない場合、ランタイムは読み込まれません。スタートアップコードによってエラーメッセージが表示され、終了します。</span><span class="sxs-lookup"><span data-stu-id="380c4-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="380c4-142">Microsoft Internet Explorer でホストされているアプリケーションのスタートアップコードは、`<requiredRuntime>` 要素を無視します。</span><span class="sxs-lookup"><span data-stu-id="380c4-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="380c4-143">例</span><span class="sxs-lookup"><span data-stu-id="380c4-143">Example</span></span>

<span data-ttu-id="380c4-144">次の例は、構成ファイルでランタイムバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="380c4-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="380c4-145">参照</span><span class="sxs-lookup"><span data-stu-id="380c4-145">See also</span></span>

- [<span data-ttu-id="380c4-146">スタートアップ設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="380c4-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="380c4-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="380c4-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="380c4-148">方法: .NET Framework 4 以降のバージョンをサポートするようにアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="380c4-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
