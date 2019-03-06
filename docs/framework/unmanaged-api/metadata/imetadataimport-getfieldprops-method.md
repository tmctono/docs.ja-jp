---
title: IMetaDataImport::GetFieldProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1064300d8bb3a9b03e1dfad1c30596c35ee1c941
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485201"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="9eb51-102">IMetaDataImport::GetFieldProps メソッド</span><span class="sxs-lookup"><span data-stu-id="9eb51-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="9eb51-103">指定した FieldDef トークンによって参照されるフィールドに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="9eb51-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eb51-104">構文</span><span class="sxs-lookup"><span data-stu-id="9eb51-104">Syntax</span></span>  
  
```  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,   
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,   
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pcbSigBlob,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eb51-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9eb51-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="9eb51-106">[in]関連付けられているメタデータを取得するフィールドを表す FieldDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="9eb51-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="9eb51-107">[out]フィールドが属するクラスの型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="9eb51-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="9eb51-108">[out]フィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="9eb51-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="9eb51-109">[in]サイズのバッファーのワイド文字単位*szField*します。</span><span class="sxs-lookup"><span data-stu-id="9eb51-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="9eb51-110">[out]返されたバッファーの実際のサイズ。</span><span class="sxs-lookup"><span data-stu-id="9eb51-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="9eb51-111">[out]フィールドのメタデータに関連付けられたフラグ。</span><span class="sxs-lookup"><span data-stu-id="9eb51-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="9eb51-112">[in]フィールドを説明するメタデータのバイナリ値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9eb51-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="9eb51-113">[out]バイト サイズ`ppvSigBlob`します。</span><span class="sxs-lookup"><span data-stu-id="9eb51-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="9eb51-114">[out]フィールドの値の型を指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="9eb51-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="9eb51-115">[out]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="9eb51-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="9eb51-116">[out]サイズの文字で`ppValue`、または 0 の文字列が存在しない場合。</span><span class="sxs-lookup"><span data-stu-id="9eb51-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9eb51-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="9eb51-117">Requirements</span></span>  
 <span data-ttu-id="9eb51-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9eb51-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eb51-119">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9eb51-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9eb51-120">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="9eb51-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9eb51-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eb51-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eb51-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="9eb51-122">See also</span></span>
- [<span data-ttu-id="9eb51-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9eb51-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9eb51-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9eb51-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
