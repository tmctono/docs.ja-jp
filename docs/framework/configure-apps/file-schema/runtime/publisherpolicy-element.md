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
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115843"
---
# <a name="publisherpolicy-element"></a><span data-ttu-id="1fc21-102">\<publisherPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="1fc21-102">\<publisherPolicy> Element</span></span>
<span data-ttu-id="1fc21-103">ランタイムが発行元ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<publisherPolicy>**  
  
## <a name="syntax"></a><span data-ttu-id="1fc21-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fc21-104">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1fc21-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1fc21-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1fc21-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1fc21-107">属性</span><span class="sxs-lookup"><span data-stu-id="1fc21-107">Attributes</span></span>  
  
|<span data-ttu-id="1fc21-108">属性</span><span class="sxs-lookup"><span data-stu-id="1fc21-108">Attribute</span></span>|<span data-ttu-id="1fc21-109">説明</span><span class="sxs-lookup"><span data-stu-id="1fc21-109">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="1fc21-110">発行者ポリシーを適用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-110">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="1fc21-111">属性の適用</span><span class="sxs-lookup"><span data-stu-id="1fc21-111">apply Attribute</span></span>  
  
|<span data-ttu-id="1fc21-112">値</span><span class="sxs-lookup"><span data-stu-id="1fc21-112">Value</span></span>|<span data-ttu-id="1fc21-113">Description</span><span class="sxs-lookup"><span data-stu-id="1fc21-113">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="1fc21-114">発行者ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-114">Applies publisher policy.</span></span> <span data-ttu-id="1fc21-115">これが既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="1fc21-115">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="1fc21-116">発行者ポリシーは適用されません。</span><span class="sxs-lookup"><span data-stu-id="1fc21-116">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1fc21-117">子要素</span><span class="sxs-lookup"><span data-stu-id="1fc21-117">Child Elements</span></span>  

<span data-ttu-id="1fc21-118">なし。</span><span class="sxs-lookup"><span data-stu-id="1fc21-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1fc21-119">親要素</span><span class="sxs-lookup"><span data-stu-id="1fc21-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1fc21-120">要素</span><span class="sxs-lookup"><span data-stu-id="1fc21-120">Element</span></span>|<span data-ttu-id="1fc21-121">Description</span><span class="sxs-lookup"><span data-stu-id="1fc21-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="1fc21-122">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="1fc21-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1fc21-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="1fc21-124">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-124">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="1fc21-125">`<dependentAssembly>`アセンブリごとに1つの要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="1fc21-125">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="1fc21-126">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1fc21-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fc21-127">解説</span><span class="sxs-lookup"><span data-stu-id="1fc21-127">Remarks</span></span>  
 <span data-ttu-id="1fc21-128">コンポーネントベンダーがアセンブリの新しいバージョンをリリースする場合、ベンダーには発行者ポリシーを含めることができるため、以前のバージョンを使用するアプリケーションでは新しいバージョンが使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1fc21-128">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="1fc21-129">特定のアセンブリに対して発行者ポリシーを適用するかどうかを指定するには、要素に要素を配置し **\<publisherPolicy>** **\<dependentAssembly>** ます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-129">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="1fc21-130">**適用**属性の既定の設定は **[はい]** です。</span><span class="sxs-lookup"><span data-stu-id="1fc21-130">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="1fc21-131">**適用**属性を [**いいえ** **]** に設定すると、アセンブリの以前のすべての設定がオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-131">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="1fc21-132">アプリケーションが [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) アプリケーション構成ファイルの要素を使用して発行者ポリシーを明示的に無視するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="1fc21-132">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="1fc21-133">権限は、にフラグを設定することによって付与され <xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission> ます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-133">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="1fc21-134">詳細については、「[アセンブリバインディングリダイレクトのセキュリティアクセス許可](../../assembly-binding-redirection-security-permission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fc21-134">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1fc21-135">例</span><span class="sxs-lookup"><span data-stu-id="1fc21-135">Example</span></span>  
 <span data-ttu-id="1fc21-136">次の例では、アセンブリの発行者ポリシーをオフにし `myAssembly` ます。</span><span class="sxs-lookup"><span data-stu-id="1fc21-136">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1fc21-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fc21-137">See also</span></span>

- [<span data-ttu-id="1fc21-138">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1fc21-138">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1fc21-139">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1fc21-139">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1fc21-140">ランタイムがアセンブリを検索する方法</span><span class="sxs-lookup"><span data-stu-id="1fc21-140">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="1fc21-141">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="1fc21-141">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
