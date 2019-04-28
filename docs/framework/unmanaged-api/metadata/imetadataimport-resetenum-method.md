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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777430"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="61767-102">IMetaDataImport::ResetEnum メソッド</span><span class="sxs-lookup"><span data-stu-id="61767-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="61767-103">指定した列挙子を指定した位置にリセットします。</span><span class="sxs-lookup"><span data-stu-id="61767-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61767-104">構文</span><span class="sxs-lookup"><span data-stu-id="61767-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61767-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61767-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="61767-106">[in]リセットする列挙子。</span><span class="sxs-lookup"><span data-stu-id="61767-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="61767-107">[in]列挙子を配置する位置の新しい位置。</span><span class="sxs-lookup"><span data-stu-id="61767-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61767-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="61767-108">Requirements</span></span>  
 <span data-ttu-id="61767-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61767-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61767-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61767-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61767-111">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="61767-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61767-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61767-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61767-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="61767-113">See also</span></span>

- [<span data-ttu-id="61767-114">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61767-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="61767-115">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61767-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
