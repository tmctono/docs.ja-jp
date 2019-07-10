---
title: IMetaDataImport::GetPropertyProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e83afcf6c872927e614fce33ca96e93f0da4f497
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778876"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="fe8c9-102">IMetaDataImport::GetPropertyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="fe8c9-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="fe8c9-103">指定したトークンによって表されるプロパティのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8c9-104">構文</span><span class="sxs-lookup"><span data-stu-id="fe8c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe8c9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe8c9-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="fe8c9-106">[in]メタデータを返すプロパティを表すトークンです。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="fe8c9-107">[out]プロパティを実装する型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="fe8c9-108">[out]プロパティ名を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="fe8c9-109">[in]ワイド文字単位サイズ`szProperty`します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="fe8c9-110">[out]返されるワイド文字数`szProperty`します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="fe8c9-111">[out]プロパティに適用される属性フラグのいずれかへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="fe8c9-112">この値はビットマスクから、 [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)列挙体。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="fe8c9-113">[out]プロパティのメタデータ署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="fe8c9-114">[out]返されるバイト数`ppvSig`します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="fe8c9-115">[out]プロパティの既定値である定数の型を指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="fe8c9-116">この値は CorElementType 列挙型です。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="fe8c9-117">[out]このプロパティの既定値を格納するバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="fe8c9-118">[out]ワイド文字単位サイズ`ppDefaultValue`場合は、 `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING; は、それ以外の場合、この値は関連はありません。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="fe8c9-119">その場合、長さの`ppDefaultValue`によって指定された型から推論されます`pdwCPlusTypeFlag`します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="fe8c9-120">[out]プロパティの set アクセサー メソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="fe8c9-121">[out]プロパティの get アクセサー メソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="fe8c9-122">[out]プロパティに関連付けられているその他のメソッドを表す MethodDef トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fe8c9-123">[in] `rmdOtherMethod` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="fe8c9-124">すべてのメソッドを保持するために十分な大きさの配列を指定しない場合は警告なしスキップされます。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="fe8c9-125">[out]返される MethodDef トークン数`rmdOtherMethod`します。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe8c9-126">必要条件</span><span class="sxs-lookup"><span data-stu-id="fe8c9-126">Requirements</span></span>  
 <span data-ttu-id="fe8c9-127">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe8c9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe8c9-128">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fe8c9-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe8c9-129">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="fe8c9-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe8c9-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe8c9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8c9-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe8c9-131">See also</span></span>

- [<span data-ttu-id="fe8c9-132">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe8c9-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fe8c9-133">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fe8c9-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
