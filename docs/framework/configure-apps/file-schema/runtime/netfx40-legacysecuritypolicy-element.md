---
title: <NetFx40_LegacySecurityPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116253"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="6ca17-102">\<NetFx40_LegacySecurityPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="6ca17-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="6ca17-103">ランタイムがレガシ コード アクセス セキュリティ (CAS) ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ca17-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="6ca17-104">構文</span><span class="sxs-lookup"><span data-stu-id="6ca17-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ca17-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6ca17-105">Attributes and Elements</span></span>

<span data-ttu-id="6ca17-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ca17-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ca17-107">属性</span><span class="sxs-lookup"><span data-stu-id="6ca17-107">Attributes</span></span>

|<span data-ttu-id="6ca17-108">属性</span><span class="sxs-lookup"><span data-stu-id="6ca17-108">Attribute</span></span>|<span data-ttu-id="6ca17-109">説明</span><span class="sxs-lookup"><span data-stu-id="6ca17-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6ca17-110">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="6ca17-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="6ca17-111">ランタイムが従来の CAS ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6ca17-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6ca17-112">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="6ca17-112">enabled Attribute</span></span>

|<span data-ttu-id="6ca17-113">値</span><span class="sxs-lookup"><span data-stu-id="6ca17-113">Value</span></span>|<span data-ttu-id="6ca17-114">Description</span><span class="sxs-lookup"><span data-stu-id="6ca17-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="6ca17-115">ランタイムでは、従来の CAS ポリシーは使用されません。</span><span class="sxs-lookup"><span data-stu-id="6ca17-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="6ca17-116">既定値です。</span><span class="sxs-lookup"><span data-stu-id="6ca17-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="6ca17-117">ランタイムは、従来の CAS ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ca17-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6ca17-118">子要素</span><span class="sxs-lookup"><span data-stu-id="6ca17-118">Child Elements</span></span>

<span data-ttu-id="6ca17-119">なし。</span><span class="sxs-lookup"><span data-stu-id="6ca17-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ca17-120">親要素</span><span class="sxs-lookup"><span data-stu-id="6ca17-120">Parent Elements</span></span>

|<span data-ttu-id="6ca17-121">要素</span><span class="sxs-lookup"><span data-stu-id="6ca17-121">Element</span></span>|<span data-ttu-id="6ca17-122">Description</span><span class="sxs-lookup"><span data-stu-id="6ca17-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6ca17-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="6ca17-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6ca17-124">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ca17-125">解説</span><span class="sxs-lookup"><span data-stu-id="6ca17-125">Remarks</span></span>

<span data-ttu-id="6ca17-126">.NET Framework バージョン3.5 以前のバージョンでは、CAS ポリシーは常に有効です。</span><span class="sxs-lookup"><span data-stu-id="6ca17-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="6ca17-127">.NET Framework 4 では、CAS ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca17-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="6ca17-128">CAS ポリシーはバージョン固有です。</span><span class="sxs-lookup"><span data-stu-id="6ca17-128">CAS policy is version-specific.</span></span> <span data-ttu-id="6ca17-129">以前のバージョンの .NET Framework に存在するカスタム CAS ポリシーは、.NET Framework 4 で再指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca17-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="6ca17-130">要素を `<NetFx40_LegacySecurityPolicy>` .NET Framework 4 アセンブリに適用しても、[セキュリティ透過的なコード](../../../misc/security-transparent-code.md)には影響しません。透過性ルールが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ca17-131">要素を適用すると、 `<NetFx40_LegacySecurityPolicy>` [グローバルアセンブリキャッシュ](../../../app-domains/gac.md)にインストールされていない[ネイティブイメージジェネレーター (ngen.exe)](../../../tools/ngen-exe-native-image-generator.md)によって作成されたネイティブイメージアセンブリのパフォーマンスが大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ca17-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="6ca17-132">パフォーマンスの低下は、属性が適用されたときにランタイムがネイティブイメージとしてアセンブリを読み込むことができないことが原因で発生し、その結果、ジャストインタイムアセンブリとして読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="6ca17-133">Visual Studio プロジェクトの [プロジェクトの設定] で、.NET Framework 4 より前のターゲット .NET Framework バージョンを指定した場合、そのバージョンに指定したカスタム CAS ポリシーも含めて、CAS ポリシーが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ca17-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="6ca17-134">ただし、新しい .NET Framework 4 種類とメンバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6ca17-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="6ca17-135">[アプリケーション構成ファイル](../../index.md)のスタートアップ設定スキーマの[ \<supportedRuntime> 要素](../startup/supportedruntime-element.md)を使用して、以前のバージョンの .NET Framework を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6ca17-136">構成ファイルの構文では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="6ca17-137">構文と例のセクションで提供されている構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ca17-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="6ca17-138">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="6ca17-138">Configuration File</span></span>

<span data-ttu-id="6ca17-139">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6ca17-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="6ca17-140">例</span><span class="sxs-lookup"><span data-stu-id="6ca17-140">Example</span></span>

<span data-ttu-id="6ca17-141">次の例では、アプリケーションに対して従来の CAS ポリシーを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6ca17-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6ca17-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ca17-142">See also</span></span>

- [<span data-ttu-id="6ca17-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="6ca17-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6ca17-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="6ca17-144">Configuration File Schema</span></span>](../index.md)
