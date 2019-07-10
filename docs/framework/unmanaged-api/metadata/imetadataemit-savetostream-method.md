---
title: IMetaDataEmit::SaveToStream メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96b3b270fb12aa451d9026435dd3d2c4c196b09c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782025"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="fdb62-102">IMetaDataEmit::SaveToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="fdb62-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="fdb62-103">指定した現在のスコープ内のすべてのメタデータの保存`IStream`します。</span><span class="sxs-lookup"><span data-stu-id="fdb62-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb62-104">構文</span><span class="sxs-lookup"><span data-stu-id="fdb62-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (   
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdb62-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fdb62-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="fdb62-106">[in]保存する書き込み可能なストリーム。</span><span class="sxs-lookup"><span data-stu-id="fdb62-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="fdb62-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="fdb62-107">[in] Reserved.</span></span> <span data-ttu-id="fdb62-108">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="fdb62-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb62-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="fdb62-109">Requirements</span></span>  
 <span data-ttu-id="fdb62-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdb62-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb62-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fdb62-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdb62-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="fdb62-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdb62-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb62-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb62-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdb62-114">See also</span></span>

- [<span data-ttu-id="fdb62-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdb62-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fdb62-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fdb62-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
