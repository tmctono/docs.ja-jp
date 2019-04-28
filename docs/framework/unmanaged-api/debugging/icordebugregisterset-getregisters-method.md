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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b417685361126951470571e2440cc842ab1c94fb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782916"
---
# <a name="icordebugregistersetgetregisters-method"></a><span data-ttu-id="81d1c-102">ICorDebugRegisterSet::GetRegisters メソッド</span><span class="sxs-lookup"><span data-stu-id="81d1c-102">ICorDebugRegisterSet::GetRegisters Method</span></span>
<span data-ttu-id="81d1c-103">各レジスタの値を取得します (現在のコードを実行しているコンピューター) でビット マスクによって指定されています。</span><span class="sxs-lookup"><span data-stu-id="81d1c-103">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81d1c-104">構文</span><span class="sxs-lookup"><span data-stu-id="81d1c-104">Syntax</span></span>  
  
```  
HRESULT GetRegisters (  
    [in] ULONG64       mask,   
    [in] ULONG32       regCount,  
    [out, size_is(regCount), length_is(regCount)]  
        CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81d1c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="81d1c-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="81d1c-106">[in]値が取得するにはどのレジスタを指定するビット マスク。</span><span class="sxs-lookup"><span data-stu-id="81d1c-106">[in] A bit mask that specifies which register values are to be retrieved.</span></span> <span data-ttu-id="81d1c-107">各ビットは、レジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="81d1c-107">Each bit corresponds to a register.</span></span> <span data-ttu-id="81d1c-108">ビットは 1 つに設定されている場合は、レジスタの値が取得されます。それ以外の場合、レジスタの値は取得されません。</span><span class="sxs-lookup"><span data-stu-id="81d1c-108">If a bit is set to one, the register's value is retrieved; otherwise, the register's value is not retrieved.</span></span>  
  
 `regCount`  
 <span data-ttu-id="81d1c-109">[in]取得するレジスタの値の数。</span><span class="sxs-lookup"><span data-stu-id="81d1c-109">[in] The number of register values to be retrieved.</span></span>  
  
 `regBuffer`  
 <span data-ttu-id="81d1c-110">[out]配列の`CORDB_REGISTER`オブジェクト、レジスタの値を受信します。</span><span class="sxs-lookup"><span data-stu-id="81d1c-110">[out] An array of `CORDB_REGISTER` objects, each of which receives a value of a register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81d1c-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="81d1c-111">Remarks</span></span>  
 <span data-ttu-id="81d1c-112">配列のサイズは、ビット マスクのいずれかに設定するビット数に等しい必要があります。</span><span class="sxs-lookup"><span data-stu-id="81d1c-112">The size of the array should be equal to the number of bits set to one in the bit mask.</span></span> <span data-ttu-id="81d1c-113">`regCount`パラメーターがレジスタの値を受け取るバッファー内の要素の数を指定します。</span><span class="sxs-lookup"><span data-stu-id="81d1c-113">The `regCount` parameter specifies the number of elements in the buffer that will receive the register values.</span></span> <span data-ttu-id="81d1c-114">場合、`regCount`マスクで指定したレジスタの数の値が小さすぎる、セットから大きい番号のレジスタは切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="81d1c-114">If the `regCount` value is too small for the number of registers indicated by the mask, the higher numbered registers will be truncated from the set.</span></span> <span data-ttu-id="81d1c-115">場合、`regCount`値が大きすぎて、未使用`regBuffer`要素は変更できません。</span><span class="sxs-lookup"><span data-stu-id="81d1c-115">If the `regCount` value is too large, the unused `regBuffer` elements will be unmodified.</span></span>  
  
 <span data-ttu-id="81d1c-116">ビット マスクが使用できないレジスタを指定する場合`GetRegisters`そのレジスタの中間の値を返します。</span><span class="sxs-lookup"><span data-stu-id="81d1c-116">If the bit mask specifies a register that is unavailable, `GetRegisters` returns an indeterminate value for that register.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81d1c-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="81d1c-117">Requirements</span></span>  
 <span data-ttu-id="81d1c-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81d1c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81d1c-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81d1c-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81d1c-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81d1c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81d1c-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81d1c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d1c-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="81d1c-122">See also</span></span>

- [<span data-ttu-id="81d1c-123">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81d1c-123">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="81d1c-124">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="81d1c-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
