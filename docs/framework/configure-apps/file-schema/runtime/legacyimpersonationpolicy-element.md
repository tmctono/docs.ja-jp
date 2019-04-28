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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c39ee551dde19d87a75403f3db7433d1ef829f3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704636"
---
# <a name="legacyimpersonationpolicy-element"></a><span data-ttu-id="58385-102">\<legacyImpersonationPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="58385-102">\<legacyImpersonationPolicy> Element</span></span>
<span data-ttu-id="58385-103">Windows ID が、現在のスレッドの実行コンテキストのフロー設定に関係なく、非同期ポイント間でフローしないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="58385-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="58385-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="58385-104">\<configuration></span></span>  
<span data-ttu-id="58385-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="58385-105">\<runtime></span></span>  
<span data-ttu-id="58385-106">\<legacyImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="58385-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58385-107">構文</span><span class="sxs-lookup"><span data-stu-id="58385-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58385-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="58385-108">Attributes and Elements</span></span>  
 <span data-ttu-id="58385-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="58385-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58385-110">属性</span><span class="sxs-lookup"><span data-stu-id="58385-110">Attributes</span></span>  
  
|<span data-ttu-id="58385-111">属性</span><span class="sxs-lookup"><span data-stu-id="58385-111">Attribute</span></span>|<span data-ttu-id="58385-112">説明</span><span class="sxs-lookup"><span data-stu-id="58385-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="58385-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="58385-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="58385-114">指定します、<xref:System.Security.Principal.WindowsIdentity>が非同期ポイント間をフローしないに関係なく、<xref:System.Threading.ExecutionContext>フローの現在のスレッドで設定します。</span><span class="sxs-lookup"><span data-stu-id="58385-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="58385-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="58385-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="58385-116">値</span><span class="sxs-lookup"><span data-stu-id="58385-116">Value</span></span>|<span data-ttu-id="58385-117">説明</span><span class="sxs-lookup"><span data-stu-id="58385-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="58385-118"><xref:System.Security.Principal.WindowsIdentity> に応じて非同期ポイント間のフロー、<xref:System.Threading.ExecutionContext>フロー、現在のスレッドを設定します。</span><span class="sxs-lookup"><span data-stu-id="58385-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="58385-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="58385-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="58385-120"><xref:System.Security.Principal.WindowsIdentity> 非同期ポイント間をフローしないに関係なく、<xref:System.Threading.ExecutionContext>フローの現在のスレッドで設定します。</span><span class="sxs-lookup"><span data-stu-id="58385-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58385-121">子要素</span><span class="sxs-lookup"><span data-stu-id="58385-121">Child Elements</span></span>  
 <span data-ttu-id="58385-122">なし。</span><span class="sxs-lookup"><span data-stu-id="58385-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58385-123">親要素</span><span class="sxs-lookup"><span data-stu-id="58385-123">Parent Elements</span></span>  
  
|<span data-ttu-id="58385-124">要素</span><span class="sxs-lookup"><span data-stu-id="58385-124">Element</span></span>|<span data-ttu-id="58385-125">説明</span><span class="sxs-lookup"><span data-stu-id="58385-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="58385-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="58385-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="58385-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="58385-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58385-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="58385-128">Remarks</span></span>  
 <span data-ttu-id="58385-129">.NET Framework バージョン 1.0 および 1.1 で、<xref:System.Security.Principal.WindowsIdentity>任意のユーザー定義の非同期ポイント間をフローしません。</span><span class="sxs-lookup"><span data-stu-id="58385-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="58385-130">以降、.NET Framework version 2.0 では、ある、<xref:System.Threading.ExecutionContext>と現在実行中のスレッドに関する情報を含むオブジェクトがアプリケーション ドメイン内での非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="58385-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="58385-131"><xref:System.Security.Principal.WindowsIdentity>この実行コンテキストが用意されており、したがってもポイント間をフロー、非同期、つまり、権限借用コンテキストが存在する場合、これがフローするもします。</span><span class="sxs-lookup"><span data-stu-id="58385-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="58385-132">以降、.NET Framework 2.0 を使えば、`<legacyImpersonationPolicy>`ことを指定する要素<xref:System.Security.Principal.WindowsIdentity>非同期ポイント間をフローしません。</span><span class="sxs-lookup"><span data-stu-id="58385-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58385-133">共通言語ランタイム (CLR) は、プラットフォームを通じてなど、マネージ コードの外部で実行する権限借用のではありませんのマネージ コードを使用して実行される操作は、アンマネージ コードに、または Win32 関数への直接の呼び出しを呼び出す権限借用に注意してください。</span><span class="sxs-lookup"><span data-stu-id="58385-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="58385-134">マネージのみ<xref:System.Security.Principal.WindowsIdentity>しない限り、非同期ポイント間でオブジェクトが流れることができる、`alwaysFlowImpersonationPolicy`要素が設定されているを true に (`<alwaysFlowImpersonationPolicy enabled="true"/>`)。</span><span class="sxs-lookup"><span data-stu-id="58385-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="58385-135">設定、 `alwaysFlowImpersonationPolicy` true 要素では、Windows id が偽装の実行方法に関係なく、非同期ポイント間で常にフローを指定します。</span><span class="sxs-lookup"><span data-stu-id="58385-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="58385-136">詳細についてはフローの情報では、権限借用をアンマネージ非同期ポイント間を参照してください[ \<alwaysFlowImpersonationPolicy > 要素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="58385-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="58385-137">他の 2 つの方法でこの既定の動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="58385-137">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="58385-138">スレッドごとにマネージ コードは。</span><span class="sxs-lookup"><span data-stu-id="58385-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="58385-139">スレッドごとのフローを抑制するには変更することによって、<xref:System.Threading.ExecutionContext>と<xref:System.Security.SecurityContext>設定を使用して、 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>、<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>または<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="58385-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="58385-140">で、共通言語ランタイム (CLR) を読み込むアンマネージ ホスト インターフェイスへの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="58385-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="58385-141">呼び出しで特別なフラグを指定するには、CLR を読み込めません (単純なマネージ実行可能ファイル) ではなく、アンマネージ ホスト インターフェイスを使用する場合、 [CorBindToRuntimeEx 関数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="58385-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="58385-142">プロセス全体の互換モードを有効にするには設定、`flags`パラメーター [CorBindToRuntimeEx 関数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)STARTUP_LEGACY_IMPERSONATION にします。</span><span class="sxs-lookup"><span data-stu-id="58385-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="58385-143">詳細については、次を参照してください。、 [ \<alwaysFlowImpersonationPolicy > 要素](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)します。</span><span class="sxs-lookup"><span data-stu-id="58385-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="58385-144">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="58385-144">Configuration File</span></span>  
 <span data-ttu-id="58385-145">.NET Framework アプリケーションでは、この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="58385-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="58385-146">見つかった aspnet.config ファイルで、ASP.NET アプリケーションの権限借用のフローを構成できます、 \<Windows フォルダー > \Microsoft.NET\Framework\vx.x.xxxx ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="58385-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="58385-147">既定では ASP.NET では、次の構成設定を使用して、aspnet.config ファイルで権限借用のフローを無効にします。</span><span class="sxs-lookup"><span data-stu-id="58385-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
``` xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="58385-148">ASP.NET では、代わりに、権限借用のフローを許可する場合は、する必要があります明示的に使用する次の構成設定。</span><span class="sxs-lookup"><span data-stu-id="58385-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="58385-149">例</span><span class="sxs-lookup"><span data-stu-id="58385-149">Example</span></span>  
 <span data-ttu-id="58385-150">次の例では、非同期ポイント間、Windows id をフローしない従来の動作を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="58385-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58385-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="58385-151">See also</span></span>

- [<span data-ttu-id="58385-152">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="58385-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="58385-153">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="58385-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="58385-154">\<alwaysFlowImpersonationPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="58385-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
