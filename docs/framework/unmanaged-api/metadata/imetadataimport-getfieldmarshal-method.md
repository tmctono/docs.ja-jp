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
ms.openlocfilehash: a031cdb875b5eb046428d4d235d3093caddb7a6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491291"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="12e85-102">IMetaDataImport::GetFieldMarshal メソッド</span><span class="sxs-lookup"><span data-stu-id="12e85-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="12e85-103">指定されたフィールドメタデータトークンによって表されるフィールドの、ネイティブなアンマネージ型へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="12e85-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12e85-104">構文</span><span class="sxs-lookup"><span data-stu-id="12e85-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12e85-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="12e85-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="12e85-106">から相互運用マーシャリング情報を取得するフィールドを表すメタデータトークン。</span><span class="sxs-lookup"><span data-stu-id="12e85-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="12e85-107">入出力フィールドのネイティブ型のメタデータシグネチャへのポインター。</span><span class="sxs-lookup"><span data-stu-id="12e85-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="12e85-108">入出力のサイズ (バイト単位) `ppvNativeType` 。</span><span class="sxs-lookup"><span data-stu-id="12e85-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12e85-109">要件</span><span class="sxs-lookup"><span data-stu-id="12e85-109">Requirements</span></span>  
 <span data-ttu-id="12e85-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12e85-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12e85-111">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="12e85-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12e85-112">**ライブラリ:** Mscoree.dll にリソースとして含まれています</span><span class="sxs-lookup"><span data-stu-id="12e85-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12e85-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12e85-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12e85-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="12e85-114">See also</span></span>

- [<span data-ttu-id="12e85-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12e85-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="12e85-116">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="12e85-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
