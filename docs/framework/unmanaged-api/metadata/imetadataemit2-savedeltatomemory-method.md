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
ms.openlocfilehash: fa95a737747e9153eb844cddd8e0684585b9108b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049974"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="721dd-102">IMetaDataEmit2::SaveDeltaToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="721dd-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="721dd-103">エディット コンティニュの現在のセッションからの変更をメモリに保存します。</span><span class="sxs-lookup"><span data-stu-id="721dd-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="721dd-104">構文</span><span class="sxs-lookup"><span data-stu-id="721dd-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,   
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="721dd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="721dd-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="721dd-106">[out]メタデータのデルタの書き込みを開始する位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="721dd-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="721dd-107">[in]変更のサイズ。</span><span class="sxs-lookup"><span data-stu-id="721dd-107">[in] The size of the changes.</span></span> <span data-ttu-id="721dd-108">使用[imetadataemit 2::getdeltasavesize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)サイズを決定します。</span><span class="sxs-lookup"><span data-stu-id="721dd-108">Use [IMetaDataEmit2::GetDeltaSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="721dd-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="721dd-109">Requirements</span></span>  
 <span data-ttu-id="721dd-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="721dd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="721dd-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="721dd-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="721dd-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="721dd-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="721dd-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="721dd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="721dd-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="721dd-114">See also</span></span>

- [<span data-ttu-id="721dd-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="721dd-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="721dd-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="721dd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
