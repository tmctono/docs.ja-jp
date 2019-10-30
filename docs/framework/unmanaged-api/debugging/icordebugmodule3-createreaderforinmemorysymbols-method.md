---
title: ICorDebugModule3::CreateReaderForInMemorySymbols メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137311"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="c0ea7-102">ICorDebugModule3::CreateReaderForInMemorySymbols メソッド</span><span class="sxs-lookup"><span data-stu-id="c0ea7-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="c0ea7-103">動的モジュールのデバッグシンボルリーダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ea7-104">構文</span><span class="sxs-lookup"><span data-stu-id="c0ea7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0ea7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0ea7-105">Parameters</span></span>  
 <span data-ttu-id="c0ea7-106">riid</span><span class="sxs-lookup"><span data-stu-id="c0ea7-106">riid</span></span>  
 <span data-ttu-id="c0ea7-107">から返す COM インターフェイスの IID。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="c0ea7-108">通常、これは[ISymUnmanagedReader インターフェイス](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="c0ea7-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="c0ea7-109">ppObj</span></span>  
 <span data-ttu-id="c0ea7-110">入出力返されたインターフェイスへのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0ea7-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0ea7-111">Return Value</span></span>  
 <span data-ttu-id="c0ea7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c0ea7-112">S_OK</span></span>  
 <span data-ttu-id="c0ea7-113">リーダーが正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="c0ea7-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="c0ea7-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="c0ea7-115">モジュールがメモリ内または動的モジュールではありません。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="c0ea7-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c0ea7-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="c0ea7-117">シンボルは、アプリケーションによって提供されていないか、まだ使用できません。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="c0ea7-118">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="c0ea7-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c0ea7-119">リーダーを作成できません。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0ea7-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="c0ea7-120">Remarks</span></span>  
 <span data-ttu-id="c0ea7-121">このメソッドを使用して、インメモリ (非動的) モジュール用のシンボルリーダーオブジェクトを作成することもできますが、最初にシンボルを使用できるようになった後 ( [UpdateModuleSymbols メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)コールバックによって示されます) にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="c0ea7-122">このメソッドは、呼び出されるたびに新しいリーダーインスタンスを返します ( [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)など)。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="c0ea7-123">したがって、デバッガーは、基になるデータが変更されている (つまり、 [Loadclass メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)のコールバックが受信された) 場合にのみ、結果をキャッシュし、新しいインスタンスを要求します。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="c0ea7-124">動的モジュールでは、最初の型が読み込まれるまで ( [Loadclass メソッド](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)コールバックによって示されるように) シンボルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0ea7-125">［要件］</span><span class="sxs-lookup"><span data-stu-id="c0ea7-125">Requirements</span></span>  
 <span data-ttu-id="c0ea7-126">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0ea7-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ea7-127">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0ea7-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0ea7-128">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0ea7-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0ea7-129">**.NET Framework のバージョン:** 4.5、4、3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c0ea7-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ea7-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0ea7-130">See also</span></span>

- [<span data-ttu-id="c0ea7-131">ICorDebugRemoteTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0ea7-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="c0ea7-132">ICorDebug インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0ea7-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="c0ea7-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0ea7-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
