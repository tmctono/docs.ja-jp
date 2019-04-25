---
title: 非推奨の CLR ホスト関数
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa84ca0defd173563817673aad183a8b64226d41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905971"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="0caa3-102">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="0caa3-103">このセクションでは、以前のバージョンのホスト API で使用されていたアンマネージ グローバル静的関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="0caa3-104">.NET Framework によってのみ使用されるインフラストラクチャ関数 (`_Cor*` 関数) を除き、これらの関数は [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] では非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="0caa3-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="0caa3-105">アクティブ化関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-105">Activation functions</span></span>  
 [<span data-ttu-id="0caa3-106">ClrCreateManagedInstance 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="0caa3-107">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-107">Deprecated.</span></span> <span data-ttu-id="0caa3-108">指定したマネージド型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="0caa3-109">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="0caa3-110">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="0caa3-110">Obsolete.</span></span> <span data-ttu-id="0caa3-111">共通言語ランタイム (CLR) を初期化するためにいずれかの操作を使用して[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)または[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="0caa3-112">CoInitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="0caa3-113">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-113">Deprecated.</span></span> <span data-ttu-id="0caa3-114">CLR 実行エンジンがプロセスに読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="0caa3-115">使用して、 [iclrruntimehost::start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="0caa3-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="0caa3-116">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="0caa3-117">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-117">Deprecated.</span></span> <span data-ttu-id="0caa3-118">XML ファイルに格納されているバージョン情報を使用して、共通言語ランタイム (CLR: Common Language Runtime) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="0caa3-119">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="0caa3-120">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-120">Deprecated.</span></span> <span data-ttu-id="0caa3-121">アンマネージ ホストが CLR をプロセスに読み込めるようにします。</span><span class="sxs-lookup"><span data-stu-id="0caa3-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="0caa3-122">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="0caa3-123">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-123">Deprecated.</span></span> <span data-ttu-id="0caa3-124">XML ファイルから読み取ったバージョン情報を使用して、CLR をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="0caa3-125">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="0caa3-126">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-126">Deprecated.</span></span> <span data-ttu-id="0caa3-127">アンマネージ ホストが CLR をプロセスに読み込めるようにします。CLR の動作を指定するフラグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="0caa3-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="0caa3-129">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-129">Deprecated.</span></span> <span data-ttu-id="0caa3-130">指定したバージョンの CLR をホストがプロセスに読み込めるようにします。</span><span class="sxs-lookup"><span data-stu-id="0caa3-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="0caa3-131">GetCORRequiredVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="0caa3-132">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-132">Deprecated.</span></span> <span data-ttu-id="0caa3-133">必要な CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="0caa3-134">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="0caa3-135">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-135">Deprecated.</span></span> <span data-ttu-id="0caa3-136">プロセスに読み込まれた CLR のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="0caa3-137">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="0caa3-138">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-138">Deprecated.</span></span> <span data-ttu-id="0caa3-139">最後にインストールされたバージョンの CLR からエクスポートされる、指定した関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="0caa3-140">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="0caa3-141">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-141">Deprecated.</span></span> <span data-ttu-id="0caa3-142">アプリケーションが要求した CLR についてのバージョン情報とディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="0caa3-143">CLR バージョン関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-143">CLR version functions</span></span>  
 <span data-ttu-id="0caa3-144">このセクションの関数は、CLR のバージョンを返します。CLR をアクティブ化することはありません。</span><span class="sxs-lookup"><span data-stu-id="0caa3-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="0caa3-145">GetCORVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="0caa3-146">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-146">Deprecated.</span></span> <span data-ttu-id="0caa3-147">現在のプロセスで実行されている CLR のバージョン番号を返します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="0caa3-148">GetFileVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="0caa3-149">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-149">Deprecated.</span></span> <span data-ttu-id="0caa3-150">指定したバッファーを使用して、指定したファイルの CLR バージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="0caa3-151">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="0caa3-152">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-152">Deprecated.</span></span> <span data-ttu-id="0caa3-153">指定したアプリケーションで要求される CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="0caa3-154">そのバージョンがインストールされていない場合は、要求されるバージョンより前にインストールされた最も新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="0caa3-155">GetRequestedRuntimeVersionForCLSID 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="0caa3-156">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-156">Deprecated.</span></span> <span data-ttu-id="0caa3-157">指定の CLSID を持つクラスに対応した CLR バージョンの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="0caa3-158">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="0caa3-159">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-159">Deprecated.</span></span> <span data-ttu-id="0caa3-160">指定のプロセス ハンドルに関連付けられた CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="0caa3-161">LockClrVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="0caa3-162">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-162">Deprecated.</span></span> <span data-ttu-id="0caa3-163">プロセス内で使用する CLR のバージョンを、CLR を明示的に初期化する前にホストが決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0caa3-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="0caa3-164">ホスト関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-164">Hosting functions</span></span>  
 [<span data-ttu-id="0caa3-165">CallFunctionShim 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="0caa3-166">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-166">Deprecated.</span></span> <span data-ttu-id="0caa3-167">指定したライブラリ内の関数を、名前とパラメーターを指定して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="0caa3-168">CoEEShutDownCOM 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="0caa3-169">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-169">Deprecated.</span></span> <span data-ttu-id="0caa3-170">プロセスから COM アセンブリをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="0caa3-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="0caa3-171">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="0caa3-172">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-172">Deprecated.</span></span> <span data-ttu-id="0caa3-173">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="0caa3-174">CorLaunchApplication 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="0caa3-175">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-175">Deprecated.</span></span> <span data-ttu-id="0caa3-176">指定したネットワーク パスのアプリケーションを、指定したマニフェストとその他のアプリケーション データを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="0caa3-177">CorMarkThreadInThreadPool 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="0caa3-178">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-178">Deprecated.</span></span> <span data-ttu-id="0caa3-179">現在実行されているスレッド プールのスレッドに、マネージド コードの実行のマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="0caa3-180">.NET Framework Version 2.0 以降では、この関数に効力はありません。</span><span class="sxs-lookup"><span data-stu-id="0caa3-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="0caa3-181">必ずしも必要はありませんが、この関数はコードから削除できます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="0caa3-182">CoUninitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="0caa3-183">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="0caa3-183">Obsolete.</span></span> <span data-ttu-id="0caa3-184">プロセスから CLR をアンロードできません。</span><span class="sxs-lookup"><span data-stu-id="0caa3-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="0caa3-185">CoUninitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="0caa3-186">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="0caa3-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="0caa3-187">CreateDebuggingInterfaceFromVersion 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="0caa3-188">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-188">Deprecated.</span></span> <span data-ttu-id="0caa3-189">作成、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)オブジェクトが指定されたバージョン情報に基づきます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="0caa3-190">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="0caa3-191">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-191">Deprecated.</span></span> <span data-ttu-id="0caa3-192">作成、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0caa3-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="0caa3-193">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="0caa3-194">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-194">Deprecated.</span></span> <span data-ttu-id="0caa3-195">破棄、 [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="0caa3-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="0caa3-196">FExecuteInAppDomainCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="0caa3-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="0caa3-197">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-197">Deprecated.</span></span> <span data-ttu-id="0caa3-198">CLR がマネージド コードを実行するために呼び出す関数を指します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="0caa3-199">FLockClrVersionCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="0caa3-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="0caa3-200">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-200">Deprecated.</span></span> <span data-ttu-id="0caa3-201">初期化が開始または完了したことをホストに通知するために CLR が呼び出す関数を指します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="0caa3-202">GetCLRIdentityManager 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="0caa3-203">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-203">Deprecated.</span></span> <span data-ttu-id="0caa3-204">CLR が ID を管理できるようにするインターフェイスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="0caa3-205">LoadLibraryShim 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="0caa3-206">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-206">Deprecated.</span></span> <span data-ttu-id="0caa3-207">指定したバージョンの .NET Framework DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="0caa3-208">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="0caa3-209">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-209">Deprecated.</span></span> <span data-ttu-id="0caa3-210">現在のスレッドの既定のカルチャを使用して、HRESULT 値をエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="0caa3-211">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="0caa3-212">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-212">Deprecated.</span></span> <span data-ttu-id="0caa3-213">HRESULT 値を、指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="0caa3-214">LPOVERLAPPED_COMPLETION_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="0caa3-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="0caa3-215">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-215">Deprecated.</span></span> <span data-ttu-id="0caa3-216">デバイスに対する重複 I/O (非同期 I/O) が完了したときに、ホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="0caa3-217">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="0caa3-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="0caa3-218">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-218">Deprecated.</span></span> <span data-ttu-id="0caa3-219">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="0caa3-220">RunDll32ShimW 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="0caa3-221">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-221">Deprecated.</span></span> <span data-ttu-id="0caa3-222">指定されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="0caa3-223">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="0caa3-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="0caa3-224">非推奨。</span><span class="sxs-lookup"><span data-stu-id="0caa3-224">Deprecated.</span></span> <span data-ttu-id="0caa3-225">待機ハンドルがシグナル状態になったこと、またはタイムアウトしたことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="0caa3-226">インフラストラクチャ関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-226">Infrastructure functions</span></span>  
 <span data-ttu-id="0caa3-227">このセクションの関数は、.NET Framework によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="0caa3-228">_CorDllMain 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="0caa3-229">CLR を初期化し、DLL アセンブリの CLR ヘッダーでマネージド エントリ ポイントを検索して、その実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="0caa3-230">_CorExeMain 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="0caa3-231">CLR を初期化し、実行可能アセンブリの CLR ヘッダーでマネージド エントリ ポイントを検索して、その実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="0caa3-232">_CorExeMain2 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="0caa3-233">指定されたメモリ マップト コードのエントリ ポイントを実行します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="0caa3-234">この関数は、オペレーティング システム ローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="0caa3-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="0caa3-235">_CorImageUnloading 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="0caa3-236">マネージド モジュール イメージがアンロードされたときに、ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="0caa3-237">_CorValidateImage 関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="0caa3-238">マネージド モジュール イメージを検証し、それらが読み込まれると、オペレーティング システム ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="0caa3-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0caa3-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="0caa3-239">See also</span></span>

- [<span data-ttu-id="0caa3-240">.NET Framework 4 ホスト グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="0caa3-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
