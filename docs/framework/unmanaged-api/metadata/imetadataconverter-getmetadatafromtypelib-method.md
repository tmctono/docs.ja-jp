---
title: IMetaDataConverter::GetMetaDataFromTypeLib メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175955"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="62e7a-102">IMetaDataConverter::GetMetaDataFromTypeLib メソッド</span><span class="sxs-lookup"><span data-stu-id="62e7a-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="62e7a-103">指定したインスタンスによって表されるタイプ ライブラリのメタデータ シグネチャを表す[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インスタンスへのインターフェイス`ITypeLib`ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="62e7a-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62e7a-104">構文</span><span class="sxs-lookup"><span data-stu-id="62e7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="62e7a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="62e7a-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="62e7a-106">[in]タイプ ライブラリ`ITypeLib`を表すオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="62e7a-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="62e7a-107">[アウト]メタデータ シグネチャを表すインスタンスのアドレスを`IMetaDataImport`受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="62e7a-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e7a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="62e7a-108">Requirements</span></span>  
 <span data-ttu-id="62e7a-109">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62e7a-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62e7a-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="62e7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62e7a-111">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="62e7a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62e7a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62e7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e7a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="62e7a-113">See also</span></span>

- [<span data-ttu-id="62e7a-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62e7a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="62e7a-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="62e7a-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
