---
title: IMetaDataTables2::GetMetaDataStreamInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228849"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="50fdc-102">IMetaDataTables2::GetMetaDataStreamInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="50fdc-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="50fdc-103">名前、サイズ、および指定したインデックス位置にあるメタデータのストリームの内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="50fdc-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50fdc-104">構文</span><span class="sxs-lookup"><span data-stu-id="50fdc-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50fdc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50fdc-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="50fdc-106">[in]要求されたメタデータのストリームのインデックス。</span><span class="sxs-lookup"><span data-stu-id="50fdc-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="50fdc-107">[out]ストリームの名前へのポインター。</span><span class="sxs-lookup"><span data-stu-id="50fdc-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="50fdc-108">[out]メタデータ ストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="50fdc-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="50fdc-109">[out]サイズ (バイト単位) の`ppv`します。</span><span class="sxs-lookup"><span data-stu-id="50fdc-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50fdc-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="50fdc-110">Requirements</span></span>  
 <span data-ttu-id="50fdc-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50fdc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50fdc-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50fdc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50fdc-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="50fdc-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50fdc-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50fdc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50fdc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="50fdc-115">See also</span></span>

- [<span data-ttu-id="50fdc-116">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50fdc-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="50fdc-117">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50fdc-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
