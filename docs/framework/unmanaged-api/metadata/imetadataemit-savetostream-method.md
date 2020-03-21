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
ms.openlocfilehash: 7db27670b72a5018a03d4614b69486f67bcef155
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175682"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="e1ab0-102">IMetaDataEmit::SaveToStream メソッド</span><span class="sxs-lookup"><span data-stu-id="e1ab0-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="e1ab0-103">現在のスコープ内のすべてのメタデータを指定した`IStream`.</span><span class="sxs-lookup"><span data-stu-id="e1ab0-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1ab0-104">構文</span><span class="sxs-lookup"><span data-stu-id="e1ab0-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1ab0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e1ab0-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="e1ab0-106">[in]保存先の書き込み可能なストリーム。</span><span class="sxs-lookup"><span data-stu-id="e1ab0-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="e1ab0-107">[in] 予約されています。</span><span class="sxs-lookup"><span data-stu-id="e1ab0-107">[in] Reserved.</span></span> <span data-ttu-id="e1ab0-108">ゼロを指定してください。</span><span class="sxs-lookup"><span data-stu-id="e1ab0-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1ab0-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1ab0-109">Requirements</span></span>  
 <span data-ttu-id="e1ab0-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1ab0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1ab0-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e1ab0-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e1ab0-112">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1ab0-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e1ab0-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1ab0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1ab0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1ab0-114">See also</span></span>

- [<span data-ttu-id="e1ab0-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1ab0-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e1ab0-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e1ab0-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
