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
ms.openlocfilehash: 247a2793bf3806f5ee38585d50b4535820dfcb69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437062"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="d3666-102">IMetaDataImport::GetPropertyProps メソッド</span><span class="sxs-lookup"><span data-stu-id="d3666-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="d3666-103">指定したトークンによって表されるプロパティのメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="d3666-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3666-104">構文</span><span class="sxs-lookup"><span data-stu-id="d3666-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d3666-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d3666-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="d3666-106">からメタデータを返すプロパティを表すトークン。</span><span class="sxs-lookup"><span data-stu-id="d3666-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="d3666-107">入出力プロパティを実装する型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="d3666-108">入出力プロパティ名を保持するバッファー。</span><span class="sxs-lookup"><span data-stu-id="d3666-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="d3666-109">から`szProperty`のワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d3666-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="d3666-110">入出力`szProperty`に返されるワイド文字数。</span><span class="sxs-lookup"><span data-stu-id="d3666-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="d3666-111">入出力プロパティに適用されている属性フラグへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="d3666-112">この値は、 [Corpropertyattr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)列挙子のビットマスクです。</span><span class="sxs-lookup"><span data-stu-id="d3666-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="d3666-113">入出力プロパティのメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="d3666-114">入出力`ppvSig`で返されたバイト数。</span><span class="sxs-lookup"><span data-stu-id="d3666-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="d3666-115">入出力プロパティの既定値である定数の型を指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="d3666-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="d3666-116">この値は CorElementType 列挙子からのものです。</span><span class="sxs-lookup"><span data-stu-id="d3666-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="d3666-117">入出力このプロパティの既定値を格納するバイトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="d3666-118">入出力`pdwCPlusTypeFlag` が ELEMENT_TYPE_STRING 場合、`ppDefaultValue`のワイド文字のサイズ。それ以外の場合、この値は関係ありません。</span><span class="sxs-lookup"><span data-stu-id="d3666-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="d3666-119">この場合、`ppDefaultValue` の長さは、`pdwCPlusTypeFlag`によって指定された型から推論されます。</span><span class="sxs-lookup"><span data-stu-id="d3666-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="d3666-120">入出力プロパティの set アクセサーメソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="d3666-121">入出力プロパティの get アクセサーメソッドを表す MethodDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d3666-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="d3666-122">入出力プロパティに関連付けられている他のメソッドを表す MethodDef トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="d3666-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d3666-123">[in] `rmdOtherMethod` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="d3666-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="d3666-124">すべてのメソッドを保持するのに十分な大きさの配列を指定しなかった場合、警告なしにスキップされます。</span><span class="sxs-lookup"><span data-stu-id="d3666-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="d3666-125">入出力`rmdOtherMethod`で返される MethodDef トークンの数。</span><span class="sxs-lookup"><span data-stu-id="d3666-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3666-126">要件</span><span class="sxs-lookup"><span data-stu-id="d3666-126">Requirements</span></span>  
 <span data-ttu-id="d3666-127">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3666-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3666-128">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="d3666-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3666-129">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="d3666-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3666-130">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3666-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3666-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="d3666-131">See also</span></span>

- [<span data-ttu-id="d3666-132">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3666-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d3666-133">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d3666-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
