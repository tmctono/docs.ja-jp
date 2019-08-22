---
title: <NetFx40_LegacySecurityPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 881862b6b81ace1c1923b2a22d2fbe54d939d84e
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663571"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="5d7b1-102">\<NetFx40_LegacySecurityPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="5d7b1-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="5d7b1-103">ランタイムがレガシ コード アクセス セキュリティ (CAS) ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

<span data-ttu-id="5d7b1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5d7b1-104">\<configuration>\</span></span>
<span data-ttu-id="5d7b1-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="5d7b1-105">\<runtime>\</span></span>
<span data-ttu-id="5d7b1-106">\<NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="5d7b1-106">\<NetFx40_LegacySecurityPolicy></span></span>

## <a name="syntax"></a><span data-ttu-id="5d7b1-107">構文</span><span class="sxs-lookup"><span data-stu-id="5d7b1-107">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5d7b1-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5d7b1-108">Attributes and Elements</span></span>

<span data-ttu-id="5d7b1-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5d7b1-110">属性</span><span class="sxs-lookup"><span data-stu-id="5d7b1-110">Attributes</span></span>

|<span data-ttu-id="5d7b1-111">属性</span><span class="sxs-lookup"><span data-stu-id="5d7b1-111">Attribute</span></span>|<span data-ttu-id="5d7b1-112">説明</span><span class="sxs-lookup"><span data-stu-id="5d7b1-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="5d7b1-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5d7b1-114">ランタイムが従来の CAS ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="5d7b1-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="5d7b1-115">enabled Attribute</span></span>

|<span data-ttu-id="5d7b1-116">値</span><span class="sxs-lookup"><span data-stu-id="5d7b1-116">Value</span></span>|<span data-ttu-id="5d7b1-117">説明</span><span class="sxs-lookup"><span data-stu-id="5d7b1-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="5d7b1-118">ランタイムでは、従来の CAS ポリシーは使用されません。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="5d7b1-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="5d7b1-120">ランタイムは、従来の CAS ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-120">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5d7b1-121">子要素</span><span class="sxs-lookup"><span data-stu-id="5d7b1-121">Child Elements</span></span>

<span data-ttu-id="5d7b1-122">なし。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5d7b1-123">親要素</span><span class="sxs-lookup"><span data-stu-id="5d7b1-123">Parent Elements</span></span>

|<span data-ttu-id="5d7b1-124">要素</span><span class="sxs-lookup"><span data-stu-id="5d7b1-124">Element</span></span>|<span data-ttu-id="5d7b1-125">説明</span><span class="sxs-lookup"><span data-stu-id="5d7b1-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="5d7b1-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="5d7b1-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5d7b1-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="5d7b1-128">Remarks</span></span>

<span data-ttu-id="5d7b1-129">.NET Framework バージョン3.5 以前のバージョンでは、CAS ポリシーは常に有効です。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="5d7b1-130">.NET Framework 4 では、CAS ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-130">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="5d7b1-131">CAS ポリシーはバージョン固有です。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-131">CAS policy is version-specific.</span></span> <span data-ttu-id="5d7b1-132">以前のバージョンの .NET Framework に存在するカスタム CAS ポリシーは、.NET Framework 4 で再指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="5d7b1-133">要素を .NET Framework 4 アセンブリに適用しても、[セキュリティ透過的なコード](../../../misc/security-transparent-code.md)には影響しません。透過性ルールが適用されます。 `<NetFx40_LegacySecurityPolicy>`</span><span class="sxs-lookup"><span data-stu-id="5d7b1-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d7b1-134">要素を`<NetFx40_LegacySecurityPolicy>`適用すると、[グローバルアセンブリキャッシュ](../../../app-domains/gac.md)にインストールされていない[ネイティブイメージジェネレーター (ngen.exe)](../../../tools/ngen-exe-native-image-generator.md)によって作成されたネイティブイメージアセンブリのパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="5d7b1-135">パフォーマンスの低下は、属性が適用されたときにランタイムがネイティブイメージとしてアセンブリを読み込むことができないことが原因で発生し、その結果、ジャストインタイムアセンブリとして読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="5d7b1-136">Visual Studio プロジェクトの [プロジェクトの設定] で、.NET Framework 4 より前のターゲット .NET Framework バージョンを指定した場合、そのバージョンに指定したカスタム CAS ポリシーも含めて、CAS ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="5d7b1-137">ただし、新しい .NET Framework 4 種類とメンバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="5d7b1-138">[アプリケーション構成ファイル](../../index.md)のスタートアップ設定スキーマで、 [ \<supportedruntime > 要素](../startup/supportedruntime-element.md)を使用して、以前のバージョンの .NET Framework を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5d7b1-139">構成ファイルの構文では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="5d7b1-140">構文と例のセクションで提供されている構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="5d7b1-141">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="5d7b1-141">Configuration File</span></span>

<span data-ttu-id="5d7b1-142">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-142">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="5d7b1-143">例</span><span class="sxs-lookup"><span data-stu-id="5d7b1-143">Example</span></span>

<span data-ttu-id="5d7b1-144">次の例では、アプリケーションに対して従来の CAS ポリシーを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5d7b1-144">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5d7b1-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d7b1-145">See also</span></span>

- [<span data-ttu-id="5d7b1-146">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="5d7b1-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5d7b1-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="5d7b1-147">Configuration File Schema</span></span>](../index.md)
