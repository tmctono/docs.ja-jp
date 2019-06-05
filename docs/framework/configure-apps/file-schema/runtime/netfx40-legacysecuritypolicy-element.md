---
title: <NetFx40_LegacySecurityPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5bfa5449ece1b24d4f47fe3e77e36b26bbe430c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689835"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="1ae41-102">\<NetFx40_LegacySecurityPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="1ae41-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="1ae41-103">ランタイムがレガシ コード アクセス セキュリティ (CAS) ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="1ae41-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1ae41-104">\<configuration>\\</span></span>
<span data-ttu-id="1ae41-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="1ae41-105">\<runtime>\\</span></span>
<span data-ttu-id="1ae41-106">\<NetFx40_LegacySecurityPolicy></span><span class="sxs-lookup"><span data-stu-id="1ae41-106">\<NetFx40_LegacySecurityPolicy></span></span>

## <a name="syntax"></a><span data-ttu-id="1ae41-107">構文</span><span class="sxs-lookup"><span data-stu-id="1ae41-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="1ae41-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1ae41-108">Attributes and Elements</span></span>

<span data-ttu-id="1ae41-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1ae41-110">属性</span><span class="sxs-lookup"><span data-stu-id="1ae41-110">Attributes</span></span>

|<span data-ttu-id="1ae41-111">属性</span><span class="sxs-lookup"><span data-stu-id="1ae41-111">Attribute</span></span>|<span data-ttu-id="1ae41-112">説明</span><span class="sxs-lookup"><span data-stu-id="1ae41-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="1ae41-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1ae41-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ae41-114">ランタイムがレガシ CAS ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="1ae41-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1ae41-115">enabled Attribute</span></span>

|<span data-ttu-id="1ae41-116">値</span><span class="sxs-lookup"><span data-stu-id="1ae41-116">Value</span></span>|<span data-ttu-id="1ae41-117">説明</span><span class="sxs-lookup"><span data-stu-id="1ae41-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="1ae41-118">ランタイムは、従来の CAS ポリシーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="1ae41-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="1ae41-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="1ae41-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="1ae41-120">ランタイムは、従来の CAS ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="1ae41-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1ae41-121">Child Elements</span></span>

<span data-ttu-id="1ae41-122">なし。</span><span class="sxs-lookup"><span data-stu-id="1ae41-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="1ae41-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1ae41-123">Parent Elements</span></span>

|<span data-ttu-id="1ae41-124">要素</span><span class="sxs-lookup"><span data-stu-id="1ae41-124">Element</span></span>|<span data-ttu-id="1ae41-125">説明</span><span class="sxs-lookup"><span data-stu-id="1ae41-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="1ae41-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1ae41-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="1ae41-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="1ae41-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="1ae41-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ae41-128">Remarks</span></span>

<span data-ttu-id="1ae41-129">.NET Framework version 3.5 以前のバージョンで、CAS ポリシーは常に影響します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="1ae41-130">.NET Framework 4 では、CAS ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae41-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="1ae41-131">CAS ポリシーは、バージョン固有です。</span><span class="sxs-lookup"><span data-stu-id="1ae41-131">CAS policy is version-specific.</span></span> <span data-ttu-id="1ae41-132">.NET Framework の以前のバージョンに存在するカスタムの CAS ポリシーは、.NET Framework 4 で再度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae41-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="1ae41-133">適用、 `<NetFx40_LegacySecurityPolicy>` .NET Framework 4 アセンブリへの要素には影響しません[セキュリティ透過的なコード](../../../../../docs/framework/misc/security-transparent-code.md); 透過性規則が引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="1ae41-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ae41-134">適用、`<NetFx40_LegacySecurityPolicy>`要素により、大幅なパフォーマンスの低下によって作成されたネイティブ イメージ アセンブリ、[ネイティブ イメージ ジェネレーター (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md)でインストールされていない、[グローバル アセンブリ キャッシュ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="1ae41-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="1ae41-135">パフォーマンスの低下は、ランタイム属性が適用されるときに、ネイティブ イメージとして、アセンブリを読み込むことができないによる、として、just-in-time でアセンブリが読み込まれる結果的にします。</span><span class="sxs-lookup"><span data-stu-id="1ae41-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="1ae41-136">Visual Studio プロジェクトのプロジェクトの設定で .NET Framework 4 より前であるターゲット .NET Framework のバージョンを指定する場合の CA ポリシーが有効に、そのバージョンの指定した任意のカスタムの CAS ポリシーを含みます。</span><span class="sxs-lookup"><span data-stu-id="1ae41-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="1ae41-137">ただし、.NET Framework 4 の新しい型とメンバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1ae41-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="1ae41-138">使用して、.NET Framework の以前のバージョンを指定することも、 [ \<supportedRuntime > 要素](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)でスタートアップ設定スキーマで、[アプリケーション構成ファイル](../../../../../docs/framework/configure-apps/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1ae41-139">構成ファイルの構文は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="1ae41-140">構文と例のセクションで指定された構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ae41-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="1ae41-141">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1ae41-141">Configuration File</span></span>

<span data-ttu-id="1ae41-142">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1ae41-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="1ae41-143">例</span><span class="sxs-lookup"><span data-stu-id="1ae41-143">Example</span></span>

<span data-ttu-id="1ae41-144">次の例では、アプリケーションの従来の CAS ポリシーを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ae41-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="1ae41-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ae41-145">See also</span></span>

- [<span data-ttu-id="1ae41-146">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1ae41-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="1ae41-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1ae41-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
