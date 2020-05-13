---
title: ICorDebugMutableDataTarget::WriteVirtual メソッド
ms.date: 03/30/2017
ms.assetid: 80833648-58a7-491a-8dc8-9a48e9bb3adc
ms.openlocfilehash: 6325dba99fba0ab5e2f752a0635fdd428d3065eb
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206738"
---
# <a name="icordebugmutabledatatargetwritevirtual-method"></a><span data-ttu-id="a1a42-102">ICorDebugMutableDataTarget::WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="a1a42-102">ICorDebugMutableDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="a1a42-103">ターゲット プロセスのアドレス空間にメモリを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="a1a42-103">Writes memory into the target process address space.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1a42-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1a42-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual(  
   [in] CORDB_ADDRESS address,  
   [in, size_is(bytesRequested)] const BYTE * pBuffer,  
   [in] ULONG32 bytesRequested);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1a42-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1a42-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="a1a42-106">[in] `pBuffer` の内容の書き込み先のアドレスです。</span><span class="sxs-lookup"><span data-stu-id="a1a42-106">[in] The address at which to write the contents of `pBuffer`.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="a1a42-107">[in] 書き込むバイト数が格納されているバイト配列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a1a42-107">[in] A pointer to a byte array that contains the bytes to be written.</span></span>  
  
 `address`  
 <span data-ttu-id="a1a42-108">[in] `pBuffer` のバイト数。</span><span class="sxs-lookup"><span data-stu-id="a1a42-108">[in] The number of bytes in `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1a42-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1a42-109">Return Value</span></span>  
 <span data-ttu-id="a1a42-110">正常に完了した場合は `S_OK`、失敗した場合はその他の `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="a1a42-110">`S_OK` on success, or any other `HRESULT` on failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1a42-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="a1a42-111">Remarks</span></span>  
 <span data-ttu-id="a1a42-112">バイトを書き込むことができない場合、メソッド呼び出しは失敗し、ターゲット アドレス空間のバイトは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a1a42-112">If any bytes cannot be written, the method call fails without changing any bytes in the target address space.</span></span> <span data-ttu-id="a1a42-113">(それ以外の場合、ターゲットは不整合な状態になり、デバッグの信頼性がさらに低下します。)</span><span class="sxs-lookup"><span data-stu-id="a1a42-113">(Otherwise, the target would be in an inconsistent state that makes further debugging unreliable.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1a42-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1a42-114">Requirements</span></span>  
 <span data-ttu-id="a1a42-115">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1a42-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1a42-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1a42-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1a42-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1a42-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1a42-118">**.NET Framework のバージョン:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1a42-118">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1a42-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1a42-119">See also</span></span>

- [<span data-ttu-id="a1a42-120">ICorDebugMutableDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1a42-120">ICorDebugMutableDataTarget Interface</span></span>](icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="a1a42-121">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="a1a42-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
