---
title: IMetaDataImport::GetFieldMarshal メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b3c9b879faf49ec7a485641c622d40a684dfb35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469301"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="2f934-102">IMetaDataImport::GetFieldMarshal メソッド</span><span class="sxs-lookup"><span data-stu-id="2f934-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="2f934-103">指定したフィールドのメタデータ トークンによって表されるフィールドのネイティブなアンマネージ型へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f934-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f934-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f934-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f934-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f934-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2f934-106">[in]相互運用マーシャ リング情報を取得するフィールドを表すメタデータ トークンです。</span><span class="sxs-lookup"><span data-stu-id="2f934-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="2f934-107">[out]フィールドのネイティブ型のメタデータ署名へのポインター。</span><span class="sxs-lookup"><span data-stu-id="2f934-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="2f934-108">[out]バイト サイズ`ppvNativeType`します。</span><span class="sxs-lookup"><span data-stu-id="2f934-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f934-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f934-109">Requirements</span></span>  
 <span data-ttu-id="2f934-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f934-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f934-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f934-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f934-112">**ライブラリ:** MsCorEE.dll でリソースとして含まれます</span><span class="sxs-lookup"><span data-stu-id="2f934-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f934-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f934-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f934-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f934-114">See also</span></span>
- [<span data-ttu-id="2f934-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f934-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2f934-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2f934-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
