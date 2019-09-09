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
ms.openlocfilehash: 164492eb1abc7329481f158963118b47d2c4aebc
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252861"
---
# <a name="alwaysflowimpersonationpolicy-element"></a><span data-ttu-id="cf461-102">\<alwaysFlowImpersonationPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="cf461-102">\<alwaysFlowImpersonationPolicy> Element</span></span>
<span data-ttu-id="cf461-103">偽装の実行方法に関係なく、Windows ID が常に非同期ポイント間でフローすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf461-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
<span data-ttu-id="cf461-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf461-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cf461-105">&nbsp;&nbsp;[ **\<runtime>** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="cf461-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cf461-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<alwaysFlowImpersonationPolicy>** </span><span class="sxs-lookup"><span data-stu-id="cf461-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<alwaysFlowImpersonationPolicy>**</span></span>\  
  
## <a name="syntax"></a><span data-ttu-id="cf461-107">構文</span><span class="sxs-lookup"><span data-stu-id="cf461-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cf461-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cf461-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cf461-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf461-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cf461-110">属性</span><span class="sxs-lookup"><span data-stu-id="cf461-110">Attributes</span></span>  
  
|<span data-ttu-id="cf461-111">属性</span><span class="sxs-lookup"><span data-stu-id="cf461-111">Attribute</span></span>|<span data-ttu-id="cf461-112">説明</span><span class="sxs-lookup"><span data-stu-id="cf461-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="cf461-113">必須の属性です。</span><span class="sxs-lookup"><span data-stu-id="cf461-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="cf461-114">Windows id が非同期ポイント間でフローするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="cf461-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cf461-115">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="cf461-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="cf461-116">値</span><span class="sxs-lookup"><span data-stu-id="cf461-116">Value</span></span>|<span data-ttu-id="cf461-117">説明</span><span class="sxs-lookup"><span data-stu-id="cf461-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="cf461-118">など<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>のマネージメソッドを使用して偽装を実行しない限り、Windows id は非同期ポイント間ではフローしません。</span><span class="sxs-lookup"><span data-stu-id="cf461-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="cf461-119">既定値です。</span><span class="sxs-lookup"><span data-stu-id="cf461-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="cf461-120">Windows id は、偽装がどのように実行されたかに関係なく、常に非同期のポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="cf461-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cf461-121">子要素</span><span class="sxs-lookup"><span data-stu-id="cf461-121">Child Elements</span></span>  
 <span data-ttu-id="cf461-122">なし。</span><span class="sxs-lookup"><span data-stu-id="cf461-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cf461-123">親要素</span><span class="sxs-lookup"><span data-stu-id="cf461-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cf461-124">要素</span><span class="sxs-lookup"><span data-stu-id="cf461-124">Element</span></span>|<span data-ttu-id="cf461-125">説明</span><span class="sxs-lookup"><span data-stu-id="cf461-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cf461-126">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cf461-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cf461-127">アセンブリのバインディングとガベージ コレクションに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf461-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cf461-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf461-128">Remarks</span></span>  
 <span data-ttu-id="cf461-129">.NET Framework バージョン1.0 および1.1 では、Windows id は非同期ポイント間ではフローしません。</span><span class="sxs-lookup"><span data-stu-id="cf461-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="cf461-130">.NET Framework バージョン2.0 では、現在実行中<xref:System.Threading.ExecutionContext>のスレッドに関する情報を格納するオブジェクトがあり、アプリケーションドメイン内の非同期ポイント間でフローします。</span><span class="sxs-lookup"><span data-stu-id="cf461-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="cf461-131">また<xref:System.Security.Principal.WindowsIdentity> 、は、非同期ポイント全体をフローする情報の一部としてもフローします。これは、など<xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>のマネージメソッドを使用して偽装が行われた場合に、ネイティブメソッドへのプラットフォーム呼び出しなどの他の方法を使用して行われなかった場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="cf461-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="cf461-132">この要素は、偽装がどのように実現されたかに関係なく、Windows id が非同期ポイント間でフローすることを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf461-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="cf461-133">この既定の動作は、次の2つの方法で変更できます。</span><span class="sxs-lookup"><span data-stu-id="cf461-133">You can alter this default behavior in two other ways:</span></span>  
  
1. <span data-ttu-id="cf461-134">マネージコード内で、スレッド単位で。</span><span class="sxs-lookup"><span data-stu-id="cf461-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="cf461-135"><xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>、 <xref:System.Threading.ExecutionContext> <xref:System.Security.SecurityContext> 、また<xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType>はメソッドを使用しておよび設定を変更することで、スレッド単位でフローを抑制できます。 <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cf461-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="cf461-136">アンマネージホストインターフェイスを呼び出して、共通言語ランタイム (CLR) を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="cf461-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="cf461-137">アンマネージホストインターフェイス (単純なマネージ実行可能ファイルではなく) を使用して CLR を読み込む場合は、 [Corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)関数の呼び出しで特別なフラグを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf461-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="cf461-138">プロセス全体で互換モードを有効にするには、 `flags` [corbindtoruntimeex 関数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)のパラメーターを`STARTUP_ALWAYSFLOW_IMPERSONATION`に設定します。</span><span class="sxs-lookup"><span data-stu-id="cf461-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cf461-139">構成ファイル</span><span class="sxs-lookup"><span data-stu-id="cf461-139">Configuration File</span></span>  
 <span data-ttu-id="cf461-140">.NET Framework アプリケーションでは、この要素はアプリケーション構成ファイルでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf461-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="cf461-141">ASP.NET アプリケーションの場合、偽装フローは、 \<Windows フォルダー > \Microsoft.NET\Framework\vx.x.xxxx ディレクトリにある aspnet ファイルで構成できます。</span><span class="sxs-lookup"><span data-stu-id="cf461-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="cf461-142">ASP.NET は、既定では、次の構成設定を使用して、aspnet ファイル内の偽装フローを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cf461-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="cf461-143">ASP.NET で、代わりに偽装のフローを許可する場合は、次の構成設定を明示的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf461-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="cf461-144">例</span><span class="sxs-lookup"><span data-stu-id="cf461-144">Example</span></span>  
 <span data-ttu-id="cf461-145">次の例では、マネージメソッド以外の方法で権限借用が行われた場合でも、Windows id を非同期ポイント間でフローするように指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cf461-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf461-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf461-146">See also</span></span>

- [<span data-ttu-id="cf461-147">ランタイム設定スキーマ</span><span class="sxs-lookup"><span data-stu-id="cf461-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cf461-148">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="cf461-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cf461-149">\<legacyImpersonationPolicy> 要素</span><span class="sxs-lookup"><span data-stu-id="cf461-149">\<legacyImpersonationPolicy> Element</span></span>](legacyimpersonationpolicy-element.md)
