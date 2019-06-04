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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d530f37c979a1ecddf2cb3895234aab2f7556b88
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489631"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a><span data-ttu-id="faaeb-102">ICLRDebugging::OpenVirtualProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="faaeb-102">ICLRDebugging::OpenVirtualProcess Method</span></span>
<span data-ttu-id="faaeb-103">ICorDebugProcess インターフェイスに対応するプロセスに読み込まれている共通言語ランタイム (CLR) モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-103">Gets the ICorDebugProcess interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faaeb-104">構文</span><span class="sxs-lookup"><span data-stu-id="faaeb-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="faaeb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="faaeb-105">Parameters</span></span>  
 `moduleBaseAddress`  
 <span data-ttu-id="faaeb-106">[in]ターゲット プロセスのモジュールのベース アドレス。</span><span class="sxs-lookup"><span data-stu-id="faaeb-106">[in] The base address of a module in the target process.</span></span> <span data-ttu-id="faaeb-107">COR_E_NOT_CLR が、指定したモジュールが CLR モジュールではない場合に返されます。</span><span class="sxs-lookup"><span data-stu-id="faaeb-107">COR_E_NOT_CLR will be returned if the specified module is not a CLR module.</span></span>  
  
 `pDataTarget`  
 <span data-ttu-id="faaeb-108">[in]マネージ デバッガーがプロセスの状態を検査できるデータ ターゲット抽象化します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-108">[in] A data target abstraction that allows the managed debugger to inspect process state.</span></span> <span data-ttu-id="faaeb-109">デバッガーを実装する必要があります、 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="faaeb-109">The debugger must implement the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="faaeb-110">実装する必要があります、 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)デバッグ中に CLR がインストールされていないローカル コンピューターのシナリオをサポートするインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="faaeb-110">You should implement the [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface to support scenarios where the CLR that is being debugged is not installed locally on the computer.</span></span>  
  
 `pLibraryProvider`  
 <span data-ttu-id="faaeb-111">[in]バージョン固有のデバッグ ライブラリを検索しに読み込む要求を許可するライブラリのプロバイダーのコールバック インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="faaeb-111">[in] A library provider callback interface that allows version-specific debugging libraries to be located and loaded on demand.</span></span> <span data-ttu-id="faaeb-112">このパラメーターは必要な場合にのみ`ppProcess`または`pFlags`ない`null`します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-112">This parameter is required only if `ppProcess` or `pFlags` is not `null`.</span></span>  
  
 `pMaxDebuggerSupportedVersion`  
 <span data-ttu-id="faaeb-113">[in]このデバッガーでデバッグできる CLR の最新バージョン。</span><span class="sxs-lookup"><span data-stu-id="faaeb-113">[in] The highest version of the CLR that this debugger can debug.</span></span> <span data-ttu-id="faaeb-114">メジャー、マイナーを指定し、このデバッガーをサポートする最新の CLR バージョンからバージョンをビルドおよびリビジョン番号を将来のインプレース CLR サービス リリースの対応するために 65535 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faaeb-114">You should specify the major, minor, and build versions from the latest CLR version this debugger supports, and set the revision number to 65535 to accommodate future in-place CLR servicing releases.</span></span>  
  
 `riidProcess`  
 <span data-ttu-id="faaeb-115">[in]取得する ICorDebugProcess インターフェイスの ID。</span><span class="sxs-lookup"><span data-stu-id="faaeb-115">[in] The ID of the ICorDebugProcess interface to retrieve.</span></span> <span data-ttu-id="faaeb-116">現時点では、可能な値は IID_CORDEBUGPROCESS3、IID_CORDEBUGPROCESS2、および IID_CORDEBUGPROCESS です。</span><span class="sxs-lookup"><span data-stu-id="faaeb-116">Currently, the only accepted values are IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2, and IID_CORDEBUGPROCESS.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="faaeb-117">[out]識別される COM インターフェイスへのポインター`riidProcess`します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-117">[out] A pointer to the COM interface that is identified by `riidProcess`.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="faaeb-118">[入力、出力]CLR のバージョン。</span><span class="sxs-lookup"><span data-stu-id="faaeb-118">[in, out] The version of the CLR.</span></span> <span data-ttu-id="faaeb-119">この値は、入力の`null`します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-119">On input, this value can be `null`.</span></span> <span data-ttu-id="faaeb-120">指していることも、 [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)構造の場合、構造体の`wStructVersion`フィールドは、0 (ゼロ) に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="faaeb-120">It can also point to a [CLR_DEBUGGING_VERSION](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) structure, in which case the structure's `wStructVersion` field must be initialized to 0 (zero).</span></span>  
  
 <span data-ttu-id="faaeb-121">出力で返された`CLR_DEBUGGING_VERSION`CLR のバージョン情報が格納される構造体。</span><span class="sxs-lookup"><span data-stu-id="faaeb-121">On output, the returned `CLR_DEBUGGING_VERSION` structure will be filled in with the version information for the CLR.</span></span>  
  
 `pdwFlags`  
 <span data-ttu-id="faaeb-122">[out]指定したランタイムの概要情報フラグです。</span><span class="sxs-lookup"><span data-stu-id="faaeb-122">[out] Informational flags about the specified runtime.</span></span> <span data-ttu-id="faaeb-123">参照してください、 [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md)フラグの説明のトピックです。</span><span class="sxs-lookup"><span data-stu-id="faaeb-123">See the [CLR_DEBUGGING_PROCESS_FLAGS](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-process-flags-enumeration.md) topic for a description of the flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faaeb-124">戻り値</span><span class="sxs-lookup"><span data-stu-id="faaeb-124">Return Value</span></span>  
 <span data-ttu-id="faaeb-125">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-125">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="faaeb-126">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faaeb-126">HRESULT</span></span>|<span data-ttu-id="faaeb-127">説明</span><span class="sxs-lookup"><span data-stu-id="faaeb-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faaeb-128">S_OK</span><span class="sxs-lookup"><span data-stu-id="faaeb-128">S_OK</span></span>|<span data-ttu-id="faaeb-129">メソッドは正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="faaeb-129">The method completed successfully.</span></span>|  
|<span data-ttu-id="faaeb-130">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="faaeb-130">E_POINTER</span></span>|<span data-ttu-id="faaeb-131">`pDataTarget` は `null` です。</span><span class="sxs-lookup"><span data-stu-id="faaeb-131">`pDataTarget` is `null`.</span></span>|  
|<span data-ttu-id="faaeb-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span><span class="sxs-lookup"><span data-stu-id="faaeb-132">CORDBG_E_LIBRARY_PROVIDER_ERROR</span></span>|<span data-ttu-id="faaeb-133">[ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)コールバックがエラーを返しますまたは、有効なハンドルは実現されません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-133">The [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) callback returns an error or does not provide a valid handle.</span></span>|  
|<span data-ttu-id="faaeb-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="faaeb-134">CORDBG_E_MISSING_DATA_TARGET_INTERFACE</span></span>|<span data-ttu-id="faaeb-135">`pDataTarget` このバージョンのランタイムの必要なデータ ターゲットのインターフェイスを実装しません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-135">`pDataTarget` does not implement the required data target interfaces for this version of the runtime.</span></span>|  
|<span data-ttu-id="faaeb-136">CORDBG_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="faaeb-136">CORDBG_E_NOT_CLR</span></span>|<span data-ttu-id="faaeb-137">指定されたモジュールが CLR モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-137">The indicated module is not a CLR module.</span></span> <span data-ttu-id="faaeb-138">メモリが破損している、モジュールが使用できないか、CLR のバージョンが shim バージョンより新しいために、CLR モジュールを検出できない場合にも、この HRESULT が返されます。</span><span class="sxs-lookup"><span data-stu-id="faaeb-138">This HRESULT is also returned when a CLR module cannot be detected because memory has been corrupted, the module is not available, or the CLR version is later than the shim version.</span></span>|  
|<span data-ttu-id="faaeb-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span><span class="sxs-lookup"><span data-stu-id="faaeb-139">CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL</span></span>|<span data-ttu-id="faaeb-140">このランタイム バージョンは、このデバッグ モデルをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-140">This runtime version does not support this debugging model.</span></span> <span data-ttu-id="faaeb-141">現時点では、デバッグのモデルは、.NET Framework 4 より前に、の CLR のバージョンではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-141">Currently, the debugging model is not supported by CLR versions before the .NET Framework 4.</span></span> <span data-ttu-id="faaeb-142">`pwszVersion`出力パラメーターが設定されて、適切な値にこのエラーが発生後します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-142">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="faaeb-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span><span class="sxs-lookup"><span data-stu-id="faaeb-143">CORDBG_E_UNSUPPORTED_FORWARD_COMPAT</span></span>|<span data-ttu-id="faaeb-144">CLR のバージョンでは、このデバッガーでサポートされるバージョンを超えています。</span><span class="sxs-lookup"><span data-stu-id="faaeb-144">The version of the CLR is greater than the version this debugger claims to support.</span></span> <span data-ttu-id="faaeb-145">`pwszVersion`出力パラメーターが設定されて、適切な値にこのエラーが発生後します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-145">The `pwszVersion` output parameter is still set to the correct value after this error.</span></span>|  
|<span data-ttu-id="faaeb-146">E_NO_INTERFACE</span><span class="sxs-lookup"><span data-stu-id="faaeb-146">E_NO_INTERFACE</span></span>|<span data-ttu-id="faaeb-147">`riidProcess`インターフェイスは利用できません。</span><span class="sxs-lookup"><span data-stu-id="faaeb-147">The `riidProcess` interface is not available.</span></span>|  
|<span data-ttu-id="faaeb-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span><span class="sxs-lookup"><span data-stu-id="faaeb-148">CORDBG_E_UNSUPPORTED_VERSION_STRUCT</span></span>|<span data-ttu-id="faaeb-149">`CLR_DEBUGGING_VERSION`構造体には、認識されている値はありません。`wStructVersion`します。</span><span class="sxs-lookup"><span data-stu-id="faaeb-149">The `CLR_DEBUGGING_VERSION` structure does not have a recognized value for `wStructVersion`.</span></span> <span data-ttu-id="faaeb-150">この時点でのみ使用できる値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="faaeb-150">The only accepted value at this time is 0.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="faaeb-151">例外</span><span class="sxs-lookup"><span data-stu-id="faaeb-151">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faaeb-152">Remarks</span><span class="sxs-lookup"><span data-stu-id="faaeb-152">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faaeb-153">必要条件</span><span class="sxs-lookup"><span data-stu-id="faaeb-153">Requirements</span></span>  
 <span data-ttu-id="faaeb-154">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="faaeb-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faaeb-155">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faaeb-155">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faaeb-156">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faaeb-156">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faaeb-157">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faaeb-157">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faaeb-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="faaeb-158">See also</span></span>

- [<span data-ttu-id="faaeb-159">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="faaeb-159">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="faaeb-160">デバッグ</span><span class="sxs-lookup"><span data-stu-id="faaeb-160">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
