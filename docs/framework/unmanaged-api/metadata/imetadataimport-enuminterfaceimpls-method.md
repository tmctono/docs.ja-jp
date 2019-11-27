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
ms.openlocfilehash: 4c819bff50e6644a733374e9863d670d3323ee68
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449524"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="02961-102">IMetaDataImport::EnumInterfaceImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="02961-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="02961-103">指定した `TypeDef`によって実装されているすべてのインターフェイスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="02961-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="02961-104">構文</span><span class="sxs-lookup"><span data-stu-id="02961-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02961-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="02961-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="02961-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="02961-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="02961-107">からインターフェイスの実装を表す MethodDef トークンを列挙する TypeDef のトークン。</span><span class="sxs-lookup"><span data-stu-id="02961-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="02961-108">入出力MethodDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="02961-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="02961-109">[in] `rImpls` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="02961-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="02961-110">入出力`rImpls`で返されたトークンの実際の数。</span><span class="sxs-lookup"><span data-stu-id="02961-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="02961-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="02961-111">Return Value</span></span>  
  
|<span data-ttu-id="02961-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="02961-112">HRESULT</span></span>|<span data-ttu-id="02961-113">説明</span><span class="sxs-lookup"><span data-stu-id="02961-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="02961-114">`EnumInterfaceImpls` が正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="02961-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="02961-115">列挙する MethodDef トークンがありません。</span><span class="sxs-lookup"><span data-stu-id="02961-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="02961-116">この場合、`pcImpls` は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="02961-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="02961-117">コメント</span><span class="sxs-lookup"><span data-stu-id="02961-117">Remarks</span></span>

<span data-ttu-id="02961-118">列挙体は、指定した `TypeDef`によって実装された各インターフェイスの `mdInterfaceImpl` トークンのコレクションを返します。</span><span class="sxs-lookup"><span data-stu-id="02961-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="02961-119">インターフェイストークンは、インターフェイスが指定された順序で返されます (`DefineTypeDef` または `SetTypeDefProps`)。</span><span class="sxs-lookup"><span data-stu-id="02961-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="02961-120">返された `mdInterfaceImpl` トークンのプロパティは、 [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)を使用して照会できます。</span><span class="sxs-lookup"><span data-stu-id="02961-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="02961-121">要件</span><span class="sxs-lookup"><span data-stu-id="02961-121">Requirements</span></span>  
 <span data-ttu-id="02961-122">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02961-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02961-123">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="02961-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="02961-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="02961-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="02961-125">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02961-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02961-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="02961-126">See also</span></span>

- [<span data-ttu-id="02961-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02961-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="02961-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="02961-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
