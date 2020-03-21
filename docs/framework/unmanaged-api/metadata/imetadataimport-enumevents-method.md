---
title: IMetaDataImport::EnumEvents メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: bd50d63b1f7080f510c29f90979b7b36242af1c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177372"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="551d3-102">IMetaDataImport::EnumEvents メソッド</span><span class="sxs-lookup"><span data-stu-id="551d3-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="551d3-103">指定した TypeDef トークンのイベント定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="551d3-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="551d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="551d3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="551d3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="551d3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="551d3-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="551d3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="551d3-107">[in]イベント定義を列挙する TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="551d3-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="551d3-108">[アウト]返されたイベントの配列。</span><span class="sxs-lookup"><span data-stu-id="551d3-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="551d3-109">[in] `rEvents` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="551d3-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="551d3-110">[アウト]で返される実際のイベント数`rEvents`。</span><span class="sxs-lookup"><span data-stu-id="551d3-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="551d3-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="551d3-111">Return Value</span></span>  
  
|<span data-ttu-id="551d3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="551d3-112">HRESULT</span></span>|<span data-ttu-id="551d3-113">説明</span><span class="sxs-lookup"><span data-stu-id="551d3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="551d3-114">`EnumEvents`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="551d3-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="551d3-115">列挙するイベントはありません。</span><span class="sxs-lookup"><span data-stu-id="551d3-115">There are no events to enumerate.</span></span> <span data-ttu-id="551d3-116">その場合は、`pcEvents`ゼロです。</span><span class="sxs-lookup"><span data-stu-id="551d3-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="551d3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="551d3-117">Requirements</span></span>  
 <span data-ttu-id="551d3-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="551d3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="551d3-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="551d3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="551d3-120">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="551d3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="551d3-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="551d3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="551d3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="551d3-122">See also</span></span>

- [<span data-ttu-id="551d3-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="551d3-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="551d3-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="551d3-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
