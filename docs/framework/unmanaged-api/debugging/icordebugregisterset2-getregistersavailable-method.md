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
ms.openlocfilehash: 2149c985519b95f89af2c50d05753ae7259babe4
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378218"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="31ec0-102">ICorDebugRegisterSet2::GetRegistersAvailable メソッド</span><span class="sxs-lookup"><span data-stu-id="31ec0-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="31ec0-103">使用できるレジスタのビットマップを提供するバイト配列を取得します。</span><span class="sxs-lookup"><span data-stu-id="31ec0-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ec0-104">構文</span><span class="sxs-lookup"><span data-stu-id="31ec0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ec0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="31ec0-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="31ec0-106">[in] `availableRegChunks` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="31ec0-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="31ec0-107">入出力バイト配列。各ビットはレジスタに対応します。</span><span class="sxs-lookup"><span data-stu-id="31ec0-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="31ec0-108">レジスタが使用可能な場合は、レジスタの対応するビットが設定されます。</span><span class="sxs-lookup"><span data-stu-id="31ec0-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31ec0-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="31ec0-109">Remarks</span></span>  
 <span data-ttu-id="31ec0-110">CorDebugRegister 列挙子の値は、異なるマイクロプロセッサのレジスタを指定します。</span><span class="sxs-lookup"><span data-stu-id="31ec0-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="31ec0-111">各値の上位5ビットは、バイト配列へのインデックスです `availableRegChunks` 。</span><span class="sxs-lookup"><span data-stu-id="31ec0-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="31ec0-112">各値の下位3ビットは、インデックス付きバイト内のビット位置を識別します。</span><span class="sxs-lookup"><span data-stu-id="31ec0-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="31ec0-113">特定の `CorDebugRegister` レジスタを指定する値を指定すると、マスク内のレジスタの位置は次のように決定されます。</span><span class="sxs-lookup"><span data-stu-id="31ec0-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="31ec0-114">配列内の正しいバイトにアクセスするために必要なインデックスを抽出し `availableRegChunks` ます。</span><span class="sxs-lookup"><span data-stu-id="31ec0-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="31ec0-115">`CorDebugRegister`値 >> 3</span><span class="sxs-lookup"><span data-stu-id="31ec0-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="31ec0-116">インデックス付きバイト内のビット位置を抽出します。ビットゼロは最下位ビットです。</span><span class="sxs-lookup"><span data-stu-id="31ec0-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="31ec0-117">`CorDebugRegister`値 & 7</span><span class="sxs-lookup"><span data-stu-id="31ec0-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31ec0-118">必要条件</span><span class="sxs-lookup"><span data-stu-id="31ec0-118">Requirements</span></span>  
 <span data-ttu-id="31ec0-119">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31ec0-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31ec0-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31ec0-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31ec0-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31ec0-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31ec0-122">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31ec0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31ec0-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="31ec0-123">See also</span></span>

- [<span data-ttu-id="31ec0-124">ICorDebugRegisterSet2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31ec0-124">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="31ec0-125">ICorDebugRegisterSet インターフェイス</span><span class="sxs-lookup"><span data-stu-id="31ec0-125">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
