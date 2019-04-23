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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a0beb9a0b1ef2db6ff32fee1b55b3478794509a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59219734"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="1a51e-102">ICLRDataTarget::WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="1a51e-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="1a51e-103">指定された仮想メモリ アドレスには、指定したバッファーからデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="1a51e-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a51e-104">構文</span><span class="sxs-lookup"><span data-stu-id="1a51e-104">Syntax</span></span>  
  
```  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]   
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a51e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a51e-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="1a51e-106">[in]仮想メモリ アドレスを格納する CLRDATA_ADDRESS します。</span><span class="sxs-lookup"><span data-stu-id="1a51e-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="1a51e-107">[in]書き込むデータを格納するバッファーへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a51e-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="1a51e-108">[in]書き込むバイト数。</span><span class="sxs-lookup"><span data-stu-id="1a51e-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="1a51e-109">[out]実際に書き込まれたバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="1a51e-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a51e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="1a51e-110">Requirements</span></span>  
 <span data-ttu-id="1a51e-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a51e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a51e-112">**ヘッダー:** ClrData.idl、ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1a51e-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1a51e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a51e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a51e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a51e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a51e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1a51e-115">See also</span></span>

- [<span data-ttu-id="1a51e-116">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1a51e-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
