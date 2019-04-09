---
title: IMetaDataImport::ResetEnum メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 143b11f0a99081b7d49bfbb68b635d92cf1e9ba3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163879"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="44df4-102">IMetaDataImport::ResetEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="44df4-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="44df4-103">指定した列挙子を指定した位置にリセットします。</span><span class="sxs-lookup"><span data-stu-id="44df4-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44df4-104">構文</span><span class="sxs-lookup"><span data-stu-id="44df4-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44df4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44df4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="44df4-106">[in]リセットする列挙子。</span><span class="sxs-lookup"><span data-stu-id="44df4-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="44df4-107">[in]列挙子を配置する位置の新しい位置。</span><span class="sxs-lookup"><span data-stu-id="44df4-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44df4-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="44df4-108">Requirements</span></span>  
 <span data-ttu-id="44df4-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44df4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44df4-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="44df4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44df4-111">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="44df4-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="44df4-112">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="44df4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="44df4-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="44df4-113">See also</span></span>

- [<span data-ttu-id="44df4-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44df4-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="44df4-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="44df4-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
