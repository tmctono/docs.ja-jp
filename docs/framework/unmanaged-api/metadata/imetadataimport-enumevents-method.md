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
ms.openlocfilehash: 4faf8646b81f92ddf65eff15fdc610d275b37864
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440015"
---
# <a name="imetadataimportenumevents-method"></a><span data-ttu-id="a43c0-102">IMetaDataImport::EnumEvents メソッド</span><span class="sxs-lookup"><span data-stu-id="a43c0-102">IMetaDataImport::EnumEvents Method</span></span>
<span data-ttu-id="a43c0-103">指定した TypeDef トークンのイベント定義トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="a43c0-103">Enumerates event definition tokens for the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43c0-104">構文</span><span class="sxs-lookup"><span data-stu-id="a43c0-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumEvents (   
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdEvent     rEvents[],   
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a43c0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a43c0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a43c0-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="a43c0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="a43c0-107">からイベント定義を列挙する TypeDef トークン。</span><span class="sxs-lookup"><span data-stu-id="a43c0-107">[in] The TypeDef token whose event definitions are to be enumerated.</span></span>  
  
 `rEvents`  
 <span data-ttu-id="a43c0-108">入出力返されたイベントの配列。</span><span class="sxs-lookup"><span data-stu-id="a43c0-108">[out] The array of returned events.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a43c0-109">[in] `rEvents` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="a43c0-109">[in] The maximum size of the `rEvents` array.</span></span>  
  
 `pcEvents`  
 <span data-ttu-id="a43c0-110">入出力`rEvents`で返されるイベントの実際の数。</span><span class="sxs-lookup"><span data-stu-id="a43c0-110">[out] The actual number of events returned in `rEvents`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a43c0-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="a43c0-111">Return Value</span></span>  
  
|<span data-ttu-id="a43c0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a43c0-112">HRESULT</span></span>|<span data-ttu-id="a43c0-113">説明</span><span class="sxs-lookup"><span data-stu-id="a43c0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a43c0-114">`EnumEvents` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="a43c0-114">`EnumEvents` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a43c0-115">列挙するイベントがありません。</span><span class="sxs-lookup"><span data-stu-id="a43c0-115">There are no events to enumerate.</span></span> <span data-ttu-id="a43c0-116">この場合、`pcEvents` は0になります。</span><span class="sxs-lookup"><span data-stu-id="a43c0-116">In that case, `pcEvents` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a43c0-117">要件</span><span class="sxs-lookup"><span data-stu-id="a43c0-117">Requirements</span></span>  
 <span data-ttu-id="a43c0-118">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a43c0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a43c0-119">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="a43c0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a43c0-120">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="a43c0-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a43c0-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a43c0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43c0-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="a43c0-122">See also</span></span>

- [<span data-ttu-id="a43c0-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a43c0-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a43c0-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a43c0-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
