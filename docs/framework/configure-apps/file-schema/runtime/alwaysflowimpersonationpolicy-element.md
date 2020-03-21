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
ms.openlocfilehash: 7c8ac37932a528ff0f000cbaab49124dec51b88c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154484"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="c4298-102">\<alwaysFlowImpersonationPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="c4298-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="c4298-103">偽装の実行方法に関係なく、Windows ID が常に非同期ポイント間でフローすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4298-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="c4298-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4298-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c4298-105">&nbsp;&nbsp;[**\<ランタイム>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c4298-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c4298-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<常にフロー偽装ポリシー>**</span><span class="sxs-lookup"><span data-stu-id="c4298-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="c4298-107">構文</span><span class="sxs-lookup"><span data-stu-id="c4298-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4298-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4298-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c4298-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4298-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4298-110">属性</span><span class="sxs-lookup"><span data-stu-id="c4298-110">Attributes</span></span>  
  
|<span data-ttu-id="c4298-111">属性</span><span class="sxs-lookup"><span data-stu-id="c4298-111">Attribute</span></span>|<span data-ttu-id="c4298-112">説明</span><span class="sxs-lookup"><span data-stu-id="c4298-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="c4298-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="c4298-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="c4298-114">Windows ID が非同期ポイントをまたいでフローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c4298-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c4298-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="c4298-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="c4298-116">Value</span><span class="sxs-lookup"><span data-stu-id="c4298-116">Value</span></span>|<span data-ttu-id="c4298-117">説明</span><span class="sxs-lookup"><span data-stu-id="c4298-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="c4298-118">Windows ID は、偽装がなどの<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>マネージ メソッドを通じて実行されない限り、非同期ポイントをまたいでフローしません。</span><span class="sxs-lookup"><span data-stu-id="c4298-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="c4298-119">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="c4298-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="c4298-120">Windows ID は、偽装の実行方法に関係なく、常に非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="c4298-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4298-121">子要素</span><span class="sxs-lookup"><span data-stu-id="c4298-121">Child Elements</span></span>  
 <span data-ttu-id="c4298-122">[なし] :</span><span class="sxs-lookup"><span data-stu-id="c4298-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4298-123">親要素</span><span class="sxs-lookup"><span data-stu-id="c4298-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c4298-124">要素</span><span class="sxs-lookup"><span data-stu-id="c4298-124">Element</span></span>|<span data-ttu-id="c4298-125">説明</span><span class="sxs-lookup"><span data-stu-id="c4298-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c4298-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c4298-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c4298-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4298-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4298-128">解説</span><span class="sxs-lookup"><span data-stu-id="c4298-128">Remarks</span></span>  
 <span data-ttu-id="c4298-129">.NET Framework バージョン 1.0 および 1.1 では、Windows ID は非同期ポイントを渡ってフローしません。</span><span class="sxs-lookup"><span data-stu-id="c4298-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="c4298-130">.NET Framework Version 2.0 には、<xref:System.Threading.ExecutionContext>現在実行中のスレッドに関する情報を格納し、アプリケーション ドメイン内の非同期ポイントを渡ってその情報を格納するオブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="c4298-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="c4298-131">また<xref:System.Security.Principal.WindowsIdentity>、ネイティブ メソッドへのプラットフォーム呼び出しなどの<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>他の方法ではなくマネージ メソッドを使用して偽装が実現された場合、非同期ポイントを流れる情報の一部としてもフローします。</span><span class="sxs-lookup"><span data-stu-id="c4298-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="c4298-132">この要素は、偽装の実行方法に関係なく、Windows ID が非同期ポイントを渡ってフローすることを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c4298-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="c4298-133">このデフォルトの動作は、他の 2 つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="c4298-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="c4298-134">スレッド単位でのマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="c4298-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="c4298-135"><xref:System.Threading.ExecutionContext>の<xref:System.Security.SecurityContext>設定を変更して、スレッド単位でフローを<xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType><xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>抑制できます。</span><span class="sxs-lookup"><span data-stu-id="c4298-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="c4298-136">共通言語ランタイム (CLR) を読み込むためのアンマネージ ホスト インターフェイスの呼び出しで。</span><span class="sxs-lookup"><span data-stu-id="c4298-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="c4298-137">CLR の読み込みに、単純なマネージ実行可能ファイルではなく、アンマネージ ホスト インターフェイスを使用する場合は[、CorBindToRuntimeEx 関数関数関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)の呼び出しで特別なフラグを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c4298-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="c4298-138">プロセス全体の互換モードを有効にするには`flags`[、CorBindToRuntimeEx 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)のパラメーターを に`STARTUP_ALWAYSFLOW_IMPERSONATION`設定します。</span><span class="sxs-lookup"><span data-stu-id="c4298-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c4298-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="c4298-139">Configuration File</span></span>  
 <span data-ttu-id="c4298-140">.NET Framework アプリケーションでは、この要素はアプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4298-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="c4298-141">ASP.NET アプリケーションの場合、偽装フローは\<、Windows フォルダ>\Microsoft.NET\Framework\vx.x.xxxx ディレクトリにある aspnet.config ファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4298-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="c4298-142">既定では、ASP.NET、次の構成設定を使用して aspnet.config ファイルの偽装フローを無効にします。</span><span class="sxs-lookup"><span data-stu-id="c4298-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c4298-143">ASP.NETでは、偽装のフローを許可する場合は、次の構成設定を明示的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4298-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="c4298-144">例</span><span class="sxs-lookup"><span data-stu-id="c4298-144">Example</span></span>  
 <span data-ttu-id="c4298-145">次の例は、マネージ メソッド以外の方法で偽装が実現された場合でも、Windows ID が非同期ポイントをまたいで流れるよう指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c4298-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4298-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4298-146">See also</span></span>

- [<span data-ttu-id="c4298-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="c4298-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c4298-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c4298-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c4298-149">\<要素>偽装ポリシー</span><span class="sxs-lookup"><span data-stu-id="c4298-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
