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
ms.openlocfilehash: a71d8694ec8c5bd35ecd3e98ed32e05bc7b382fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177619"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="83051-102">IMetaDataEmit::DefineUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="83051-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="83051-103">指定したリテラル文字列のメタデータ トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="83051-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83051-104">構文</span><span class="sxs-lookup"><span data-stu-id="83051-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83051-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83051-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="83051-106">[in]格納するユーザー文字列。</span><span class="sxs-lookup"><span data-stu-id="83051-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="83051-107">[in]のワイド文字の`szString`数。</span><span class="sxs-lookup"><span data-stu-id="83051-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="83051-108">[アウト]割り当てられた文字列トークン。</span><span class="sxs-lookup"><span data-stu-id="83051-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83051-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="83051-109">Requirements</span></span>  
 <span data-ttu-id="83051-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83051-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83051-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="83051-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83051-112">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="83051-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83051-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83051-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83051-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="83051-114">See also</span></span>

- [<span data-ttu-id="83051-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83051-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="83051-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83051-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
