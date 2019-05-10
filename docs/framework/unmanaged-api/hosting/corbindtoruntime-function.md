---
title: CorBindToRuntime 関数
ms.date: 03/30/2017
api_name:
- CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntime
helpviewer_keywords:
- CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93300ba84dea17b52303a78d3729cbf4f761ba4f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64634865"
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="42de5-102">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="42de5-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="42de5-103">アンマネージ ホストが共通言語ランタイム (CLR: Common Language Runtime) をプロセスに読み込むことを有効にします。</span><span class="sxs-lookup"><span data-stu-id="42de5-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="42de5-104">この関数は、[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="42de5-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42de5-105">構文</span><span class="sxs-lookup"><span data-stu-id="42de5-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42de5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="42de5-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="42de5-107">[入力] 読み込む CLR のバージョンを示す文字列。</span><span class="sxs-lookup"><span data-stu-id="42de5-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="42de5-108">.NET Framework のバージョン番号はピリオドで区切られた 4 つの部分で構成されます: *major.minor.build.revision*します。</span><span class="sxs-lookup"><span data-stu-id="42de5-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="42de5-109">`pwszVersion` として渡される文字列は、文字 "v" で始まり、バージョン番号の最初の 3 つの部分がその後に続く必要があります (たとえば "v1.0.1529")。</span><span class="sxs-lookup"><span data-stu-id="42de5-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="42de5-110">いくつかのバージョンの CLR は、以前のバージョンの CLR との互換性を指定するポリシー ステートメントと共にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="42de5-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="42de5-111">既定では、スタートアップ shim により、ポリシー ステートメントに対して `pwszVersion` が評価され、要求されたバージョンと互換性がある最新バージョンのランタイムが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="42de5-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="42de5-112">ホストは shim に対し、次に示すように `pwszVersion` パラメーターで値 `STARTUP_LOADER_SAFEMODE` を渡すことにより、ポリシー評価を省略し、`flags` で指定されたバージョンとまったく同じバージョンを読み込ませることができます。</span><span class="sxs-lookup"><span data-stu-id="42de5-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="42de5-113">呼び出し元が null を指定する場合`pwszVersion`ランタイムの最新バージョンが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="42de5-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="42de5-114">ホストするランタイムのバージョンが読み込まれていないコントロールは、null を渡すことです。</span><span class="sxs-lookup"><span data-stu-id="42de5-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="42de5-115">状況によってはこのような方法が適切なこともありますが、読み込むバージョンを特定させておくことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="42de5-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="42de5-116">[入力] CLR のサーバー ビルドまたはワークステーション ビルドのどちらを読み込むかを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="42de5-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="42de5-117">有効値は `svr` または `wks` です。</span><span class="sxs-lookup"><span data-stu-id="42de5-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="42de5-118">ワークステーション ビルドはシングルプロセッサ コンピューターでクライアント アプリケーションを実行するために最適化され、サーバー ビルドはガベージ コレクションでマルチ プロセッサを利用するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="42de5-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="42de5-119">場合`pwszBuildFlavor`に設定されている null の場合、ワークステーション ビルドが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="42de5-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="42de5-120">シングル プロセッサ コンピューターでを実行するときに常にワークステーション ビルドが読み込まれて、たとえ`pwszBuildFlavor`に設定されている`svr`します。</span><span class="sxs-lookup"><span data-stu-id="42de5-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="42de5-121">ただし場合、`pwszBuildFlavor`に設定されている`svr`と同時実行ガベージ コレクションの指定 (の説明を参照して、`flags`パラメーター)、サーバー ビルドが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="42de5-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="42de5-122">[in]`CLSID`のいずれかを実装するコクラスの[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)または[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="42de5-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="42de5-123">サポートされている値は CLSID_CorRuntimeHost と CLSID_CLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="42de5-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="42de5-124">[入力] 要求された `IID` のインターフェイスの `rclsid`。</span><span class="sxs-lookup"><span data-stu-id="42de5-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="42de5-125">サポートされている値は IID_ICorRuntimeHost と IID_ICLRRuntimeHost です。</span><span class="sxs-lookup"><span data-stu-id="42de5-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="42de5-126">[出力] 返された `riid` へのインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="42de5-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42de5-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="42de5-127">Remarks</span></span>  
 <span data-ttu-id="42de5-128">`pwszVersion` で指定したランタイムのバージョンが存在しない場合は、`CorBindToRuntimeEx` は CLR_E_SHIM_RUNTIMELOAD の HRESULT 値を返します。</span><span class="sxs-lookup"><span data-stu-id="42de5-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="42de5-129">Windows ID の実行コンテキストとフロー</span><span class="sxs-lookup"><span data-stu-id="42de5-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="42de5-130">CLR のバージョン 1 では、<xref:System.Security.Principal.WindowsIdentity> オブジェクトは、新しいスレッド、スレッド プール、タイマー コールバックなどの非同期ポイント間をフローしません。</span><span class="sxs-lookup"><span data-stu-id="42de5-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="42de5-131">CLR のバージョン 2.0 では、<xref:System.Threading.ExecutionContext> オブジェクトは現在実行しているスレッドに関する情報をラップして非同期ポイント間をフローしますが、アプリケーション ドメインの境界を越えることはありません。</span><span class="sxs-lookup"><span data-stu-id="42de5-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="42de5-132">同様に、<xref:System.Security.Principal.WindowsIdentity> オブジェクトもすべての非同期ポイント間をフローします。</span><span class="sxs-lookup"><span data-stu-id="42de5-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="42de5-133">したがって、現在スレッドに偽装がある場合は、その偽装もフローします。</span><span class="sxs-lookup"><span data-stu-id="42de5-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="42de5-134">2 つの方法のいずれかでフローを変更できます。</span><span class="sxs-lookup"><span data-stu-id="42de5-134">You can alter the flow in two ways:</span></span>  
  
1. <span data-ttu-id="42de5-135"><xref:System.Threading.ExecutionContext> 設定を変更し、スレッド単位ではフローしないようにします (<xref:System.Threading.ExecutionContext.SuppressFlow%2A>、<xref:System.Security.SecurityContext.SuppressFlow%2A>、および <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> の各メソッドを参照)。</span><span class="sxs-lookup"><span data-stu-id="42de5-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2. <span data-ttu-id="42de5-136">処理の既定のモードを、現在のスレッドの <xref:System.Security.Principal.WindowsIdentity> 設定がどの状態でも <xref:System.Threading.ExecutionContext> オブジェクトは非同期ポイント間をフローしない、バージョン 1 互換モードに変更します。</span><span class="sxs-lookup"><span data-stu-id="42de5-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="42de5-137">既定のモードを変更する方法は、CLR を読み込むときにマネージド実行可能ファイルを使用するか、アンマネージド ホスト インターフェイスを使用するかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="42de5-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1. <span data-ttu-id="42de5-138">マネージ実行可能ファイル、設定する必要があります、`enabled`の属性、 [ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)要素`true`します。</span><span class="sxs-lookup"><span data-stu-id="42de5-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2. <span data-ttu-id="42de5-139">アンマネージ ホスト インターフェイスを使用する場合は、`STARTUP_LEGACY_IMPERSONATION` 関数を呼び出すときの `flags` パラメーターに `CorBindToRuntimeEx` フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="42de5-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="42de5-140">バージョン 1 互換モードは、その処理全体および処理のすべてのアプリケーション ドメインに適用されます。</span><span class="sxs-lookup"><span data-stu-id="42de5-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42de5-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="42de5-141">Remarks</span></span>  
 <span data-ttu-id="42de5-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)と`CorBindToRuntime`同じ操作の実行が、`CorBindToRuntimeEx`関数では、CLR の動作を指定するフラグを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="42de5-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42de5-143">必要条件</span><span class="sxs-lookup"><span data-stu-id="42de5-143">Requirements</span></span>  
 <span data-ttu-id="42de5-144">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42de5-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42de5-145">**ヘッダー:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42de5-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42de5-146">**ライブラリ:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42de5-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42de5-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42de5-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42de5-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="42de5-148">See also</span></span>

- [<span data-ttu-id="42de5-149">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="42de5-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="42de5-150">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="42de5-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)
- [<span data-ttu-id="42de5-151">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="42de5-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="42de5-152">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="42de5-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="42de5-153">ICorRuntimeHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="42de5-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="42de5-154">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="42de5-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
