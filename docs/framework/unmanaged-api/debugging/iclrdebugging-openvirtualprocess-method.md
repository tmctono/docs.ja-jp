---
title: ICLRDebugging::OpenVirtualProcess メソッド
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 585b3d605d0df9169c12ca10198846ec0a7fe6d4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793610"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="c55ca-102">ICLRDebugging::OpenVirtualProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="c55ca-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="c55ca-103">プロセスに読み込まれた共通言語ランタイム (CLR) モジュールに対応する、コンポーネントインターフェイスを取得します。</span><span class="sxs-lookup"><span data-stu-id="c55ca-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55ca-104">構文</span><span class="sxs-lookup"><span data-stu-id="c55ca-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c55ca-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c55ca-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="c55ca-106">からターゲットプロセス内のモジュールのベースアドレス。</span><span class="sxs-lookup"><span data-stu-id="c55ca-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="c55ca-107">指定したモジュールが CLR モジュールでない場合、COR_E_NOT_CLR が返されます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="c55ca-108">からマネージデバッガーがプロセスの状態を検査できるデータターゲットの抽象化。</span><span class="sxs-lookup"><span data-stu-id="c55ca-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="c55ca-109">デバッガーでは、、のように、によっては、[このインターフェイスを](icordebugdatatarget-interface.md)実装してください。</span><span class="sxs-lookup"><span data-stu-id="c55ca-109">The debugger must implement the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="c55ca-110">デバッグ対象の CLR がコンピューターにローカルにインストールされていないシナリオをサポートするには、 [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)インターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c55ca-110">You should implement the [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="c55ca-111">からライブラリプロバイダーのコールバックインターフェイス。バージョン固有のデバッグライブラリをオンデマンドで検索し、読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="c55ca-112">このパラメーターは、`ppProcess` または `pFlags` が `null`ない場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="c55ca-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="c55ca-113">からこのデバッガーがデバッグできる CLR の最大バージョン。</span><span class="sxs-lookup"><span data-stu-id="c55ca-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="c55ca-114">このデバッガーでサポートされている最新の CLR バージョンからメジャー、マイナー、ビルドの各バージョンを指定し、将来の CLR サービスリリースに対応するためにリビジョン番号を65535に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c55ca-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="c55ca-115">から取得するコード処理インターフェイスの ID。</span><span class="sxs-lookup"><span data-stu-id="c55ca-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="c55ca-116">現時点で許容される値は、IID_CORDEBUGPROCESS3、IID_CORDEBUGPROCESS2、および IID_CORDEBUGPROCESS だけです。</span><span class="sxs-lookup"><span data-stu-id="c55ca-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="c55ca-117">入出力`riidProcess`によって識別される COM インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c55ca-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="c55ca-118">[入力、出力]CLR のバージョン。</span><span class="sxs-lookup"><span data-stu-id="c55ca-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="c55ca-119">入力時には、この値を `null`できます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-119">On input, this value can be `null`.</span></span> <span data-ttu-id="c55ca-120">また、 [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md)構造体を指すこともできます。この場合、構造体の `wStructVersion` フィールドを 0 (ゼロ) に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c55ca-120">It can also point to a [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="c55ca-121">出力時には、返された `CLR_DEBUGGING_VERSION` 構造体に CLR のバージョン情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="c55ca-122">入出力指定されたランタイムに関する情報フラグ。</span><span class="sxs-lookup"><span data-stu-id="c55ca-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="c55ca-123">フラグの説明については、 [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md)のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ca-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c55ca-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="c55ca-124">Return Value</span></span>  
 <span data-ttu-id="c55ca-125">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="c55ca-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c55ca-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c55ca-126">HRESULT</span></span>|<span data-ttu-id="c55ca-127">説明</span><span class="sxs-lookup"><span data-stu-id="c55ca-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c55ca-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="c55ca-128">S_OK</span></span>|<span data-ttu-id="c55ca-129">メソッドは正常に終了しました。</span><span class="sxs-lookup"><span data-stu-id="c55ca-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="c55ca-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c55ca-130">E_POINTER</span></span>|<span data-ttu-id="c55ca-131">`pDataTarget` は `null`です。</span><span class="sxs-lookup"><span data-stu-id="c55ca-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="c55ca-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="c55ca-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="c55ca-133">[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md)コールバックによってエラーが返されたか、有効なハンドルが提供されていません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-133">The [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="c55ca-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="c55ca-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="c55ca-135">`pDataTarget` は、このバージョンのランタイムに必要なデータターゲットインターフェイスを実装していません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="c55ca-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="c55ca-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="c55ca-137">指定されたモジュールは CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="c55ca-138">この HRESULT は、メモリが破損している、モジュールが使用できない、または CLR バージョンが shim バージョンより後であるために CLR モジュールが検出できない場合にも返されます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="c55ca-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="c55ca-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="c55ca-140">このランタイムバージョンでは、このデバッグモデルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="c55ca-141">現時点では、.NET Framework 4 より前のバージョンの CLR では、デバッグモデルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="c55ca-142">このエラーが発生した後も、`pwszVersion` 出力パラメーターは正しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="c55ca-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="c55ca-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="c55ca-144">CLR のバージョンが、このデバッガーがサポートするために要求するバージョンよりも大きくなっています。</span><span class="sxs-lookup"><span data-stu-id="c55ca-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="c55ca-145">このエラーが発生した後も、`pwszVersion` 出力パラメーターは正しい値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="c55ca-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="c55ca-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="c55ca-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="c55ca-147">`riidProcess` インターフェイスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="c55ca-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="c55ca-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="c55ca-149">`CLR_DEBUGGING_VERSION` 構造体には、`wStructVersion`に対して認識される値がありません。</span><span class="sxs-lookup"><span data-stu-id="c55ca-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="c55ca-150">現時点で許容される値は0のみです。</span><span class="sxs-lookup"><span data-stu-id="c55ca-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c55ca-151">例外</span><span class="sxs-lookup"><span data-stu-id="c55ca-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c55ca-152">コメント</span><span class="sxs-lookup"><span data-stu-id="c55ca-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55ca-153">要件</span><span class="sxs-lookup"><span data-stu-id="c55ca-153">Requirements</span></span>  
 <span data-ttu-id="c55ca-154">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c55ca-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55ca-155">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c55ca-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c55ca-156">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c55ca-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c55ca-157">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55ca-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55ca-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="c55ca-158">See also</span></span>

- [<span data-ttu-id="c55ca-159">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c55ca-159">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c55ca-160">デバッグ</span><span class="sxs-lookup"><span data-stu-id="c55ca-160">Debugging</span></span>](index.md)
