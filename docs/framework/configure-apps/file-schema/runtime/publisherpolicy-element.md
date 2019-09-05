---
title: <publisherPolicy> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc206e584440778858e61fc0bab51fc8ffa2009a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252381"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="01a70-102">\<Publisherpolicy apply > 要素</span><span class="sxs-lookup"><span data-stu-id="01a70-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="01a70-103">ランタイムが発行元ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a70-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
<span data-ttu-id="01a70-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="01a70-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="01a70-105">&nbsp;&nbsp;[ **\<ランタイム >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="01a70-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="01a70-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="01a70-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="01a70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="01a70-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="01a70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Publisherpolicy apply >**</span><span class="sxs-lookup"><span data-stu-id="01a70-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01a70-109">構文</span><span class="sxs-lookup"><span data-stu-id="01a70-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01a70-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="01a70-110">Attributes and Elements</span></span>  
 <span data-ttu-id="01a70-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="01a70-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01a70-112">属性</span><span class="sxs-lookup"><span data-stu-id="01a70-112">Attributes</span></span>  
  
|<span data-ttu-id="01a70-113">属性</span><span class="sxs-lookup"><span data-stu-id="01a70-113">Attribute</span></span>|<span data-ttu-id="01a70-114">説明</span><span class="sxs-lookup"><span data-stu-id="01a70-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="01a70-115">発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="01a70-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="01a70-116">属性の適用</span><span class="sxs-lookup"><span data-stu-id="01a70-116">apply Attribute</span></span>  
  
|<span data-ttu-id="01a70-117">[値]</span><span class="sxs-lookup"><span data-stu-id="01a70-117">Value</span></span>|<span data-ttu-id="01a70-118">説明</span><span class="sxs-lookup"><span data-stu-id="01a70-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="01a70-119">発行者ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="01a70-119">Applies publisher policy.</span></span> <span data-ttu-id="01a70-120">これは、既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="01a70-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="01a70-121">発行者ポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="01a70-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01a70-122">子要素</span><span class="sxs-lookup"><span data-stu-id="01a70-122">Child Elements</span></span>  

<span data-ttu-id="01a70-123">なし。</span><span class="sxs-lookup"><span data-stu-id="01a70-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01a70-124">親要素</span><span class="sxs-lookup"><span data-stu-id="01a70-124">Parent Elements</span></span>  
  
|<span data-ttu-id="01a70-125">要素</span><span class="sxs-lookup"><span data-stu-id="01a70-125">Element</span></span>|<span data-ttu-id="01a70-126">説明</span><span class="sxs-lookup"><span data-stu-id="01a70-126">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="01a70-127">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01a70-127">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="01a70-128">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="01a70-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="01a70-129">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="01a70-129">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="01a70-130">アセンブリごと`<dependentAssembly>`に1つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="01a70-130">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="01a70-131">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="01a70-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01a70-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="01a70-132">Remarks</span></span>  
 <span data-ttu-id="01a70-133">コンポーネントベンダーがアセンブリの新しいバージョンをリリースする場合、ベンダーには発行者ポリシーを含めることができるため、以前のバージョンを使用するアプリケーションでは新しいバージョンが使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="01a70-133">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="01a70-134">特定のアセンブリに対して発行者ポリシーを適用するかどうかを指定するには、  **\<publisherpolicy apply >** 要素を **\<dependentAssembly >** 要素に配置します。</span><span class="sxs-lookup"><span data-stu-id="01a70-134">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="01a70-135">**適用**属性の既定の設定は **[はい]** です。</span><span class="sxs-lookup"><span data-stu-id="01a70-135">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="01a70-136">**適用**属性を [**いいえ** **]** に設定すると、アセンブリの以前のすべての設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="01a70-136">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="01a70-137">アプリケーション構成ファイルの[ \<publisherpolicy apply apply = "no"/>](publisherpolicy-element.md)要素を使用して、アプリケーションが発行者ポリシーを明示的に無視するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="01a70-137">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="01a70-138">権限は、 <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission>にフラグを設定することによって付与されます。</span><span class="sxs-lookup"><span data-stu-id="01a70-138">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="01a70-139">詳細については、「[アセンブリバインディングリダイレクトのセキュリティアクセス許可](../../assembly-binding-redirection-security-permission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01a70-139">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01a70-140">例</span><span class="sxs-lookup"><span data-stu-id="01a70-140">Example</span></span>  
 <span data-ttu-id="01a70-141">次の例では、アセンブリの発行者ポリシー `myAssembly`をオフにします。</span><span class="sxs-lookup"><span data-stu-id="01a70-141">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01a70-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="01a70-142">See also</span></span>

- [<span data-ttu-id="01a70-143">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="01a70-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="01a70-144">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="01a70-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="01a70-145">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="01a70-145">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="01a70-146">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="01a70-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
