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
ms.openlocfilehash: aac7079d941e6774ca6c00fbece8ff72fbf3f0e1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663880"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="a1465-102">\<bypassTrustedAppStrongNames> 要素</span><span class="sxs-lookup"><span data-stu-id="a1465-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="a1465-103">完全に信頼<xref:System.AppDomain>されているアセンブリでの厳密な名前の検証をバイパスするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1465-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="a1465-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a1465-104">\<configuration></span></span>  
<span data-ttu-id="a1465-105">\<ランタイム ></span><span class="sxs-lookup"><span data-stu-id="a1465-105">\<runtime></span></span>  
<span data-ttu-id="a1465-106">\<Bypasstrustedappstrongnames> ></span><span class="sxs-lookup"><span data-stu-id="a1465-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1465-107">構文</span><span class="sxs-lookup"><span data-stu-id="a1465-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1465-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1465-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a1465-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1465-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1465-110">属性</span><span class="sxs-lookup"><span data-stu-id="a1465-110">Attributes</span></span>  
  
|<span data-ttu-id="a1465-111">属性</span><span class="sxs-lookup"><span data-stu-id="a1465-111">Attribute</span></span>|<span data-ttu-id="a1465-112">説明</span><span class="sxs-lookup"><span data-stu-id="a1465-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a1465-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="a1465-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1465-114">完全に信頼されたアセンブリの厳密な名前の検証を回避するバイパス機能が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a1465-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="a1465-115">この機能が有効になっている場合、アセンブリの読み込み時に厳密な名前が正しいかどうかは検証されません。</span><span class="sxs-lookup"><span data-stu-id="a1465-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="a1465-116">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="a1465-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1465-117">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="a1465-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="a1465-118">値</span><span class="sxs-lookup"><span data-stu-id="a1465-118">Value</span></span>|<span data-ttu-id="a1465-119">説明</span><span class="sxs-lookup"><span data-stu-id="a1465-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="a1465-120">完全に信頼されたアセンブリの厳密な名前の署名は、アセンブリが完全に信頼<xref:System.AppDomain>されているときには検証されません。</span><span class="sxs-lookup"><span data-stu-id="a1465-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="a1465-121">既定値です。</span><span class="sxs-lookup"><span data-stu-id="a1465-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="a1465-122">完全に信頼されたアセンブリの厳密な名前の署名は、アセンブリが完全信頼<xref:System.AppDomain>に読み込まれるときに検証されます。</span><span class="sxs-lookup"><span data-stu-id="a1465-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="a1465-123">厳密な名前の署名は、署名が正しいかどうかのみを確認します。一致のために別の厳密な名前と比較されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a1465-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1465-124">子要素</span><span class="sxs-lookup"><span data-stu-id="a1465-124">Child Elements</span></span>  
 <span data-ttu-id="a1465-125">なし。</span><span class="sxs-lookup"><span data-stu-id="a1465-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1465-126">親要素</span><span class="sxs-lookup"><span data-stu-id="a1465-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a1465-127">要素</span><span class="sxs-lookup"><span data-stu-id="a1465-127">Element</span></span>|<span data-ttu-id="a1465-128">説明</span><span class="sxs-lookup"><span data-stu-id="a1465-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1465-129">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="a1465-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1465-130">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a1465-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1465-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1465-131">Remarks</span></span>  
 <span data-ttu-id="a1465-132">厳密な名前のバイパス機能を使用すると、完全に信頼されたアセンブリに対する厳密な名前の署名の検証のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="a1465-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="a1465-133">バイ パス機能は、厳密な名前で署名されていて、次の特性を持つアセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="a1465-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
- <span data-ttu-id="a1465-134"><xref:System.Security.Policy.StrongName>証拠なしで完全に信頼されている`MyComputer` (たとえば、ゾーン証拠がある)。</span><span class="sxs-lookup"><span data-stu-id="a1465-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
- <span data-ttu-id="a1465-135">完全に信頼された <xref:System.AppDomain> に読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="a1465-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="a1465-136">その <xref:System.AppDomain> の <xref:System.AppDomainSetup.ApplicationBase%2A> プロパティに基づいた場所から読み込まれる。</span><span class="sxs-lookup"><span data-stu-id="a1465-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
- <span data-ttu-id="a1465-137">遅延署名されていない。</span><span class="sxs-lookup"><span data-stu-id="a1465-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1465-138">レジストリキーを使用して、コンピューター上のすべてのアプリケーションでバイパス機能が無効になっている場合、この構成ファイルの設定は無効です。</span><span class="sxs-lookup"><span data-stu-id="a1465-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="a1465-139">詳細については、「[方法 :厳密な名前のバイパス機能を無効にする](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1465-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1465-140">例</span><span class="sxs-lookup"><span data-stu-id="a1465-140">Example</span></span>  
 <span data-ttu-id="a1465-141">次の例は、完全に信頼されたアセンブリの厳密な名前の署名を検証する動作を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a1465-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1465-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1465-142">See also</span></span>

- [<span data-ttu-id="a1465-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="a1465-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a1465-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="a1465-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a1465-145">方法: 厳密な名前のバイパス機能を無効にする</span><span class="sxs-lookup"><span data-stu-id="a1465-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../app-domains/how-to-disable-the-strong-name-bypass-feature.md)
