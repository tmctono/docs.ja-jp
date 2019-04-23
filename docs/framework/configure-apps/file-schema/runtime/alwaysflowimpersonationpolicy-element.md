---
title: <alwaysFlowImpersonationPolicy> 要素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec411039363cfb118fee06dff88daf50bbc97a86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314777"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="b70f0-102">\<alwaysFlowImpersonationPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="b70f0-103">偽装の実行方法に関係なく、Windows ID が常に非同期ポイント間でフローすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="b70f0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b70f0-104">\<configuration></span></span>  
<span data-ttu-id="b70f0-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b70f0-105">\<runtime></span></span>  
<span data-ttu-id="b70f0-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="b70f0-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b70f0-107">構文</span><span class="sxs-lookup"><span data-stu-id="b70f0-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b70f0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b70f0-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b70f0-110">属性</span><span class="sxs-lookup"><span data-stu-id="b70f0-110">Attributes</span></span>  
  
|<span data-ttu-id="b70f0-111">属性</span><span class="sxs-lookup"><span data-stu-id="b70f0-111">Attribute</span></span>|<span data-ttu-id="b70f0-112">説明</span><span class="sxs-lookup"><span data-stu-id="b70f0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b70f0-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="b70f0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b70f0-114">Windows id が非同期ポイント間でフローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b70f0-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="b70f0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b70f0-116">値</span><span class="sxs-lookup"><span data-stu-id="b70f0-116">Value</span></span>|<span data-ttu-id="b70f0-117">説明</span><span class="sxs-lookup"><span data-stu-id="b70f0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b70f0-118">管理されているメソッドをなどで、権限の借用を実行しない限り、id が、非同期ポイント間でフローしない Windows<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="b70f0-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="b70f0-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b70f0-120">Windows id は、偽装の実行方法に関係なく、非同期ポイント間で常にフローします。</span><span class="sxs-lookup"><span data-stu-id="b70f0-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b70f0-121">子要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-121">Child Elements</span></span>  
 <span data-ttu-id="b70f0-122">なし。</span><span class="sxs-lookup"><span data-stu-id="b70f0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b70f0-123">親要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b70f0-124">要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-124">Element</span></span>|<span data-ttu-id="b70f0-125">説明</span><span class="sxs-lookup"><span data-stu-id="b70f0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b70f0-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b70f0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b70f0-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b70f0-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b70f0-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="b70f0-128">Remarks</span></span>  
 <span data-ttu-id="b70f0-129">.NET Framework バージョン 1.0 および 1.1 では、Windows id が非同期ポイント間をフローしません。</span><span class="sxs-lookup"><span data-stu-id="b70f0-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="b70f0-130">.NET Framework version 2.0 では、<xref:System.Threading.ExecutionContext>オブジェクトを現在実行中のスレッドに関する情報を含み、アプリケーション ドメイン内での非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="b70f0-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="b70f0-131"><xref:System.Security.Principal.WindowsIdentity>またメソッドの管理を使用して、権限の借用が行われた指定された、非同期ポイント間をフロー情報の一部としてフローなど<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>platform などの他の方法ではなくネイティブ メソッドを呼び出すとします。</span><span class="sxs-lookup"><span data-stu-id="b70f0-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="b70f0-132">この要素を使用して、Windows id は、権限借用の実現方法に関係なく、非同期ポイント間でフローことを指定します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="b70f0-133">他の 2 つの方法でこの既定の動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b70f0-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="b70f0-134">スレッドごとにマネージ コードは。</span><span class="sxs-lookup"><span data-stu-id="b70f0-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="b70f0-135">スレッドごとのフローを抑制するには変更することによって、<xref:System.Threading.ExecutionContext>と<xref:System.Security.SecurityContext>設定を使用して、 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>、 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>、または<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>メソッド。</span><span class="sxs-lookup"><span data-stu-id="b70f0-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="b70f0-136">で、共通言語ランタイム (CLR) を読み込むアンマネージ ホスト インターフェイスへの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="b70f0-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="b70f0-137">呼び出しで特別なフラグを指定するには、CLR を読み込めません (単純なマネージ実行可能ファイル) ではなく、アンマネージ ホスト インターフェイスを使用する場合、 [CorBindToRuntimeEx 関数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="b70f0-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="b70f0-138">プロセス全体の互換モードを有効にするには設定、`flags`パラメーター [CorBindToRuntimeEx 関数](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)に`STARTUP_ALWAYSFLOW_IMPERSONATION`します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b70f0-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="b70f0-139">Configuration File</span></span>  
 <span data-ttu-id="b70f0-140">.NET Framework アプリケーションでは、この要素は、アプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b70f0-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="b70f0-141">見つかった aspnet.config ファイルで、ASP.NET アプリケーションの権限借用のフローを構成できます、 \<Windows フォルダー > \Microsoft.NET\Framework\vx.x.xxxx ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="b70f0-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="b70f0-142">既定では ASP.NET では、次の構成設定を使用して、aspnet.config ファイルで権限借用のフローを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b70f0-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="b70f0-143">ASP.NET では、代わりに、権限借用のフローを許可する場合は、する必要があります明示的に使用する次の構成設定。</span><span class="sxs-lookup"><span data-stu-id="b70f0-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b70f0-144">例</span><span class="sxs-lookup"><span data-stu-id="b70f0-144">Example</span></span>  
 <span data-ttu-id="b70f0-145">次の例では、Windows id を権限の借用は、マネージ メソッド以外の方法によって実現している場合でも、非同期ポイント間でフローするかを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b70f0-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b70f0-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="b70f0-146">See also</span></span>

- [<span data-ttu-id="b70f0-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="b70f0-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b70f0-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="b70f0-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="b70f0-149">\<legacyImpersonationPolicy > 要素</span><span class="sxs-lookup"><span data-stu-id="b70f0-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
