---
title: <bypassTrustedAppStrongNames> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674208"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="ea07c-102">\<bypassTrustedAppStrongNames> 要素</span><span class="sxs-lookup"><span data-stu-id="ea07c-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="ea07c-103">完全信頼に読み込まれる完全に信頼されたアセンブリに厳密な名前の検証をバイパスするかどうかを指定します<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="ea07c-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="ea07c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ea07c-104">\<configuration></span></span>  
<span data-ttu-id="ea07c-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ea07c-105">\<runtime></span></span>  
<span data-ttu-id="ea07c-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="ea07c-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea07c-107">構文</span><span class="sxs-lookup"><span data-stu-id="ea07c-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea07c-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ea07c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ea07c-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea07c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea07c-110">属性</span><span class="sxs-lookup"><span data-stu-id="ea07c-110">Attributes</span></span>  
  
|<span data-ttu-id="ea07c-111">属性</span><span class="sxs-lookup"><span data-stu-id="ea07c-111">Attribute</span></span>|<span data-ttu-id="ea07c-112">説明</span><span class="sxs-lookup"><span data-stu-id="ea07c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ea07c-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="ea07c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ea07c-114">完全信頼アセンブリの厳密な名前の検証を回避するバイパス機能が有効になっているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea07c-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="ea07c-115">この機能を有効にすると、アセンブリが読み込まれると正確性の厳密な名前は検証されません。</span><span class="sxs-lookup"><span data-stu-id="ea07c-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="ea07c-116">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="ea07c-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ea07c-117">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="ea07c-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="ea07c-118">値</span><span class="sxs-lookup"><span data-stu-id="ea07c-118">Value</span></span>|<span data-ttu-id="ea07c-119">説明</span><span class="sxs-lookup"><span data-stu-id="ea07c-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="ea07c-120">アセンブリが完全信頼に読み込まれるときに、完全信頼アセンブリの厳密な名前の署名は検証されません<xref:System.AppDomain>します。</span><span class="sxs-lookup"><span data-stu-id="ea07c-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ea07c-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="ea07c-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="ea07c-122">アセンブリが完全信頼に読み込まれるときに完全信頼アセンブリの厳密な名前の署名は検証<xref:System.AppDomain>です。</span><span class="sxs-lookup"><span data-stu-id="ea07c-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ea07c-123">署名の正確性ののみ、厳密な名前の署名がチェックします。別の厳密な名前の一致しないと比較されます。</span><span class="sxs-lookup"><span data-stu-id="ea07c-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea07c-124">子要素</span><span class="sxs-lookup"><span data-stu-id="ea07c-124">Child Elements</span></span>  
 <span data-ttu-id="ea07c-125">なし。</span><span class="sxs-lookup"><span data-stu-id="ea07c-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea07c-126">親要素</span><span class="sxs-lookup"><span data-stu-id="ea07c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ea07c-127">要素</span><span class="sxs-lookup"><span data-stu-id="ea07c-127">Element</span></span>|<span data-ttu-id="ea07c-128">説明</span><span class="sxs-lookup"><span data-stu-id="ea07c-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ea07c-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="ea07c-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ea07c-130">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea07c-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea07c-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="ea07c-131">Remarks</span></span>  
 <span data-ttu-id="ea07c-132">厳密な名前のバイパス機能は、完全信頼アセンブリの厳密な名前の署名の検証のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ea07c-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="ea07c-133">バイ パス機能は、厳密な名前で署名されていて、次の特性を持つアセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ea07c-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="ea07c-134">なく完全に信頼された、<xref:System.Security.Policy.StrongName>証拠 (たとえば、`MyComputer`ゾーン証拠)。</span><span class="sxs-lookup"><span data-stu-id="ea07c-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="ea07c-135">完全に信頼された <xref:System.AppDomain> に読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="ea07c-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="ea07c-136">その <xref:System.AppDomain> の <xref:System.AppDomainSetup.ApplicationBase%2A> プロパティに基づいた場所から読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="ea07c-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="ea07c-137">遅延署名されていない。</span><span class="sxs-lookup"><span data-stu-id="ea07c-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea07c-138">バイパス機能がオフになっているコンピューター上のすべてのアプリケーションのレジストリ キーを使用して場合は、この構成ファイルの設定に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="ea07c-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="ea07c-139">詳細については、「[方法 :厳密な名前のバイパス機能を無効にする](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea07c-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea07c-140">例</span><span class="sxs-lookup"><span data-stu-id="ea07c-140">Example</span></span>  
 <span data-ttu-id="ea07c-141">次の例では、完全信頼アセンブリの厳密な名前の署名を検証する動作を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ea07c-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea07c-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea07c-142">See also</span></span>

- [<span data-ttu-id="ea07c-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="ea07c-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ea07c-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ea07c-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ea07c-145">方法: 厳密な名前のバイパス機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="ea07c-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
