---
title: IMetaDataImport::EnumTypeDefs メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 3854cb4aa3d229c87466c0a35a72447ceb235624
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449995"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="8bf5e-102">IMetaDataImport::EnumTypeDefs メソッド</span><span class="sxs-lookup"><span data-stu-id="8bf5e-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="8bf5e-103">現在のスコープ内のすべての型を表す TypeDef トークンを列挙します。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bf5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="8bf5e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,   
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,   
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bf5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8bf5e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8bf5e-106">入出力新しい列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="8bf5e-107">このメソッドの最初の呼び出しでは、この値は NULL である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="8bf5e-108">からTypeDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8bf5e-109">[in] `rTypeDefs` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="8bf5e-110">入出力`rTypeDefs`で返された TypeDef トークンの数。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8bf5e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="8bf5e-111">Return Value</span></span>  
  
|<span data-ttu-id="8bf5e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8bf5e-112">HRESULT</span></span>|<span data-ttu-id="8bf5e-113">説明</span><span class="sxs-lookup"><span data-stu-id="8bf5e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8bf5e-114">`EnumTypeDefs` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8bf5e-115">列挙するトークンがありません。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8bf5e-116">この場合、`pcTypeDefs` は0になります。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bf5e-117">コメント</span><span class="sxs-lookup"><span data-stu-id="8bf5e-117">Remarks</span></span>  
 <span data-ttu-id="8bf5e-118">TypeDef トークンは、クラスやインターフェイスなどの型、および拡張メカニズムを使用して追加された型を表します。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bf5e-119">要件</span><span class="sxs-lookup"><span data-stu-id="8bf5e-119">Requirements</span></span>  
 <span data-ttu-id="8bf5e-120">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8bf5e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bf5e-121">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8bf5e-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bf5e-122">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="8bf5e-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bf5e-123">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bf5e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf5e-124">参照</span><span class="sxs-lookup"><span data-stu-id="8bf5e-124">See also</span></span>

- [<span data-ttu-id="8bf5e-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bf5e-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8bf5e-126">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8bf5e-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
