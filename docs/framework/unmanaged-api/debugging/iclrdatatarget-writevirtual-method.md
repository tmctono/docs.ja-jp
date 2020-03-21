---
title: ICLRDataTarget::WriteVirtual メソッド
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: bd2f67c2d7230d3873b4dc0df73ac1be778a0828
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179097"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="5e88b-102">ICLRDataTarget::WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="5e88b-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="5e88b-103">指定したバッファーから指定した仮想メモリ アドレスにデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="5e88b-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e88b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e88b-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e88b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e88b-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5e88b-106">[in]仮想メモリ アドレスを格納するCLRDATA_ADDRESS。</span><span class="sxs-lookup"><span data-stu-id="5e88b-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="5e88b-107">[in]書き込まれるデータを格納するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e88b-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="5e88b-108">[in]書き込むバイト数。</span><span class="sxs-lookup"><span data-stu-id="5e88b-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="5e88b-109">[アウト]書き込まれた実際のバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5e88b-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e88b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="5e88b-110">Requirements</span></span>  
 <span data-ttu-id="5e88b-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e88b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e88b-112">**ヘッダー:** をします。</span><span class="sxs-lookup"><span data-stu-id="5e88b-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5e88b-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e88b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e88b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e88b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e88b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e88b-115">See also</span></span>

- [<span data-ttu-id="5e88b-116">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e88b-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
