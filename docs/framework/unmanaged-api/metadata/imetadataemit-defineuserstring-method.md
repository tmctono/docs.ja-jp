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
ms.openlocfilehash: aa5d66d2408010d7a7b52ec68a18f667097795ae
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450175"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d9f72-102">IMetaDataEmit::DefineUserString メソッド</span><span class="sxs-lookup"><span data-stu-id="d9f72-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="d9f72-103">指定されたリテラル文字列のメタデータトークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9f72-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f72-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9f72-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9f72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9f72-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="d9f72-106">から格納するユーザー文字列。</span><span class="sxs-lookup"><span data-stu-id="d9f72-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d9f72-107">から`szString`内のワイド文字の数。</span><span class="sxs-lookup"><span data-stu-id="d9f72-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d9f72-108">入出力割り当てられた文字列トークン。</span><span class="sxs-lookup"><span data-stu-id="d9f72-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9f72-109">要件</span><span class="sxs-lookup"><span data-stu-id="d9f72-109">Requirements</span></span>  
 <span data-ttu-id="d9f72-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9f72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f72-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d9f72-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9f72-112">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="d9f72-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9f72-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f72-114">参照</span><span class="sxs-lookup"><span data-stu-id="d9f72-114">See also</span></span>

- [<span data-ttu-id="d9f72-115">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9f72-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d9f72-116">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d9f72-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
