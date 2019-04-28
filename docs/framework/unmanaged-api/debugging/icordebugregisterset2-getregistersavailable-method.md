---
title: ICorDebugRegisterSet2::GetRegistersAvailable メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1522d643a69c47eec03770a8f51756dd4250075a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782825"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="dc4c0-102">ICorDebugRegisterSet2::GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="dc4c0-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="dc4c0-103">使用可能なレジスタのビットマップを提供するバイト配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc4c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="dc4c0-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc4c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc4c0-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="dc4c0-106">[in] `availableRegChunks` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="dc4c0-107">[out]バイトの配列を各ビットは、レジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="dc4c0-108">レジスタが利用可能な場合は、レジスタの対応するビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc4c0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="dc4c0-109">Remarks</span></span>  
 <span data-ttu-id="dc4c0-110">CorDebugRegister 列挙型の値では、マイクロプロセッサの別のレジスタを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="dc4c0-111">各値の上位 5 つのビットは、インデックス、`availableRegChunks`バイトの配列。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="dc4c0-112">各値の下位の 3 つのビットは、インデックス付きのバイト内のビット位置を特定します。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="dc4c0-113">指定された、`CorDebugRegister`特定の登録、マスク内の登録の位置を指定する値は次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="dc4c0-114">抽出の正確なバイトへのアクセスに必要なインデックス、`availableRegChunks`配列。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="dc4c0-115">`CorDebugRegister` 値 >> 3</span><span class="sxs-lookup"><span data-stu-id="dc4c0-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="dc4c0-116">ビット 0 が最下位ビットをインデックス付きのバイト内のビット位置を抽出します。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="dc4c0-117">`CorDebugRegister` (& 7) 値</span><span class="sxs-lookup"><span data-stu-id="dc4c0-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc4c0-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="dc4c0-118">Requirements</span></span>  
 <span data-ttu-id="dc4c0-119">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc4c0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc4c0-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc4c0-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc4c0-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc4c0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc4c0-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc4c0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc4c0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc4c0-123">See also</span></span>

- [<span data-ttu-id="dc4c0-124">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc4c0-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="dc4c0-125">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="dc4c0-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
