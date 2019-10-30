---
title: ICorDebugDataTarget2::CreateVirtualUnwinder メソッド
ms.date: 03/30/2017
ms.assetid: 354c8b4c-7d23-45c6-a7d7-3be4c2a5b772
ms.openlocfilehash: f9a9038bd0d268e09d8518fa50534a9959b456de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122183"
---
# <a name="icordebugdatatarget2createvirtualunwinder-method"></a><span data-ttu-id="a457e-102">ICorDebugDataTarget2::CreateVirtualUnwinder メソッド</span><span class="sxs-lookup"><span data-stu-id="a457e-102">ICorDebugDataTarget2::CreateVirtualUnwinder Method</span></span>
<span data-ttu-id="a457e-103">初期コンテキストからアンワインドを開始する新しいスタック アンワインダーを作成します (これは、必ずしもスレッドのリーフではありません)。</span><span class="sxs-lookup"><span data-stu-id="a457e-103">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a457e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a457e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateVirtualUnwinder(  
    [in] DWORD nativeThreadID,  
    [in] ULONG32 contextFlags,  
    [in] ULONG32 cbContext,  
    [in, size_is(cbContext)] BYTE initialContext[],  
    [out] ICorDebugVirtualUnwinder ** ppUnwinder);  
};  
```  
  
## <a name="parameters"></a><span data-ttu-id="a457e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a457e-105">Parameters</span></span>  
 <span data-ttu-id="a457e-106">nativeThreadID</span><span class="sxs-lookup"><span data-stu-id="a457e-106">nativeThreadID</span></span>  
 <span data-ttu-id="a457e-107">[入力] スタックをアンワインドするスレッドのネイティブ スレッド ID。</span><span class="sxs-lookup"><span data-stu-id="a457e-107">[in] The native thread ID of the thread whose stack is to be unwound.</span></span>  
  
 <span data-ttu-id="a457e-108">contextFlags</span><span class="sxs-lookup"><span data-stu-id="a457e-108">contextFlags</span></span>  
 <span data-ttu-id="a457e-109">[入力] コンテキストのどの部分が `initialContext` で定義されるかを指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="a457e-109">[in] Flags that specify which parts of the context are defined in `initialContext`.</span></span>  
  
 <span data-ttu-id="a457e-110">cbContext</span><span class="sxs-lookup"><span data-stu-id="a457e-110">cbContext</span></span>  
 <span data-ttu-id="a457e-111">[入力] `initialContext` のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a457e-111">[in] The size of `initialContext`.</span></span>  
  
 <span data-ttu-id="a457e-112">initialContext</span><span class="sxs-lookup"><span data-stu-id="a457e-112">initialContext</span></span>  
 <span data-ttu-id="a457e-113">[入力] コンテキストのデータ。</span><span class="sxs-lookup"><span data-stu-id="a457e-113">[in] The data in the context.</span></span>  
  
 <span data-ttu-id="a457e-114">ppUnwinder</span><span class="sxs-lookup"><span data-stu-id="a457e-114">ppUnwinder</span></span>  
 <span data-ttu-id="a457e-115">[出力] ICorDebugVirtualUnwinder インターフェイス オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a457e-115">[out] A pointer to the address of an ICorDebugVirtualUnwinder interface object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a457e-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="a457e-116">Return Value</span></span>  
 <span data-ttu-id="a457e-117">正常終了した場合は、`S_OK`。</span><span class="sxs-lookup"><span data-stu-id="a457e-117">`S_OK` if successful.</span></span> <span data-ttu-id="a457e-118">それ以外の `HRESULT` は失敗を示します。</span><span class="sxs-lookup"><span data-stu-id="a457e-118">Any other `HRESULT` indicates failure.</span></span> <span data-ttu-id="a457e-119">Mscordbi.dll によって受信された失敗した `HRESULT` は致命的と見なされ、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)メソッドによって `CORDBG_E_DATA_TARGET_ERROR`が返されます。</span><span class="sxs-lookup"><span data-stu-id="a457e-119">Any failing `HRESULT` received by mscordbi is considered fatal and causes [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a457e-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="a457e-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a457e-121">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a457e-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a457e-122">［要件］</span><span class="sxs-lookup"><span data-stu-id="a457e-122">Requirements</span></span>  
 <span data-ttu-id="a457e-123">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a457e-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a457e-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a457e-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a457e-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a457e-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a457e-126">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a457e-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a457e-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a457e-127">See also</span></span>

- [<span data-ttu-id="a457e-128">ICorDebugDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a457e-128">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a457e-129">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a457e-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
