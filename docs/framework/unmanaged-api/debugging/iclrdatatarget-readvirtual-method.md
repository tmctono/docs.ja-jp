---
title: ICLRDataTarget::ReadVirtual メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38e2ec063d46ce9c890927391107888032e31378
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698097"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="9b29b-102">ICLRDataTarget::ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="9b29b-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="9b29b-103">指定されたバッファーに指定された仮想メモリ アドレスからのデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9b29b-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b29b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b29b-104">Syntax</span></span>  
  
```  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b29b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b29b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9b29b-106">[in]仮想メモリ アドレスを格納する CLRDATA_ADDRESS します。</span><span class="sxs-lookup"><span data-stu-id="9b29b-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9b29b-107">[out]データを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b29b-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="9b29b-108">[in]バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="9b29b-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="9b29b-109">[out]返されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9b29b-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b29b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b29b-110">Requirements</span></span>  
 <span data-ttu-id="9b29b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b29b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b29b-112">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="9b29b-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9b29b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b29b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b29b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b29b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b29b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b29b-115">See also</span></span>

- [<span data-ttu-id="9b29b-116">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b29b-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
