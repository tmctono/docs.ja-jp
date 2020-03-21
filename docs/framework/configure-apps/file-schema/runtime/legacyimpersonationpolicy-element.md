---
title: <legacyImpersonationPolicy> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
ms.openlocfilehash: 5e43ead278ecd4049014f4000a2f056b2190f7e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154105"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="1bdf4-102">\<要素>偽装ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bdf4-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="1bdf4-103">Windows ID が、現在のスレッドの実行コンテキストのフロー設定に関係なく、非同期ポイント間でフローしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
<span data-ttu-id="1bdf4-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1bdf4-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="1bdf4-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="1bdf4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<レガシズマシポリシー>**</span><span class="sxs-lookup"><span data-stu-id="1bdf4-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyImpersonationPolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bdf4-107">構文</span><span class="sxs-lookup"><span data-stu-id="1bdf4-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bdf4-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1bdf4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1bdf4-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bdf4-110">属性</span><span class="sxs-lookup"><span data-stu-id="1bdf4-110">Attributes</span></span>  
  
|<span data-ttu-id="1bdf4-111">属性</span><span class="sxs-lookup"><span data-stu-id="1bdf4-111">Attribute</span></span>|<span data-ttu-id="1bdf4-112">説明</span><span class="sxs-lookup"><span data-stu-id="1bdf4-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1bdf4-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1bdf4-114">現在のスレッド<xref:System.Security.Principal.WindowsIdentity>のフロー設定に関係なく、非同期ポイント間<xref:System.Threading.ExecutionContext>でのフローを行わないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="1bdf4-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="1bdf4-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1bdf4-116">Value</span><span class="sxs-lookup"><span data-stu-id="1bdf4-116">Value</span></span>|<span data-ttu-id="1bdf4-117">説明</span><span class="sxs-lookup"><span data-stu-id="1bdf4-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1bdf4-118"><xref:System.Security.Principal.WindowsIdentity>現在のスレッドのフロー設定に<xref:System.Threading.ExecutionContext>応じて、非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="1bdf4-119">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1bdf4-120"><xref:System.Security.Principal.WindowsIdentity>は、現在のスレッドのフロー設定に<xref:System.Threading.ExecutionContext>関係なく、非同期ポイント間でフローしません。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bdf4-121">子要素</span><span class="sxs-lookup"><span data-stu-id="1bdf4-121">Child Elements</span></span>  
 <span data-ttu-id="1bdf4-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="1bdf4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1bdf4-123">親要素</span><span class="sxs-lookup"><span data-stu-id="1bdf4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1bdf4-124">要素</span><span class="sxs-lookup"><span data-stu-id="1bdf4-124">Element</span></span>|<span data-ttu-id="1bdf4-125">説明</span><span class="sxs-lookup"><span data-stu-id="1bdf4-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1bdf4-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1bdf4-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bdf4-128">解説</span><span class="sxs-lookup"><span data-stu-id="1bdf4-128">Remarks</span></span>  
 <span data-ttu-id="1bdf4-129">NET Framework バージョン 1.0 および 1.1<xref:System.Security.Principal.WindowsIdentity>では、 はユーザー定義の非同期ポイントを経由しません。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="1bdf4-130">.NET Framework Version 2.0 以降では、<xref:System.Threading.ExecutionContext>現在実行中のスレッドに関する情報を格納するオブジェクトがあり、アプリケーション ドメイン内の非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="1bdf4-131"><xref:System.Security.Principal.WindowsIdentity>この実行コンテキストに含まれるので、非同期ポイントをまた流れ、偽装コンテキストが存在する場合にもフローします。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="1bdf4-132">NET Framework 2.0 以降では、要素を`<legacyImpersonationPolicy>`使用して、非同期ポイント<xref:System.Security.Principal.WindowsIdentity>を渡って流れないことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bdf4-133">共通言語ランタイム (CLR) は、マネージ コードの外部で実行される偽装操作 (プラットフォーム呼び出しからアンマネージ コードへの呼び出し、Win32 関数への直接呼び出しなど) ではなく、マネージ コードのみを使用して実行される偽装操作を認識します。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="1bdf4-134">要素が<xref:System.Security.Principal.WindowsIdentity>true ( )`<alwaysFlowImpersonationPolicy enabled="true"/>`に設定`alwaysFlowImpersonationPolicy`されていない限り、非同期ポイントをまたいで流すことができるのはマネージ オブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="1bdf4-135">要素を`alwaysFlowImpersonationPolicy`true に設定すると、偽装の実行方法に関係なく、Windows ID が常に非同期ポイントをまたいでフローするように指定されます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="1bdf4-136">非同期ポイント間でアンマネージ偽装をフローする方法の詳細については[\<、「alwaysFlowImpersonationPolicy>要素](alwaysflowimpersonationpolicy-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="1bdf4-137">このデフォルトの動作は、他の 2 つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="1bdf4-138">スレッド単位でのマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="1bdf4-139">または<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>メソッドを使用して<xref:System.Threading.ExecutionContext>および の設定を変更することで、<xref:System.Security.SecurityContext>スレッド単位でフローを<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>抑制できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="1bdf4-140">共通言語ランタイム (CLR) を読み込むためのアンマネージ ホスト インターフェイスの呼び出しで。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="1bdf4-141">CLR の読み込みに、単純なマネージ実行可能ファイルではなく、アンマネージ ホスト インターフェイスを使用する場合は[、CorBindToRuntimeEx 関数関数関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)の呼び出しで特別なフラグを指定できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="1bdf4-142">プロセス全体の互換モードを有効にするには`flags`[、CorBindToRuntimeEx 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)のパラメーターをSTARTUP_LEGACY_IMPERSONATIONに設定します。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="1bdf4-143">詳細については、「[\<常にフロー偽装ポリシー>要素](alwaysflowimpersonationpolicy-element.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="1bdf4-144">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="1bdf4-144">Configuration File</span></span>  
 <span data-ttu-id="1bdf4-145">.NET Framework アプリケーションでは、この要素はアプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="1bdf4-146">ASP.NET アプリケーションの場合、偽装フローは\<、Windows フォルダ>\Microsoft.NET\Framework\vx.x.xxxx ディレクトリにある aspnet.config ファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="1bdf4-147">既定では、ASP.NET、次の構成設定を使用して aspnet.config ファイルの偽装フローを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="1bdf4-148">ASP.NETでは、偽装のフローを許可する場合は、次の構成設定を明示的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="1bdf4-149">例</span><span class="sxs-lookup"><span data-stu-id="1bdf4-149">Example</span></span>  
 <span data-ttu-id="1bdf4-150">次の例は、非同期ポイント間で Windows ID をフローしない従来の動作を指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bdf4-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bdf4-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bdf4-151">See also</span></span>

- [<span data-ttu-id="1bdf4-152">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="1bdf4-152">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1bdf4-153">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="1bdf4-153">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1bdf4-154">\<常にフロー偽装ポリシー>要素</span><span class="sxs-lookup"><span data-stu-id="1bdf4-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](alwaysflowimpersonationpolicy-element.md)
