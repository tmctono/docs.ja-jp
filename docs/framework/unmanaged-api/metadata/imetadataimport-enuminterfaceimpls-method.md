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
ms.openlocfilehash: 910c40413075131765a37e00703ac892e3f39641
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492205"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="3a7e2-102">IMetaDataImport::EnumInterfaceImpls メソッド</span><span class="sxs-lookup"><span data-stu-id="3a7e2-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="3a7e2-103">指定したによって実装されているすべてのインターフェイスを列挙 `TypeDef` します。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="3a7e2-104">構文</span><span class="sxs-lookup"><span data-stu-id="3a7e2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a7e2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3a7e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3a7e2-106">[入力、出力]列挙子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="3a7e2-107">からインターフェイスの実装を表す MethodDef トークンを列挙する TypeDef のトークン。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="3a7e2-108">入出力MethodDef トークンを格納するために使用される配列。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3a7e2-109">から配列の最大長 `rImpls` 。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="3a7e2-110">入出力で返されたトークンの実際の数 `rImpls` 。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a7e2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3a7e2-111">Return Value</span></span>  
  
|<span data-ttu-id="3a7e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a7e2-112">HRESULT</span></span>|<span data-ttu-id="3a7e2-113">説明</span><span class="sxs-lookup"><span data-stu-id="3a7e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3a7e2-114">`EnumInterfaceImpls`正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3a7e2-115">列挙する MethodDef トークンがありません。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="3a7e2-116">この場合、 `pcImpls` は0に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="3a7e2-117">解説</span><span class="sxs-lookup"><span data-stu-id="3a7e2-117">Remarks</span></span>

<span data-ttu-id="3a7e2-118">列挙体は `mdInterfaceImpl` 、指定したによって実装された各インターフェイスのトークンのコレクションを返し `TypeDef` ます。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="3a7e2-119">インターフェイストークンは、インターフェイスが指定された順序で返され `DefineTypeDef` ます (またはを使用 `SetTypeDefProps` )。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="3a7e2-120">返されたトークンのプロパティは、 `mdInterfaceImpl` [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)を使用して照会できます。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3a7e2-121">要件</span><span class="sxs-lookup"><span data-stu-id="3a7e2-121">Requirements</span></span>  
 <span data-ttu-id="3a7e2-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a7e2-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a7e2-123">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="3a7e2-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a7e2-124">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="3a7e2-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a7e2-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a7e2-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a7e2-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a7e2-126">See also</span></span>

- [<span data-ttu-id="3a7e2-127">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a7e2-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3a7e2-128">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3a7e2-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
