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
ms.openlocfilehash: b5da781f148c23efcc909ad65e198e4f3c6fe5b5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447874"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="164cc-102">IMetaDataEmit2::SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="164cc-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="164cc-103">現在のエディットコンティニュセッションから、指定されたストリームに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="164cc-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="164cc-104">構文</span><span class="sxs-lookup"><span data-stu-id="164cc-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="164cc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="164cc-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="164cc-106">から変更を保存する書き込み可能なストリームへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="164cc-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="164cc-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="164cc-107">[in] Reserved.</span></span> <span data-ttu-id="164cc-108">この値は0にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="164cc-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="164cc-109">要件</span><span class="sxs-lookup"><span data-stu-id="164cc-109">Requirements</span></span>  
 <span data-ttu-id="164cc-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="164cc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="164cc-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="164cc-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="164cc-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="164cc-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="164cc-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="164cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164cc-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="164cc-114">See also</span></span>

- [<span data-ttu-id="164cc-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164cc-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="164cc-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="164cc-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
