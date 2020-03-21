---
title: IMetaDataImport::GetMemberProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: 72e14ea0414ebdeb8f54a4bdef8ce5208fc8ef72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177230"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="25192-102">IMetaDataImport::GetMemberProps メソッド</span><span class="sxs-lookup"><span data-stu-id="25192-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="25192-103">指定したメタデータ トークンによって参照されるメンバーの名前、バイナリ シグネチャ、相対仮想アドレスなど、指定した<xref:System.Type>メンバー定義のメタデータに格納されている情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="25192-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="25192-104">これは単純なヘルパー メソッドです: *mb*がメソッド定義の場合は **、GetMethodProps**が呼び出されます。*mb*がフィールド定義の場合は **、GetFieldProps が**呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="25192-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="25192-105">詳細については、他の方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25192-105">See these other methods for details.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="25192-106">構文</span><span class="sxs-lookup"><span data-stu-id="25192-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25192-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25192-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="25192-108">[in]関連付けられたメタデータを取得するメンバーを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="25192-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="25192-109">[アウト]メンバーのクラスを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25192-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="25192-110">[アウト]メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="25192-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="25192-111">[in]バッファーのワイド文字で示される`szMember`サイズ。</span><span class="sxs-lookup"><span data-stu-id="25192-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="25192-112">[アウト]返された名前のワイド文字で示されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="25192-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="25192-113">[アウト]メンバーに適用されるフラグ値。</span><span class="sxs-lookup"><span data-stu-id="25192-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="25192-114">[アウト]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25192-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="25192-115">[アウト]のサイズ (バイト`ppvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="25192-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="25192-116">[アウト]メンバーの相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25192-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="25192-117">[アウト]メンバーに関連付けられたメソッド実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="25192-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="25192-118">[アウト]をマークするフラグ。 <xref:System.ValueType></span><span class="sxs-lookup"><span data-stu-id="25192-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="25192-119">これは値の`ELEMENT_TYPE_*`1 つです。</span><span class="sxs-lookup"><span data-stu-id="25192-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="25192-120">[アウト]このメンバーによって返される定数文字列値。</span><span class="sxs-lookup"><span data-stu-id="25192-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="25192-121">[アウト]のサイズを文字`ppValue`で指定`ppValue`します。</span><span class="sxs-lookup"><span data-stu-id="25192-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25192-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="25192-122">Requirements</span></span>  
 <span data-ttu-id="25192-123">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25192-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25192-124">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="25192-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25192-125">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="25192-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="25192-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25192-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25192-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="25192-127">See also</span></span>

- [<span data-ttu-id="25192-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25192-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="25192-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="25192-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
