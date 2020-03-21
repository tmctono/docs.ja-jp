---
title: <bindingRedirect> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/bindingRedirect
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bindingRedirect
helpviewer_keywords:
- <bindingRedirect> element
- container tags, <bindingRedirect> element
- bindingRedirect element
ms.assetid: 67784ecd-9663-434e-bd6a-26975e447ac0
ms.openlocfilehash: d96585b397f75dcb9fac7e7fce93799cc95e7c6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154297"
---
# <a name="bindingredirect-element"></a><span data-ttu-id="aa145-102">\<バインドリダイレクト>要素</span><span class="sxs-lookup"><span data-stu-id="aa145-102">\<bindingRedirect> Element</span></span>
<span data-ttu-id="aa145-103">1 つのアセンブリ バージョンを別のバージョンにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="aa145-103">Redirects one assembly version to another.</span></span>  
  
<span data-ttu-id="aa145-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa145-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aa145-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa145-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="aa145-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<アセンブリバインディング>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="aa145-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="aa145-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<従属アセンブリ>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="aa145-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="aa145-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<バインドリダイレクト>**</span><span class="sxs-lookup"><span data-stu-id="aa145-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bindingRedirect>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa145-109">構文</span><span class="sxs-lookup"><span data-stu-id="aa145-109">Syntax</span></span>  
  
```xml  
   <bindingRedirect
oldVersion="existing assembly version"  
newVersion="new assembly version"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa145-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa145-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aa145-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa145-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa145-112">属性</span><span class="sxs-lookup"><span data-stu-id="aa145-112">Attributes</span></span>  
  
|<span data-ttu-id="aa145-113">属性</span><span class="sxs-lookup"><span data-stu-id="aa145-113">Attribute</span></span>|<span data-ttu-id="aa145-114">説明</span><span class="sxs-lookup"><span data-stu-id="aa145-114">Description</span></span>|  
|---------------|-----------------|  
|`oldVersion`|<span data-ttu-id="aa145-115">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="aa145-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="aa145-116">初めに要求されていたアセンブリのバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa145-116">Specifies the version of the assembly that was originally requested.</span></span> <span data-ttu-id="aa145-117">アセンブリのバージョン番号の形式は *、メジャー.マイナー.ビルド.リビジョンです*。</span><span class="sxs-lookup"><span data-stu-id="aa145-117">The format of an assembly version number is *major.minor.build.revision*.</span></span> <span data-ttu-id="aa145-118">このバージョン番号の各部分で有効値は、0 ～ 65535 です。</span><span class="sxs-lookup"><span data-stu-id="aa145-118">Valid values for each part of this version number are 0 to 65535.</span></span><br /><br /> <span data-ttu-id="aa145-119">バージョン範囲は、次の形式でも指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa145-119">You can also specify a range of versions in the following format:</span></span><br /><br /> <span data-ttu-id="aa145-120">*n.n.n.n - n.n.n.n*</span><span class="sxs-lookup"><span data-stu-id="aa145-120">*n.n.n.n - n.n.n.n*</span></span>|  
|`newVersion`|<span data-ttu-id="aa145-121">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="aa145-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="aa145-122">最初に要求されたバージョンの代わりに使用するアセンブリのバージョンを *、次の*形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="aa145-122">Specifies the version of the assembly to use instead of the originally requested version in the format: *n.n.n.n*</span></span><br /><br /> <span data-ttu-id="aa145-123">この値では `oldVersion` より前のバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aa145-123">This value can specify an earlier version than `oldVersion`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa145-124">子要素</span><span class="sxs-lookup"><span data-stu-id="aa145-124">Child Elements</span></span>  
  
|<span data-ttu-id="aa145-125">要素</span><span class="sxs-lookup"><span data-stu-id="aa145-125">Element</span></span>|<span data-ttu-id="aa145-126">説明</span><span class="sxs-lookup"><span data-stu-id="aa145-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa145-127">なし</span><span class="sxs-lookup"><span data-stu-id="aa145-127">None</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="aa145-128">親要素</span><span class="sxs-lookup"><span data-stu-id="aa145-128">Parent Elements</span></span>  
  
|<span data-ttu-id="aa145-129">要素</span><span class="sxs-lookup"><span data-stu-id="aa145-129">Element</span></span>|<span data-ttu-id="aa145-130">説明</span><span class="sxs-lookup"><span data-stu-id="aa145-130">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="aa145-131">アセンブリ バージョンのリダイレクトおよびアセンブリの位置に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa145-131">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="aa145-132">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="aa145-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="aa145-133">各アセンブリのバインディング ポリシーとアセンブリの場所をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="aa145-133">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="aa145-134">アセンブリごとに 1 つの dependentAssembly 要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="aa145-134">Use one dependentAssembly element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="aa145-135">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="aa145-135">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa145-136">解説</span><span class="sxs-lookup"><span data-stu-id="aa145-136">Remarks</span></span>  
 <span data-ttu-id="aa145-137">厳密な名前付きアセンブリに対して .NET Framework アプリケーションを構築すると、実行時に新しいバージョンが利用できる場合でも、既定で、アプリケーションの構築時に使用したアセンブリのバージョンが使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa145-137">When you build a .NET Framework application against a strong-named assembly, the application uses that version of the assembly at run time by default, even if a new version is available.</span></span> <span data-ttu-id="aa145-138">ただし、新しいバージョンのアセンブリで実行するようにもアプリケーションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="aa145-138">However, you can configure the application to run against a newer version of the assembly.</span></span> <span data-ttu-id="aa145-139">ランタイムがこれらのファイルを使用して使用するアセンブリ バージョンを決定する方法の詳細については、「[ランタイムがアセンブリを検索する方法](../../../deployment/how-the-runtime-locates-assemblies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa145-139">For details on how the runtime uses these files to determine which assembly version to use, see [How the Runtime Locates Assemblies](../../../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="aa145-140">複数の `bindingRedirect` 要素を `dependentAssembly` 要素に含めることによって、複数のアセンブリ バージョンをリダイレクトできます。</span><span class="sxs-lookup"><span data-stu-id="aa145-140">You can redirect more than one assembly version by including multiple `bindingRedirect` elements in a `dependentAssembly` element.</span></span> <span data-ttu-id="aa145-141">また、アセンブリの新しいバージョンから古いバージョンにリダイレクトすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa145-141">You can also redirect from a newer version to an older version of the assembly.</span></span>  
  
 <span data-ttu-id="aa145-142">アプリケーション構成ファイルで明示的にアセンブリ バインディングをリダイレクトするには、セキュリティ アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="aa145-142">Explicit assembly binding redirection in an application configuration file requires a security permission.</span></span> <span data-ttu-id="aa145-143">これは、.NET Framework アセンブリおよびサードパーティ製アセンブリに適用されます。</span><span class="sxs-lookup"><span data-stu-id="aa145-143">This applies to redirection of .NET Framework assemblies and assemblies from third parties.</span></span> <span data-ttu-id="aa145-144">アクセス許可は、 にフラグ<xref:System.Security.Permissions.SecurityPermissionFlag>を設定することによって<xref:System.Security.Permissions.SecurityPermission>付与されます。</span><span class="sxs-lookup"><span data-stu-id="aa145-144">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="aa145-145">詳細については、「[アセンブリ バインディング リダイレクト セキュリティ 権限](../../assembly-binding-redirection-security-permission.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa145-145">For more information, see [Assembly Binding Redirection Security Permission](../../assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa145-146">例</span><span class="sxs-lookup"><span data-stu-id="aa145-146">Example</span></span>  
 <span data-ttu-id="aa145-147">あるアセンブリ バージョンを別のバージョンにリダイレクトする例を示します。</span><span class="sxs-lookup"><span data-stu-id="aa145-147">The following example shows how to redirect one assembly version to another.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa145-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa145-148">See also</span></span>

- [<span data-ttu-id="aa145-149">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="aa145-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="aa145-150">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="aa145-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="aa145-151">アセンブリ バージョンのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="aa145-151">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
