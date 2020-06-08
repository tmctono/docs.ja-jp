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
ms.openlocfilehash: a8f46871dde4c664a502c261fc882f3badf0f362
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492757"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="59877-102">IMetaDataEmit2::SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="59877-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="59877-103">現在のエディットコンティニュセッションから、指定されたストリームに変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="59877-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59877-104">構文</span><span class="sxs-lookup"><span data-stu-id="59877-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59877-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59877-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="59877-106">から変更を保存する書き込み可能なストリームへのインターフェイスポインター。</span><span class="sxs-lookup"><span data-stu-id="59877-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="59877-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="59877-107">[in] Reserved.</span></span> <span data-ttu-id="59877-108">必ずゼロを指定します。</span><span class="sxs-lookup"><span data-stu-id="59877-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59877-109">要件</span><span class="sxs-lookup"><span data-stu-id="59877-109">Requirements</span></span>  
 <span data-ttu-id="59877-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59877-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59877-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="59877-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59877-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="59877-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59877-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59877-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59877-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="59877-114">See also</span></span>

- [<span data-ttu-id="59877-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59877-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="59877-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59877-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
