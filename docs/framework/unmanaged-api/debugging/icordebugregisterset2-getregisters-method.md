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
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792059"
---
# <a name="icordebugregisterset2getregisters-method"></a><span data-ttu-id="b65b5-102">ICorDebugRegisterSet2::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="b65b5-102">ICorDebugRegisterSet2::GetRegisters Method</span></span>
<span data-ttu-id="b65b5-103">指定されたビットマスクによって指定された各レジスタの値を取得します (コードが現在実行されているプラットフォーム用)。</span><span class="sxs-lookup"><span data-stu-id="b65b5-103">Gets the value of each register (for the platform on which code is currently executing) that is specified by the given bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b65b5-104">構文</span><span class="sxs-lookup"><span data-stu-id="b65b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b65b5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b65b5-105">Parameters</span></span>  
 `maskCount`  
 <span data-ttu-id="b65b5-106">から`mask` 配列のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b65b5-106">[in] The size, in bytes, of the `mask` array.</span></span>  
  
 `mask`  
 <span data-ttu-id="b65b5-107">からバイト配列。各ビットはレジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="b65b5-107">[in] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="b65b5-108">ビットが1の場合は、対応するレジスタの値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="b65b5-108">If the bit is 1, the corresponding register's value will be retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="b65b5-109">から取得するレジスタ値の数。</span><span class="sxs-lookup"><span data-stu-id="b65b5-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="b65b5-110">入出力`CORDB_REGISTER` オブジェクトの配列。各オブジェクトは、レジスタの値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b65b5-110">[out] An array of `CORDB_REGISTER` objects, each of which receives the value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b65b5-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b65b5-111">Remarks</span></span>  
 <span data-ttu-id="b65b5-112">`GetRegisters` メソッドは、マスクによって指定されたレジスタから値の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="b65b5-112">The `GetRegisters` method returns an array of values from the registers that are specified by the mask.</span></span> <span data-ttu-id="b65b5-113">配列に、マスクビットが設定されていないレジスタの値が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b65b5-113">The array does not contain values of registers whose mask bit is not set.</span></span> <span data-ttu-id="b65b5-114">したがって、`regBuffer` 配列のサイズは、マスク内の1の数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="b65b5-114">Thus, the size of the `regBuffer` array must be equal to the number of 1's in the mask.</span></span> <span data-ttu-id="b65b5-115">`regCount` の値が、マスクによって示されるレジスタの数に対して小さすぎる場合、より上位の番号付きレジスタの値はセットから切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="b65b5-115">If the value of `regCount` is too small for the number of registers indicated by the mask, the values of the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="b65b5-116">`regCount` が大きすぎる場合、未使用の `regBuffer` 要素は変更されません。</span><span class="sxs-lookup"><span data-stu-id="b65b5-116">If `regCount` is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="b65b5-117">使用できないレジスタがマスクによって示されている場合、そのレジスタに対して不確定な値が返されます。</span><span class="sxs-lookup"><span data-stu-id="b65b5-117">If an unavailable register is indicated by the mask, an indeterminate value will be returned for that register.</span></span>  
  
 <span data-ttu-id="b65b5-118">`ICorDebugRegisterSet2::GetRegisters` メソッドは、64を超えるレジスタを持つプラットフォームに必要です。</span><span class="sxs-lookup"><span data-stu-id="b65b5-118">The `ICorDebugRegisterSet2::GetRegisters` method is necessary for platforms which have more than 64 registers.</span></span> <span data-ttu-id="b65b5-119">たとえば、IA64 には128汎用レジスタと128浮動小数点レジスタがあるため、ビットマスクには64ビット以上のビットが必要です。</span><span class="sxs-lookup"><span data-stu-id="b65b5-119">For example, IA64 has 128 general purpose registers and 128 floating-point registers, so you need more than 64-bits in the bit mask.</span></span>  
  
 <span data-ttu-id="b65b5-120">X86 などのプラットフォームの場合と同様に、64以上のレジスタがない場合、`GetRegisters` メソッドは実際には `mask` バイト配列のバイトを `ULONG64` に変換し、次に、`ULONG64` マスクを受け取る、"、 [" のよう](icordebugregisterset-getregisters-method.md)に入力します。</span><span class="sxs-lookup"><span data-stu-id="b65b5-120">If you do not have more than 64 registers, as is the case on platforms such as x86, the `GetRegisters` method actually just translates the bytes in the `mask` byte array into a `ULONG64` and then calls the [ICorDebugRegisterSet::GetRegisters](icordebugregisterset-getregisters-method.md) method, which takes the `ULONG64` mask.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b65b5-121">要件</span><span class="sxs-lookup"><span data-stu-id="b65b5-121">Requirements</span></span>  
 <span data-ttu-id="b65b5-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b65b5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b65b5-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b65b5-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b65b5-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b65b5-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b65b5-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b65b5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b65b5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="b65b5-126">See also</span></span>

- [<span data-ttu-id="b65b5-127">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b65b5-127">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="b65b5-128">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b65b5-128">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
