---
title: IMetaDataConverter::GetMetaDataFromTypeInfo メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8619bf0e62752513b1ae03fa01d22be40f65e58e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468859"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="9b653-102">IMetaDataConverter::GetMetaDataFromTypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="9b653-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="9b653-103">ポインターを取得、 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)インスタンスを指定した参照されるタイプ ライブラリのメタデータ シグネチャを表す`ITypeInfo`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="9b653-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b653-104">構文</span><span class="sxs-lookup"><span data-stu-id="9b653-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b653-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9b653-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="9b653-106">[in]ポインター、`ITypeInfo`タイプ ライブラリを参照するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="9b653-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="9b653-107">[out]アドレスを受け取る場所へのポインター、`IMetaDataImport`メタデータ シグネチャを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="9b653-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b653-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="9b653-108">Requirements</span></span>  
 <span data-ttu-id="9b653-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b653-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b653-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b653-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b653-111">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9b653-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b653-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b653-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b653-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b653-113">See also</span></span>
- [<span data-ttu-id="9b653-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b653-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9b653-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9b653-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
