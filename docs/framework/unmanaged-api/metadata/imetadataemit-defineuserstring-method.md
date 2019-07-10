---
title: IMetaDataEmit::DefineUserString メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25e35fd9afd2ce4dc60e23ccd64e0630a008bf39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777432"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="4ec45-102">IMetaDataEmit::DefineUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="4ec45-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="4ec45-103">指定されたリテラル文字列のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec45-104">構文</span><span class="sxs-lookup"><span data-stu-id="4ec45-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ec45-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4ec45-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="4ec45-106">[in]格納するユーザー文字列。</span><span class="sxs-lookup"><span data-stu-id="4ec45-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="4ec45-107">[in]ワイド文字の数`szString`します。</span><span class="sxs-lookup"><span data-stu-id="4ec45-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="4ec45-108">[out]割り当てられた文字列トークン。</span><span class="sxs-lookup"><span data-stu-id="4ec45-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec45-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="4ec45-109">Requirements</span></span>  
 <span data-ttu-id="4ec45-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4ec45-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec45-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4ec45-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ec45-112">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="4ec45-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ec45-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec45-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec45-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="4ec45-114">See also</span></span>

- [<span data-ttu-id="4ec45-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ec45-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4ec45-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4ec45-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
