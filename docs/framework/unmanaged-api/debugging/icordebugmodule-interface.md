---
title: ICorDebugModule インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
ms.openlocfilehash: 971d6a6a2157c48dcb9105e9f523b1f077098479
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129480"
---
# <a name="icordebugmodule-interface"></a><span data-ttu-id="435fa-102">ICorDebugModule インターフェイス</span><span class="sxs-lookup"><span data-stu-id="435fa-102">ICorDebugModule Interface</span></span>

<span data-ttu-id="435fa-103">実行可能ファイルまたはダイナミックリンクライブラリ (DLL) のいずれかである共通言語ランタイム (CLR) モジュールを表します。</span><span class="sxs-lookup"><span data-stu-id="435fa-103">Represents a common language runtime (CLR) module, which is either an executable file or a dynamic-link library (DLL).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="435fa-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-104">Methods</span></span>  
  
|<span data-ttu-id="435fa-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-105">Method</span></span>|<span data-ttu-id="435fa-106">説明</span><span class="sxs-lookup"><span data-stu-id="435fa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="435fa-107">CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-107">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|<span data-ttu-id="435fa-108">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="435fa-108">Not implemented.</span></span>|  
|[<span data-ttu-id="435fa-109">EnableClassLoadCallbacks メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-109">EnableClassLoadCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|<span data-ttu-id="435fa-110">このモジュールに対して、" [UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) " コール[バック:: loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)との各コールバックを呼び出すかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="435fa-110">Determines whether the [ICorDebugManagedCallback::LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) callbacks are called for this module.</span></span>|  
|[<span data-ttu-id="435fa-111">EnableJITDebugging メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-111">EnableJITDebugging Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|<span data-ttu-id="435fa-112">Just-in-time (JIT) コンパイラが、このモジュール内のメソッドのデバッグ情報を保持するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="435fa-112">Determines whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>|  
|[<span data-ttu-id="435fa-113">GetAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-113">GetAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|<span data-ttu-id="435fa-114">このモジュールの格納アセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-114">Gets the containing assembly for this module.</span></span>|  
|[<span data-ttu-id="435fa-115">GetBaseAddress メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-115">GetBaseAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|<span data-ttu-id="435fa-116">モジュールのベースアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-116">Gets the base address of the module.</span></span>|  
|[<span data-ttu-id="435fa-117">GetClassFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-117">GetClassFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|<span data-ttu-id="435fa-118">メタデータから、このクラスを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-118">Gets the ICorDebugClass from the metadata.</span></span>|  
|[<span data-ttu-id="435fa-119">GetEditAndContinueSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-119">GetEditAndContinueSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|<span data-ttu-id="435fa-120">非推奨。</span><span class="sxs-lookup"><span data-stu-id="435fa-120">Deprecated.</span></span>|  
|[<span data-ttu-id="435fa-121">GetFunctionFromRVA メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-121">GetFunctionFromRVA Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|<span data-ttu-id="435fa-122">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="435fa-122">Not implemented.</span></span>|  
|[<span data-ttu-id="435fa-123">GetFunctionFromToken メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-123">GetFunctionFromToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|<span data-ttu-id="435fa-124">メタデータトークンによって指定された関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-124">Gets the function that is specified by the metadata token.</span></span>|  
|[<span data-ttu-id="435fa-125">GetGlobalVariableValue メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-125">GetGlobalVariableValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|<span data-ttu-id="435fa-126">指定したグローバル変数の値オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-126">Gets a value object for the specified global variable.</span></span>|  
|[<span data-ttu-id="435fa-127">GetMetaDataInterface メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-127">GetMetaDataInterface Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|<span data-ttu-id="435fa-128">モジュールのメタデータを調べるために使用できるメタデータインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-128">Gets a metadata interface pointer that can be used to examine the metadata for the module.</span></span>|  
|[<span data-ttu-id="435fa-129">GetName メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-129">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|<span data-ttu-id="435fa-130">モジュールのファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-130">Gets the file name of the module.</span></span>|  
|[<span data-ttu-id="435fa-131">GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-131">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|<span data-ttu-id="435fa-132">このモジュールの格納プロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-132">Gets the containing process for this module.</span></span>|  
|[<span data-ttu-id="435fa-133">GetSize メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-133">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|<span data-ttu-id="435fa-134">モジュールのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-134">Gets the size of the module in bytes.</span></span>|  
|[<span data-ttu-id="435fa-135">GetToken メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-135">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|<span data-ttu-id="435fa-136">このモジュールのテーブルエントリのトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="435fa-136">Gets the token for the table entry for this module.</span></span>|  
|[<span data-ttu-id="435fa-137">IsDynamic メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-137">IsDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|<span data-ttu-id="435fa-138">モジュールが動的かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="435fa-138">Indicates whether the module is dynamic.</span></span>|  
|[<span data-ttu-id="435fa-139">IsInMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="435fa-139">IsInMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|<span data-ttu-id="435fa-140">このモジュールがメモリ内にのみ存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="435fa-140">Indicates whether this module exists only in memory.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="435fa-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="435fa-141">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="435fa-142">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="435fa-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435fa-143">［要件］</span><span class="sxs-lookup"><span data-stu-id="435fa-143">Requirements</span></span>  
 <span data-ttu-id="435fa-144">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="435fa-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435fa-145">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="435fa-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="435fa-146">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="435fa-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="435fa-147">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435fa-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435fa-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="435fa-148">See also</span></span>

- [<span data-ttu-id="435fa-149">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="435fa-149">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="435fa-150">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="435fa-150">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
