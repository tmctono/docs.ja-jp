---
title: ICorDebugMutableDataTarget::WriteVirtual メソッド
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fba970de6e5882d3cbe9be17b5b49be5a3e81aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171653"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="fcdd3-102">ICorDebugMutableDataTarget::WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="fcdd3-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="fcdd3-103">ターゲット プロセスのアドレス空間にメモリを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcdd3-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcdd3-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcdd3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcdd3-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="fcdd3-106">[in] `pBuffer` の内容の書き込み先のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="fcdd3-107">[in] 書き込むバイト数が格納されているバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="fcdd3-108">[in] `pBuffer` のバイト数。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcdd3-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="fcdd3-109">Return Value</span></span>  
 <span data-ttu-id="fcdd3-110">正常に完了した場合は `S_OK`、失敗した場合はその他の `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcdd3-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="fcdd3-111">Remarks</span></span>  
 <span data-ttu-id="fcdd3-112">バイトを書き込むことができない場合、メソッド呼び出しは失敗し、ターゲット アドレス空間のバイトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="fcdd3-113">(それ以外の場合、ターゲットは不整合な状態になり、デバッグの信頼性がさらに低下します。)</span><span class="sxs-lookup"><span data-stu-id="fcdd3-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcdd3-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcdd3-114">Requirements</span></span>  
 <span data-ttu-id="fcdd3-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcdd3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcdd3-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcdd3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcdd3-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcdd3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fcdd3-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcdd3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcdd3-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcdd3-119">See also</span></span>

- [<span data-ttu-id="fcdd3-120">ICorDebugMutableDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcdd3-120">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="fcdd3-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fcdd3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
