---
title: ICorDebugRegisterSet::GetRegisters メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetRegisters method [.NET Framework debugging]
ms.assetid: fdf91864-48ea-4aa6-b70c-361b7a3184c7
topic_type:
- apiref
ms.openlocfilehash: 737993ac80b26d490915af3e97fd6a9552246aee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792119"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="62c46-102">ICorDebugRegisterSet::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="62c46-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="62c46-103">ビットマスクによって指定された、(現在コードを実行しているコンピューター上の) 各レジスタの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="62c46-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62c46-104">構文</span><span class="sxs-lookup"><span data-stu-id="62c46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62c46-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62c46-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="62c46-106">から取得するレジスタ値を指定するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="62c46-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="62c46-107">各ビットは、レジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="62c46-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="62c46-108">ビットが1に設定されている場合は、レジスタの値が取得されます。それ以外の場合は、レジスタの値は取得されません。</span><span class="sxs-lookup"><span data-stu-id="62c46-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="62c46-109">から取得するレジスタ値の数。</span><span class="sxs-lookup"><span data-stu-id="62c46-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="62c46-110">入出力`CORDB_REGISTER` オブジェクトの配列。各オブジェクトはレジスタの値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="62c46-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c46-111">コメント</span><span class="sxs-lookup"><span data-stu-id="62c46-111">Remarks</span></span>  
 <span data-ttu-id="62c46-112">配列のサイズは、ビットマスクで1に設定されているビット数と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="62c46-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="62c46-113">`regCount` パラメーターは、レジスタ値を受け取るバッファー内の要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="62c46-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="62c46-114">`regCount` 値がマスクで示されているレジスタの数に対して小さすぎる場合、番号の大きいレジスタはセットから切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="62c46-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="62c46-115">`regCount` 値が大きすぎる場合、未使用の `regBuffer` 要素は変更されません。</span><span class="sxs-lookup"><span data-stu-id="62c46-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="62c46-116">使用できないレジスタがビットマスクによって指定されている場合、`GetRegisters` はそのレジスタの不定値を返します。</span><span class="sxs-lookup"><span data-stu-id="62c46-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62c46-117">要件</span><span class="sxs-lookup"><span data-stu-id="62c46-117">Requirements</span></span>  
 <span data-ttu-id="62c46-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62c46-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62c46-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62c46-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62c46-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62c46-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62c46-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62c46-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c46-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="62c46-122">See also</span></span>

- [<span data-ttu-id="62c46-123">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62c46-123">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="62c46-124">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62c46-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
