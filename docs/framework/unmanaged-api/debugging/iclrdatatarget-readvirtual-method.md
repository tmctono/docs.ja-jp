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
ms.openlocfilehash: 0c26a2df3f73af5ebd1f8b735d7662bb23ba4228
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134162"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="eb0bf-102">ICLRDataTarget::ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="eb0bf-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="eb0bf-103">指定された仮想メモリアドレスから指定されたバッファーにデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb0bf-104">構文</span><span class="sxs-lookup"><span data-stu-id="eb0bf-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb0bf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb0bf-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="eb0bf-106">から仮想メモリアドレスを格納する CLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="eb0bf-107">入出力データを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="eb0bf-108">からバッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="eb0bf-109">入出力返されたバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb0bf-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="eb0bf-110">Requirements</span></span>  
 <span data-ttu-id="eb0bf-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb0bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb0bf-112">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="eb0bf-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="eb0bf-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb0bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb0bf-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb0bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0bf-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb0bf-115">See also</span></span>

- [<span data-ttu-id="eb0bf-116">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="eb0bf-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
