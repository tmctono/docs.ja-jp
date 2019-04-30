---
title: IMetaDataEmit::SaveToMemory メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050065"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="2b740-102">IMetaDataEmit::SaveToMemory メソッド</span><span class="sxs-lookup"><span data-stu-id="2b740-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="2b740-103">メモリの指定された領域を現在のスコープ内のすべてのメタデータを保存します。</span><span class="sxs-lookup"><span data-stu-id="2b740-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b740-104">構文</span><span class="sxs-lookup"><span data-stu-id="2b740-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b740-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2b740-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="2b740-106">[out]メタデータの書き込みを開始する位置のアドレス。</span><span class="sxs-lookup"><span data-stu-id="2b740-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="2b740-107">[in]割り当てられたメモリのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="2b740-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b740-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b740-108">Requirements</span></span>  
 <span data-ttu-id="2b740-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b740-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b740-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b740-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b740-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="2b740-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b740-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b740-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b740-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b740-113">See also</span></span>

- [<span data-ttu-id="2b740-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b740-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2b740-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b740-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
