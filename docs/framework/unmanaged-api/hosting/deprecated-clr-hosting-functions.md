---
title: 非推奨の CLR ホスト関数
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504369"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="4e819-102">非推奨の CLR ホスト関数</span><span class="sxs-lookup"><span data-stu-id="4e819-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="4e819-103">このセクションでは、以前のバージョンのホスト API で使用されていたアンマネージ グローバル静的関数について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e819-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="4e819-104">`_Cor*`.NET Framework によってのみ使用されるインフラストラクチャ関数 (functions) を除き、これらの関数は .NET Framework 4 で非推奨とされました。</span><span class="sxs-lookup"><span data-stu-id="4e819-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="4e819-105">アクティブ化関数</span><span class="sxs-lookup"><span data-stu-id="4e819-105">Activation functions</span></span>  
 [<span data-ttu-id="4e819-106">ClrCreateManagedInstance 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-106">ClrCreateManagedInstance Function</span></span>](clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="4e819-107">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-107">Deprecated.</span></span> <span data-ttu-id="4e819-108">指定したマネージド型のインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e819-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="4e819-109">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-109">CoInitializeCor Function</span></span>](coinitializecor-function.md)  
 <span data-ttu-id="4e819-110">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="4e819-110">Obsolete.</span></span> <span data-ttu-id="4e819-111">共通言語ランタイム (CLR) を初期化するには、 [Corbindtoruntimeex](corbindtoruntimeex-function.md)または[Corbindtoの entruntime](corbindtocurrentruntime-function.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e819-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="4e819-112">CoInitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-112">CoInitializeEE Function</span></span>](coinitializeee-function.md)  
 <span data-ttu-id="4e819-113">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-113">Deprecated.</span></span> <span data-ttu-id="4e819-114">CLR 実行エンジンがプロセスに読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4e819-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="4e819-115">代わりに[ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md)メソッドを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4e819-115">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="4e819-116">CorBindToCurrentRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-116">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)  
 <span data-ttu-id="4e819-117">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-117">Deprecated.</span></span> <span data-ttu-id="4e819-118">XML ファイルに格納されているバージョン情報を使用して、共通言語ランタイム (CLR: Common Language Runtime) をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4e819-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="4e819-119">CorBindToRuntime 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-119">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)  
 <span data-ttu-id="4e819-120">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-120">Deprecated.</span></span> <span data-ttu-id="4e819-121">アンマネージ ホストが CLR をプロセスに読み込めるようにします。</span><span class="sxs-lookup"><span data-stu-id="4e819-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="4e819-122">CorBindToRuntimeByCfg 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-122">CorBindToRuntimeByCfg Function</span></span>](corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="4e819-123">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-123">Deprecated.</span></span> <span data-ttu-id="4e819-124">XML ファイルから読み取ったバージョン情報を使用して、CLR をプロセスに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4e819-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="4e819-125">CorBindToRuntimeEx 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-125">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)  
 <span data-ttu-id="4e819-126">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-126">Deprecated.</span></span> <span data-ttu-id="4e819-127">アンマネージ ホストが CLR をプロセスに読み込めるようにします。CLR の動作を指定するフラグを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4e819-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="4e819-128">CorBindToRuntimeHost 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)  
 <span data-ttu-id="4e819-129">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-129">Deprecated.</span></span> <span data-ttu-id="4e819-130">指定したバージョンの CLR をホストがプロセスに読み込めるようにします。</span><span class="sxs-lookup"><span data-stu-id="4e819-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="4e819-131">GetCORRequiredVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-131">GetCORRequiredVersion Function</span></span>](getcorrequiredversion-function.md)  
 <span data-ttu-id="4e819-132">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-132">Deprecated.</span></span> <span data-ttu-id="4e819-133">必要な CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="4e819-134">GetCORSystemDirectory 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-134">GetCORSystemDirectory Function</span></span>](getcorsystemdirectory-function.md)  
 <span data-ttu-id="4e819-135">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-135">Deprecated.</span></span> <span data-ttu-id="4e819-136">プロセスに読み込まれた CLR のインストール ディレクトリを返します。</span><span class="sxs-lookup"><span data-stu-id="4e819-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="4e819-137">GetRealProcAddress 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-137">GetRealProcAddress Function</span></span>](getrealprocaddress-function.md)  
 <span data-ttu-id="4e819-138">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-138">Deprecated.</span></span> <span data-ttu-id="4e819-139">最後にインストールされたバージョンの CLR からエクスポートされる、指定した関数のアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="4e819-140">GetRequestedRuntimeInfo 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-140">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="4e819-141">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-141">Deprecated.</span></span> <span data-ttu-id="4e819-142">アプリケーションが要求した CLR についてのバージョン情報とディレクトリ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="4e819-143">CLR バージョン関数</span><span class="sxs-lookup"><span data-stu-id="4e819-143">CLR version functions</span></span>  
 <span data-ttu-id="4e819-144">このセクションの関数は、CLR のバージョンを返します。CLR をアクティブ化することはありません。</span><span class="sxs-lookup"><span data-stu-id="4e819-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="4e819-145">GetCORVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-145">GetCORVersion Function</span></span>](getcorversion-function.md)  
 <span data-ttu-id="4e819-146">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-146">Deprecated.</span></span> <span data-ttu-id="4e819-147">現在のプロセスで実行されている CLR のバージョン番号を返します。</span><span class="sxs-lookup"><span data-stu-id="4e819-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="4e819-148">GetFileVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-148">GetFileVersion Function</span></span>](getfileversion-function.md)  
 <span data-ttu-id="4e819-149">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-149">Deprecated.</span></span> <span data-ttu-id="4e819-150">指定したバッファーを使用して、指定したファイルの CLR バージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="4e819-151">GetRequestedRuntimeVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-151">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)  
 <span data-ttu-id="4e819-152">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-152">Deprecated.</span></span> <span data-ttu-id="4e819-153">指定したアプリケーションで要求される CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="4e819-154">そのバージョンがインストールされていない場合は、要求されるバージョンより前にインストールされた最も新しいバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="4e819-155">GetRequestedRuntimeVersionForCLSID 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="4e819-156">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-156">Deprecated.</span></span> <span data-ttu-id="4e819-157">指定の CLSID を持つクラスに対応した CLR バージョンの情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="4e819-158">GetVersionFromProcess 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-158">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)  
 <span data-ttu-id="4e819-159">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-159">Deprecated.</span></span> <span data-ttu-id="4e819-160">指定のプロセス ハンドルに関連付けられた CLR のバージョン番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="4e819-161">LockClrVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-161">LockClrVersion Function</span></span>](lockclrversion-function.md)  
 <span data-ttu-id="4e819-162">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-162">Deprecated.</span></span> <span data-ttu-id="4e819-163">プロセス内で使用する CLR のバージョンを、CLR を明示的に初期化する前にホストが決定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4e819-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="4e819-164">ホスト関数</span><span class="sxs-lookup"><span data-stu-id="4e819-164">Hosting functions</span></span>  
 [<span data-ttu-id="4e819-165">CallFunctionShim 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-165">CallFunctionShim Function</span></span>](callfunctionshim-function.md)  
 <span data-ttu-id="4e819-166">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-166">Deprecated.</span></span> <span data-ttu-id="4e819-167">指定したライブラリ内の関数を、名前とパラメーターを指定して呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4e819-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="4e819-168">CoEEShutDownCOM 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-168">CoEEShutDownCOM Function</span></span>](coeeshutdowncom-function.md)  
 <span data-ttu-id="4e819-169">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-169">Deprecated.</span></span> <span data-ttu-id="4e819-170">プロセスから COM アセンブリをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="4e819-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="4e819-171">CorExitProcess 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-171">CorExitProcess Function</span></span>](corexitprocess-function.md)  
 <span data-ttu-id="4e819-172">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-172">Deprecated.</span></span> <span data-ttu-id="4e819-173">現在のアンマネージ プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="4e819-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="4e819-174">CorLaunchApplication 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-174">CorLaunchApplication Function</span></span>](corlaunchapplication-function.md)  
 <span data-ttu-id="4e819-175">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-175">Deprecated.</span></span> <span data-ttu-id="4e819-176">指定したネットワーク パスのアプリケーションを、指定したマニフェストとその他のアプリケーション データを使用して起動します。</span><span class="sxs-lookup"><span data-stu-id="4e819-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="4e819-177">CorMarkThreadInThreadPool 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-177">CorMarkThreadInThreadPool Function</span></span>](cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="4e819-178">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-178">Deprecated.</span></span> <span data-ttu-id="4e819-179">現在実行されているスレッド プールのスレッドに、マネージド コードの実行のマークを付けます。</span><span class="sxs-lookup"><span data-stu-id="4e819-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="4e819-180">.NET Framework Version 2.0 以降では、この関数に効力はありません。</span><span class="sxs-lookup"><span data-stu-id="4e819-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="4e819-181">必ずしも必要はありませんが、この関数はコードから削除できます。</span><span class="sxs-lookup"><span data-stu-id="4e819-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="4e819-182">CoUninitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-182">CoUninitializeCor Function</span></span>](couninitializecor-function.md)  
 <span data-ttu-id="4e819-183">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="4e819-183">Obsolete.</span></span> <span data-ttu-id="4e819-184">プロセスから CLR をアンロードできません。</span><span class="sxs-lookup"><span data-stu-id="4e819-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="4e819-185">CoUninitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-185">CoUninitializeEE Function</span></span>](couninitializeee-function.md)  
 <span data-ttu-id="4e819-186">互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="4e819-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="4e819-187">CreateDebuggingInterfaceFromVersion 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-187">CreateDebuggingInterfaceFromVersion Function</span></span>](createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="4e819-188">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-188">Deprecated.</span></span> <span data-ttu-id="4e819-189">指定されたバージョン情報に基づいて[ICorDebug](../debugging/icordebug-interface.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e819-189">Creates an [ICorDebug](../debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="4e819-190">CreateICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-190">CreateICeeFileGen Function</span></span>](createiceefilegen-function.md)  
 <span data-ttu-id="4e819-191">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-191">Deprecated.</span></span> <span data-ttu-id="4e819-192">[ICeeFileGen](iceefilegen-class.md)オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e819-192">Creates an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="4e819-193">DestroyICeeFileGen 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-193">DestroyICeeFileGen Function</span></span>](destroyiceefilegen-function.md)  
 <span data-ttu-id="4e819-194">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-194">Deprecated.</span></span> <span data-ttu-id="4e819-195">[ICeeFileGen](iceefilegen-class.md)オブジェクトを破棄します。</span><span class="sxs-lookup"><span data-stu-id="4e819-195">Destroys an [ICeeFileGen](iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="4e819-196">FExecuteInAppDomainCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4e819-196">FExecuteInAppDomainCallback Function Pointer</span></span>](fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="4e819-197">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-197">Deprecated.</span></span> <span data-ttu-id="4e819-198">CLR がマネージド コードを実行するために呼び出す関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4e819-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="4e819-199">FLockClrVersionCallback 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4e819-199">FLockClrVersionCallback Function Pointer</span></span>](flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="4e819-200">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-200">Deprecated.</span></span> <span data-ttu-id="4e819-201">初期化が開始または完了したことをホストに通知するために CLR が呼び出す関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4e819-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="4e819-202">GetCLRIdentityManager 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-202">GetCLRIdentityManager Function</span></span>](getclridentitymanager-function.md)  
 <span data-ttu-id="4e819-203">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-203">Deprecated.</span></span> <span data-ttu-id="4e819-204">CLR が ID を管理できるようにするインターフェイスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e819-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="4e819-205">LoadLibraryShim 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-205">LoadLibraryShim Function</span></span>](loadlibraryshim-function.md)  
 <span data-ttu-id="4e819-206">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-206">Deprecated.</span></span> <span data-ttu-id="4e819-207">指定したバージョンの .NET Framework DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4e819-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="4e819-208">LoadStringRC 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-208">LoadStringRC Function</span></span>](loadstringrc-function.md)  
 <span data-ttu-id="4e819-209">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-209">Deprecated.</span></span> <span data-ttu-id="4e819-210">現在のスレッドの既定のカルチャを使用して、HRESULT 値をエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="4e819-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="4e819-211">LoadStringRCEx 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-211">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)  
 <span data-ttu-id="4e819-212">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-212">Deprecated.</span></span> <span data-ttu-id="4e819-213">HRESULT 値を、指定したカルチャの適切なエラー メッセージに変換します。</span><span class="sxs-lookup"><span data-stu-id="4e819-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="4e819-214">LPOVERLAPPED_COMPLETION_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4e819-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="4e819-215">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-215">Deprecated.</span></span> <span data-ttu-id="4e819-216">デバイスに対する重複 I/O (非同期 I/O) が完了したときに、ホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4e819-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="4e819-217">LPTHREAD_START_ROUTINE 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4e819-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="4e819-218">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-218">Deprecated.</span></span> <span data-ttu-id="4e819-219">スレッドの実行を開始したことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4e819-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="4e819-220">RunDll32ShimW 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-220">RunDll32ShimW Function</span></span>](rundll32shimw-function.md)  
 <span data-ttu-id="4e819-221">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-221">Deprecated.</span></span> <span data-ttu-id="4e819-222">指定されたコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e819-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="4e819-223">WAITORTIMERCALLBACK 関数ポインター</span><span class="sxs-lookup"><span data-stu-id="4e819-223">WAITORTIMERCALLBACK Function Pointer</span></span>](waitortimercallback-function-pointer.md)  
 <span data-ttu-id="4e819-224">非推奨になりました。</span><span class="sxs-lookup"><span data-stu-id="4e819-224">Deprecated.</span></span> <span data-ttu-id="4e819-225">待機ハンドルがシグナル状態になったこと、またはタイムアウトしたことをホストに通知する関数を指します。</span><span class="sxs-lookup"><span data-stu-id="4e819-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="4e819-226">インフラストラクチャ関数</span><span class="sxs-lookup"><span data-stu-id="4e819-226">Infrastructure functions</span></span>  
 <span data-ttu-id="4e819-227">このセクションの関数は、.NET Framework によってのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e819-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="4e819-228">_CorDllMain 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-228">_CorDllMain Function</span></span>](cordllmain-function.md)  
 <span data-ttu-id="4e819-229">CLR を初期化し、DLL アセンブリの CLR ヘッダーでマネージド エントリ ポイントを検索して、その実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="4e819-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="4e819-230">_CorExeMain 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-230">_CorExeMain Function</span></span>](corexemain-function.md)  
 <span data-ttu-id="4e819-231">CLR を初期化し、実行可能アセンブリの CLR ヘッダーでマネージド エントリ ポイントを検索して、その実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="4e819-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="4e819-232">_CorExeMain2 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-232">_CorExeMain2 Function</span></span>](corexemain2-function.md)  
 <span data-ttu-id="4e819-233">指定されたメモリ マップト コードのエントリ ポイントを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e819-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="4e819-234">この関数は、オペレーティング システム ローダーによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4e819-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="4e819-235">_CorImageUnloading 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-235">_CorImageUnloading Function</span></span>](corimageunloading-function.md)  
 <span data-ttu-id="4e819-236">マネージド モジュール イメージがアンロードされたときに、ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4e819-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="4e819-237">_CorValidateImage 関数</span><span class="sxs-lookup"><span data-stu-id="4e819-237">_CorValidateImage Function</span></span>](corvalidateimage-function.md)  
 <span data-ttu-id="4e819-238">マネージド モジュール イメージを検証し、それらが読み込まれると、オペレーティング システム ローダーに通知します。</span><span class="sxs-lookup"><span data-stu-id="4e819-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e819-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="4e819-239">See also</span></span>

- [<span data-ttu-id="4e819-240">.NET Framework 4 ホスト グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="4e819-240">.NET Framework 4 Hosting Global Static Functions</span></span>](net-framework-4-hosting-global-static-functions.md)
