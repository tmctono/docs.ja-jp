---
title: IMetaDataImport::EnumTypeSpecs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 94b4c3935c949c0c4008e41244713b6bfa4dba84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503719"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="3ec69-102">IMetaDataImport::EnumTypeSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="3ec69-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="3ec69-103">現在のメタデータ スコープに定義されている TypeSpec トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="3ec69-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec69-104">構文</span><span class="sxs-lookup"><span data-stu-id="3ec69-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ec69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3ec69-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3ec69-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3ec69-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3ec69-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ec69-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="3ec69-108">入出力TypeSpec トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="3ec69-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3ec69-109">[in] `rTypeSpecs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="3ec69-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="3ec69-110">入出力で返された TypeSpec トークンの数 `rTypeSpecs` 。</span><span class="sxs-lookup"><span data-stu-id="3ec69-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ec69-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3ec69-111">Return Value</span></span>  
  
|<span data-ttu-id="3ec69-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ec69-112">HRESULT</span></span>|<span data-ttu-id="3ec69-113">説明</span><span class="sxs-lookup"><span data-stu-id="3ec69-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3ec69-114">`EnumTypeSpecs`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3ec69-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3ec69-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="3ec69-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3ec69-116">この場合、 `pcTypeSpecs` は0になります。</span><span class="sxs-lookup"><span data-stu-id="3ec69-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ec69-117">解説</span><span class="sxs-lookup"><span data-stu-id="3ec69-117">Remarks</span></span>  
 <span data-ttu-id="3ec69-118">TypeSpec トークンは、 [IMetaDataEmit:: GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md)メソッドによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ec69-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ec69-119">要件</span><span class="sxs-lookup"><span data-stu-id="3ec69-119">Requirements</span></span>  
 <span data-ttu-id="3ec69-120">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ec69-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ec69-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3ec69-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ec69-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3ec69-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ec69-123">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec69-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec69-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ec69-124">See also</span></span>

- [<span data-ttu-id="3ec69-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ec69-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3ec69-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3ec69-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
