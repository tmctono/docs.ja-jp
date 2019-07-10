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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fcf32c4b27324ccc54eabbb248e8c9906cf693b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782359"
---
# <a name="imetadataimportgetmemberprops-method"></a><span data-ttu-id="a188b-102">IMetaDataImport::GetMemberProps メソッド</span><span class="sxs-lookup"><span data-stu-id="a188b-102">IMetaDataImport::GetMemberProps Method</span></span>
<span data-ttu-id="a188b-103">名前、バイナリ シグネチャ、および相対仮想アドレスを含む、指定したメンバーの定義のメタデータに格納されている情報の取得、<xref:System.Type>指定したメタデータ トークンによって参照されるメンバー。</span><span class="sxs-lookup"><span data-stu-id="a188b-103">Gets information stored in the metadata for a specified member definition, including the name, binary signature, and relative virtual address, of the <xref:System.Type> member referenced by the specified metadata token.</span></span> <span data-ttu-id="a188b-104">これは単純なヘルパー メソッド: 場合*mb*は、MethodDef **GetMethodProps**が呼び出されます場合*mb*は、の FieldDef **GetFieldProps** 。呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="a188b-104">This is a simple helper method: if *mb* is a MethodDef, then **GetMethodProps** is called; if *mb* is a FieldDef, then **GetFieldProps** is called.</span></span> <span data-ttu-id="a188b-105">他の方法の詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a188b-105">See these other methods for details.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="a188b-106">構文</span><span class="sxs-lookup"><span data-stu-id="a188b-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="a188b-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a188b-107">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="a188b-108">[in]関連付けられているメタデータを取得するメンバーを参照するトークンです。</span><span class="sxs-lookup"><span data-stu-id="a188b-108">[in] The token that references the member to get the associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a188b-109">[out]メンバーのクラスを表すメタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a188b-109">[out] A pointer to the metadata token that represents the class of the member.</span></span>  
  
 `szMember`  
 <span data-ttu-id="a188b-110">[out]メンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="a188b-110">[out] The name of the member.</span></span>  
  
 `cchMember`  
 <span data-ttu-id="a188b-111">[in]ワイド文字のサイズ、`szMember`バッファー。</span><span class="sxs-lookup"><span data-stu-id="a188b-111">[in] The size in wide characters of the `szMember` buffer.</span></span>  
  
 `pchMember`  
 <span data-ttu-id="a188b-112">[out]返される名前のワイド文字単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="a188b-112">[out] The size in wide characters of the returned name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="a188b-113">[out]いずれかのフラグ値がメンバーに適用します。</span><span class="sxs-lookup"><span data-stu-id="a188b-113">[out] Any flag values applied to the member.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="a188b-114">[out]メンバーのバイナリ メタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a188b-114">[out] A pointer to the binary metadata signature of the member.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="a188b-115">[out]バイト サイズ`ppvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="a188b-115">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="a188b-116">[out]メンバーの相対仮想アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a188b-116">[out] A pointer to the relative virtual address of the member.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="a188b-117">[out]メンバーに関連付けられているすべてメソッド実装フラグ。</span><span class="sxs-lookup"><span data-stu-id="a188b-117">[out] Any method implementation flags associated with the member.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="a188b-118">[out]マークするフラグを<xref:System.ValueType>します。</span><span class="sxs-lookup"><span data-stu-id="a188b-118">[out] A flag that marks a <xref:System.ValueType>.</span></span> <span data-ttu-id="a188b-119">1 つは、`ELEMENT_TYPE_*`値。</span><span class="sxs-lookup"><span data-stu-id="a188b-119">It is one of the `ELEMENT_TYPE_*` values.</span></span>
  
 `ppValue`  
 <span data-ttu-id="a188b-120">[out]このメンバーが返される定数文字列値。</span><span class="sxs-lookup"><span data-stu-id="a188b-120">[out] A constant string value returned by this member.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="a188b-121">[out]サイズの文字で`ppValue`、または場合は 0`ppValue`文字列を保持しません。</span><span class="sxs-lookup"><span data-stu-id="a188b-121">[out] The size in characters of `ppValue`, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a188b-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="a188b-122">Requirements</span></span>  
 <span data-ttu-id="a188b-123">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a188b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a188b-124">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a188b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a188b-125">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="a188b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a188b-126">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a188b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a188b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="a188b-127">See also</span></span>

- [<span data-ttu-id="a188b-128">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a188b-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a188b-129">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a188b-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
