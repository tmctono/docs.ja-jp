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
ms.openlocfilehash: 0332fae46d6a65cfb7cc0b929cc2fd0d97e1790e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179157"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="c27fb-102">ICLRDataTarget::ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="c27fb-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="c27fb-103">指定した仮想メモリ アドレスから指定したバッファーにデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c27fb-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c27fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="c27fb-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c27fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c27fb-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c27fb-106">[in]仮想メモリ アドレスを格納するCLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="c27fb-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c27fb-107">[アウト]データを受け取るバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c27fb-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="c27fb-108">[in]バッファーの長さ。</span><span class="sxs-lookup"><span data-stu-id="c27fb-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="c27fb-109">[アウト]返されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c27fb-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c27fb-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c27fb-110">Requirements</span></span>  
 <span data-ttu-id="c27fb-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c27fb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c27fb-112">**ヘッダー:** をします。</span><span class="sxs-lookup"><span data-stu-id="c27fb-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c27fb-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c27fb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c27fb-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c27fb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c27fb-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c27fb-115">See also</span></span>

- [<span data-ttu-id="c27fb-116">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c27fb-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
