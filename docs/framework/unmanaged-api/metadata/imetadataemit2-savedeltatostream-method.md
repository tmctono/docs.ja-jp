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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31bed2019eef5a37e1086624afdae3e8f2c58632
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927232"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="c3b13-102">IMetaDataEmit2::SaveDeltaToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="c3b13-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="c3b13-103">エディット コンティニュの現在のセッションからの変更を指定したストリームに保存します。</span><span class="sxs-lookup"><span data-stu-id="c3b13-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b13-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3b13-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b13-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3b13-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="c3b13-106">[in]変更の保存先となる書き込み可能なストリームへのインターフェイス ポインター。</span><span class="sxs-lookup"><span data-stu-id="c3b13-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c3b13-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="c3b13-107">[in] Reserved.</span></span> <span data-ttu-id="c3b13-108">この値は 0 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3b13-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b13-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c3b13-109">Requirements</span></span>  
 <span data-ttu-id="c3b13-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b13-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b13-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3b13-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3b13-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="c3b13-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3b13-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b13-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b13-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3b13-114">See also</span></span>

- [<span data-ttu-id="c3b13-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3b13-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="c3b13-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c3b13-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
