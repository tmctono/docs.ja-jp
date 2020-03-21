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
ms.openlocfilehash: 8c3f98a124dbbcae3b0500932a2357ed1757951f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177244"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="8b2d6-102">IMetaDataImport::GetFieldProps メソッド</span><span class="sxs-lookup"><span data-stu-id="8b2d6-102">IMetaDataImport::GetFieldProps Method</span></span>
<span data-ttu-id="8b2d6-103">指定した FieldDef トークンによって参照されるフィールドに関連付けられているメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2d6-104">構文</span><span class="sxs-lookup"><span data-stu-id="8b2d6-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="8b2d6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b2d6-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="8b2d6-106">[in]関連付けられたメタデータを取得するフィールドを表す FieldDef トークン。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="8b2d6-107">[アウト]フィールドが属するクラスの型を表す TypeDef トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="8b2d6-108">[アウト]フィールドの名前。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="8b2d6-109">[in]*szField*のバッファーのワイド文字でのサイズ。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="8b2d6-110">[アウト]返されるバッファーの実際のサイズ。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="8b2d6-111">[アウト]フィールドのメタデータに関連付けられたフラグ。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="8b2d6-112">[in]フィールドを記述するバイナリ メタデータ値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="8b2d6-113">[アウト]のサイズ (バイト`ppvSigBlob`単位)</span><span class="sxs-lookup"><span data-stu-id="8b2d6-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="8b2d6-114">[アウト]フィールドの値の型を指定するフラグ。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="8b2d6-115">[アウト]フィールドの定数値。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="8b2d6-116">[アウト]の文字`ppValue`で表されるサイズ。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2d6-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8b2d6-117">Requirements</span></span>  
 <span data-ttu-id="8b2d6-118">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b2d6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2d6-119">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="8b2d6-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b2d6-120">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="8b2d6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b2d6-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2d6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2d6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b2d6-122">See also</span></span>

- [<span data-ttu-id="8b2d6-123">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b2d6-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8b2d6-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8b2d6-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
