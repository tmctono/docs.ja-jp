---
title: IMetaDataImport::EnumInterfaceImpls メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175500"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="91dcb-102">IMetaDataImport::EnumInterfaceImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="91dcb-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="91dcb-103">指定した`TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="91dcb-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="91dcb-104">構文</span><span class="sxs-lookup"><span data-stu-id="91dcb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91dcb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91dcb-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="91dcb-106">[イン、アウト]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="91dcb-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="91dcb-107">[in]インターフェイスの実装を表す MethodDef トークンを列挙する TypeDef のトークン。</span><span class="sxs-lookup"><span data-stu-id="91dcb-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="91dcb-108">[アウト]メソッド定義トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="91dcb-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="91dcb-109">[in]`rImpls`配列の最大長。</span><span class="sxs-lookup"><span data-stu-id="91dcb-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="91dcb-110">[アウト]に返されるトークンの実際の`rImpls`数。</span><span class="sxs-lookup"><span data-stu-id="91dcb-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91dcb-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="91dcb-111">Return Value</span></span>  
  
|<span data-ttu-id="91dcb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91dcb-112">HRESULT</span></span>|<span data-ttu-id="91dcb-113">説明</span><span class="sxs-lookup"><span data-stu-id="91dcb-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="91dcb-114">`EnumInterfaceImpls`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="91dcb-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="91dcb-115">列挙する MethodDef トークンはありません。</span><span class="sxs-lookup"><span data-stu-id="91dcb-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="91dcb-116">その場合は、`pcImpls`ゼロに設定されます。</span><span class="sxs-lookup"><span data-stu-id="91dcb-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="91dcb-117">解説</span><span class="sxs-lookup"><span data-stu-id="91dcb-117">Remarks</span></span>

<span data-ttu-id="91dcb-118">列挙体は、指定された`mdInterfaceImpl`によって実装される各インターフェイスのトークンの`TypeDef`コレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="91dcb-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="91dcb-119">インターフェイス トークンは、インターフェイスが指定された順序で返されます`DefineTypeDef` `SetTypeDefProps`(または を通じて)。</span><span class="sxs-lookup"><span data-stu-id="91dcb-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="91dcb-120">返される`mdInterfaceImpl`トークンのプロパティは[、GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)を使用してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="91dcb-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="91dcb-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="91dcb-121">Requirements</span></span>  
 <span data-ttu-id="91dcb-122">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91dcb-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91dcb-123">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="91dcb-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91dcb-124">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="91dcb-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91dcb-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91dcb-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91dcb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="91dcb-126">See also</span></span>

- [<span data-ttu-id="91dcb-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91dcb-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="91dcb-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="91dcb-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
