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
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175396"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="e336a-102">IMetaDataImport::GetFieldMarshal メソッド</span><span class="sxs-lookup"><span data-stu-id="e336a-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="e336a-103">指定したフィールド メタデータ トークンによって表されるフィールドのネイティブでアンマネージ型へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e336a-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e336a-104">構文</span><span class="sxs-lookup"><span data-stu-id="e336a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e336a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e336a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e336a-106">[in]相互運用マーシャリング情報を取得するフィールドを表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="e336a-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="e336a-107">[アウト]フィールドのネイティブ型のメタデータ シグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e336a-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="e336a-108">[アウト]のサイズ (バイト`ppvNativeType`単位)</span><span class="sxs-lookup"><span data-stu-id="e336a-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e336a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e336a-109">Requirements</span></span>  
 <span data-ttu-id="e336a-110">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e336a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e336a-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e336a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e336a-112">**ライブラリ:** MsCorEE.dll にリソースとして含まれる</span><span class="sxs-lookup"><span data-stu-id="e336a-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e336a-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e336a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e336a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="e336a-114">See also</span></span>

- [<span data-ttu-id="e336a-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e336a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e336a-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e336a-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
