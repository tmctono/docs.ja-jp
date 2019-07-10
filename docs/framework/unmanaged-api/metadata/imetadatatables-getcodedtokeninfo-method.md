---
title: IMetaDataTables::GetCodedTokenInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b89409a08ed2dff0111b3b6e552960ac78a5882e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781533"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="39297-102">IMetaDataTables::GetCodedTokenInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="39297-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="39297-103">指定した行のインデックスに関連付けられているトークンの配列へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="39297-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39297-104">構文</span><span class="sxs-lookup"><span data-stu-id="39297-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39297-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39297-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="39297-106">[in]コード化されたトークンの種類。</span><span class="sxs-lookup"><span data-stu-id="39297-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="39297-107">[out]長さへのポインター`ppTokens`します。</span><span class="sxs-lookup"><span data-stu-id="39297-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="39297-108">[out]返されたトークンの一覧を格納している配列へのポインターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="39297-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="39297-109">[out]トークンの名前へのポインターへのポインター`ixCdTkn`します。</span><span class="sxs-lookup"><span data-stu-id="39297-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39297-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="39297-110">Requirements</span></span>  
 <span data-ttu-id="39297-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39297-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39297-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="39297-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39297-113">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="39297-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39297-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39297-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39297-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="39297-115">See also</span></span>

- [<span data-ttu-id="39297-116">IMetaDataTables インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39297-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="39297-117">IMetaDataTables2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="39297-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
