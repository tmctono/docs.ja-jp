---
title: <NetFx40_LegacySecurityPolicy> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 848c56773c0ff2986f0bec3e82a08a3d0dd35434
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456470"
---
# <a name="netfx40legacysecuritypolicy-element"></a><span data-ttu-id="a4a0f-102">\<NetFx40_LegacySecurityPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="a4a0f-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>
<span data-ttu-id="a4a0f-103">ランタイムがレガシ コード アクセス セキュリティ (CAS) ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="a4a0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a4a0f-104">\<configuration></span></span>  
<span data-ttu-id="a4a0f-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a4a0f-105">\<runtime></span></span>  
<span data-ttu-id="a4a0f-106">< NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="a4a0f-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a0f-107">構文</span><span class="sxs-lookup"><span data-stu-id="a4a0f-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4a0f-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a4a0f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a4a0f-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4a0f-110">属性</span><span class="sxs-lookup"><span data-stu-id="a4a0f-110">Attributes</span></span>  
  
|<span data-ttu-id="a4a0f-111">属性</span><span class="sxs-lookup"><span data-stu-id="a4a0f-111">Attribute</span></span>|<span data-ttu-id="a4a0f-112">説明</span><span class="sxs-lookup"><span data-stu-id="a4a0f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a4a0f-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a4a0f-114">ランタイムがレガシ CAS ポリシーを使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a4a0f-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a4a0f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a4a0f-116">値</span><span class="sxs-lookup"><span data-stu-id="a4a0f-116">Value</span></span>|<span data-ttu-id="a4a0f-117">説明</span><span class="sxs-lookup"><span data-stu-id="a4a0f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="a4a0f-118">ランタイムは、従来の CAS ポリシーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="a4a0f-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="a4a0f-120">ランタイムは、従来の CAS ポリシーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4a0f-121">子要素</span><span class="sxs-lookup"><span data-stu-id="a4a0f-121">Child Elements</span></span>  
 <span data-ttu-id="a4a0f-122">なし。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4a0f-123">親要素</span><span class="sxs-lookup"><span data-stu-id="a4a0f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a4a0f-124">要素</span><span class="sxs-lookup"><span data-stu-id="a4a0f-124">Element</span></span>|<span data-ttu-id="a4a0f-125">説明</span><span class="sxs-lookup"><span data-stu-id="a4a0f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a4a0f-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a4a0f-127">ランタイム初期化オプションに関する情報を含んでいます。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4a0f-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="a4a0f-128">Remarks</span></span>  
 <span data-ttu-id="a4a0f-129">.NET Framework version 3.5 以前のバージョンで、CAS ポリシーは常に影響します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="a4a0f-130">[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]、CAS ポリシーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="a4a0f-131">CAS ポリシーは、バージョン固有です。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-131">CAS policy is version-specific.</span></span> <span data-ttu-id="a4a0f-132">.NET Framework の以前のバージョンに存在するカスタムの CAS ポリシーは、.NET Framework 4 で再度指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="a4a0f-133">適用する、`<NetFx40_LegacySecurityPolicy>`要素を[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]アセンブリには影響しません[セキュリティ透過的なコード](../../../../../docs/framework/misc/security-transparent-code.md); 透過性規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4a0f-134">適用、`<NetFx40_LegacySecurityPolicy>`要素により、大幅なパフォーマンスの低下によって作成されたネイティブ イメージ アセンブリ、[ネイティブ イメージ ジェネレーター (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md)でインストールされていない、[グローバル アセンブリ キャッシュ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="a4a0f-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="a4a0f-135">パフォーマンスの低下は、ランタイム属性が適用されるときに、ネイティブ イメージとして、アセンブリを読み込むことができないによる、として、just-in-time でアセンブリが読み込まれる結果的にします。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4a0f-136">Visual Studio プロジェクトのプロジェクトの設定で .NET Framework 4 より前であるターゲット .NET Framework のバージョンを指定する場合の CA ポリシーが有効に、そのバージョンの指定した任意のカスタムの CAS ポリシーを含みます。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-136">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="a4a0f-137">ただし、.NET Framework 4 の新しい型とメンバーを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-137">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="a4a0f-138">使用して、.NET Framework の以前のバージョンを指定することも、 [ \<supportedRuntime > 要素](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)でスタートアップ設定スキーマで、[アプリケーション構成ファイル](../../../../../docs/framework/configure-apps/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4a0f-139">構成ファイルの構文は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="a4a0f-140">構文と例のセクションで指定された構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a4a0f-141">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="a4a0f-141">Configuration File</span></span>  
 <span data-ttu-id="a4a0f-142">この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4a0f-143">例</span><span class="sxs-lookup"><span data-stu-id="a4a0f-143">Example</span></span>  
 <span data-ttu-id="a4a0f-144">次の例では、アプリケーションの従来の CAS ポリシーを有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a4a0f-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4a0f-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4a0f-145">See also</span></span>

- [<span data-ttu-id="a4a0f-146">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a4a0f-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a4a0f-147">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a4a0f-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
