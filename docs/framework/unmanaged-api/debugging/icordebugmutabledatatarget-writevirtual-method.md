---
title: 'ICorDebugMutableDataTarget:: WriteVirtual メソッド'
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 5947caa8dfb97574bb4b3c5634d962df153211c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132680"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="5fa1d-102">ICorDebugMutableDataTarget:: WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="5fa1d-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="5fa1d-103">ターゲット プロセスのアドレス空間にメモリを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fa1d-104">構文</span><span class="sxs-lookup"><span data-stu-id="5fa1d-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fa1d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5fa1d-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5fa1d-106">[in] `pBuffer` の内容の書き込み先のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="5fa1d-107">[in] 書き込むバイト数が格納されているバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="5fa1d-108">[in] `pBuffer` のバイト数。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fa1d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="5fa1d-109">Return Value</span></span>  
 <span data-ttu-id="5fa1d-110">正常に完了した場合は `S_OK`、失敗した場合はその他の `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fa1d-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fa1d-111">Remarks</span></span>  
 <span data-ttu-id="5fa1d-112">バイトを書き込むことができない場合、メソッド呼び出しは失敗し、ターゲット アドレス空間のバイトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="5fa1d-113">(それ以外の場合、ターゲットは不整合な状態になり、デバッグの信頼性がさらに低下します。)</span><span class="sxs-lookup"><span data-stu-id="5fa1d-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fa1d-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="5fa1d-114">Requirements</span></span>  
 <span data-ttu-id="5fa1d-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fa1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fa1d-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fa1d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fa1d-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fa1d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fa1d-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fa1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa1d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fa1d-119">See also</span></span>

- [<span data-ttu-id="5fa1d-120">ICorDebugMutableDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fa1d-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="5fa1d-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5fa1d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
