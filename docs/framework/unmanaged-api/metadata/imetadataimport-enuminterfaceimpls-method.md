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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992343"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="14afd-102">IMetaDataImport::EnumInterfaceImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="14afd-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="14afd-103">指定したによって実装されるすべてのインターフェイスを列挙`TypeDef`します。</span><span class="sxs-lookup"><span data-stu-id="14afd-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="14afd-104">構文</span><span class="sxs-lookup"><span data-stu-id="14afd-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14afd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="14afd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="14afd-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="14afd-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="14afd-107">[in]インターフェイスの実装を表す MethodDef トークンを持つが列挙 TypeDef のトークンです。</span><span class="sxs-lookup"><span data-stu-id="14afd-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="14afd-108">[out]MethodDef トークンを格納するために使用する配列。</span><span class="sxs-lookup"><span data-stu-id="14afd-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="14afd-109">[in] `rImpls` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="14afd-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="14afd-110">[out]実際のトークンで返される数`rImpls`します。</span><span class="sxs-lookup"><span data-stu-id="14afd-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14afd-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="14afd-111">Return Value</span></span>  
  
|<span data-ttu-id="14afd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14afd-112">HRESULT</span></span>|<span data-ttu-id="14afd-113">説明</span><span class="sxs-lookup"><span data-stu-id="14afd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="14afd-114">`EnumInterfaceImpls` 正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="14afd-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="14afd-115">MethodDef トークンを列挙することはありません。</span><span class="sxs-lookup"><span data-stu-id="14afd-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="14afd-116">その場合は、 `pcImpls` 0 に設定されます。</span><span class="sxs-lookup"><span data-stu-id="14afd-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="14afd-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="14afd-117">Remarks</span></span>

<span data-ttu-id="14afd-118">列挙体のコレクションを返します`mdInterfaceImpl`各インターフェイスを指定した実装のためのトークン`TypeDef`します。</span><span class="sxs-lookup"><span data-stu-id="14afd-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="14afd-119">インターフェイスのトークンは、インターフェイスが指定された順序で返されます (を通じて`DefineTypeDef`または`SetTypeDefProps`)。</span><span class="sxs-lookup"><span data-stu-id="14afd-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="14afd-120">プロパティは、返された`mdInterfaceImpl`を使用してトークンを照会できます[GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="14afd-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="14afd-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="14afd-121">Requirements</span></span>  
 <span data-ttu-id="14afd-122">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="14afd-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14afd-123">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="14afd-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14afd-124">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="14afd-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="14afd-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14afd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14afd-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="14afd-126">See also</span></span>

- [<span data-ttu-id="14afd-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14afd-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="14afd-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="14afd-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
