---
title: ICorDebugRegisterSet2::GetRegisters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1b90390689e709ee131935bd6417fa6b273eb2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769984"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="cf5c7-102">ICorDebugRegisterSet2::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="cf5c7-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="cf5c7-103">各レジスタの値を取得します (コードが現在実行されているプラットフォーム) の特定のビット マスクによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf5c7-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf5c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf5c7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf5c7-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="cf5c7-106">[in]サイズ (バイト単位) の`mask`配列。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="cf5c7-107">[in]バイトの配列を各ビットは、レジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="cf5c7-108">ビットが 1 の場合は、対応するレジスタの値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="cf5c7-109">[in]取得するレジスタの値の数。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="cf5c7-110">[out]配列の`CORDB_REGISTER`オブジェクト、レジスタの値を受信します。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf5c7-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf5c7-111">Remarks</span></span>  
 <span data-ttu-id="cf5c7-112">`GetRegisters`マスクによって指定されているレジスタの値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="cf5c7-113">配列にマスク ビットが設定されていないレジスタの値が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="cf5c7-114">したがってのサイズ、`regBuffer`配列は、マスク内の 1 の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="cf5c7-115">場合の値`regCount`のセットからマスク、大きい番号のレジスタの値で指定したレジスタの数は切り捨てられますが、小さすぎます。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="cf5c7-116">場合`regCount`が大きすぎる、未使用`regBuffer`要素は変更できません。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="cf5c7-117">使用できないレジスタがマスクによって示される場合、は、そのレジスタの中間の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="cf5c7-118">`ICorDebugRegisterSet2::GetRegisters`メソッドがプラットフォーム 64 を超えるレジスタがあるに必要です。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="cf5c7-119">たとえば、IA64 が 128 の汎用レジスタと 128 の浮動小数点レジスタ、64 ビット マスクのビットを超える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="cf5c7-120">同様に、x86 などのプラットフォームでは、64 を超えるレジスタを持たない場合、`GetRegisters`メソッドは実際には、バイト、変換、`mask`のバイト配列、`ULONG64`号餧ェヒェマル、 [ICorDebugRegisterSet:。GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md)メソッド、`ULONG64`マスク。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf5c7-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="cf5c7-121">Requirements</span></span>  
 <span data-ttu-id="cf5c7-122">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf5c7-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf5c7-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf5c7-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf5c7-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf5c7-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf5c7-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf5c7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf5c7-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf5c7-126">See also</span></span>

- [<span data-ttu-id="cf5c7-127">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf5c7-127">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="cf5c7-128">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf5c7-128">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
