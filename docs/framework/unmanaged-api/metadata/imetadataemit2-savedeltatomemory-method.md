---
title: IMetaDataEmit2::SaveDeltaToMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8cc9544279c6be3efe278c3effda00bc2d387ec
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495365"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="d35eb-102">IMetaDataEmit2::SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="d35eb-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="d35eb-103">エディット コンティニュの現在のセッションからの変更をメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="d35eb-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="d35eb-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d35eb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d35eb-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="d35eb-106">[out]メタデータのデルタの書き込みを開始する位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="d35eb-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d35eb-107">[in]変更のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d35eb-107">[in] The size of the changes.</span></span> <span data-ttu-id="d35eb-108">使用[imetadataemit 2::getdeltasavesize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)サイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="d35eb-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d35eb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d35eb-109">Requirements</span></span>  
 <span data-ttu-id="d35eb-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d35eb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d35eb-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d35eb-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d35eb-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d35eb-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d35eb-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d35eb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35eb-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="d35eb-114">See also</span></span>
- [<span data-ttu-id="d35eb-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d35eb-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d35eb-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d35eb-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
