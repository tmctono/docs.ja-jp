---
title: IMetaDataEmit2::SaveDeltaToStream メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
ms.openlocfilehash: 7e8376f3a029b0e3ec51a1e7587dd14b3e7530ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177427"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="0d15d-102">IMetaDataEmit2::SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="0d15d-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="0d15d-103">現在のエディット コンティニュ セッションの変更を、指定したストリームに保存します。</span><span class="sxs-lookup"><span data-stu-id="0d15d-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d15d-104">構文</span><span class="sxs-lookup"><span data-stu-id="0d15d-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d15d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d15d-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="0d15d-106">[in]変更を保存する書き込み可能なストリームへのインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="0d15d-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="0d15d-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="0d15d-107">[in] Reserved.</span></span> <span data-ttu-id="0d15d-108">必ずゼロを指定します。</span><span class="sxs-lookup"><span data-stu-id="0d15d-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d15d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d15d-109">Requirements</span></span>  
 <span data-ttu-id="0d15d-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d15d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d15d-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="0d15d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d15d-112">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d15d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d15d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d15d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d15d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d15d-114">See also</span></span>

- [<span data-ttu-id="0d15d-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d15d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="0d15d-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="0d15d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
