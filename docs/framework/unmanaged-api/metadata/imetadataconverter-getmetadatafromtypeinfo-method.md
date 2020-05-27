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
ms.openlocfilehash: f9f3e3f196f74a7dea3c722925f1d03968688882
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009003"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="6e71d-102">IMetaDataConverter::GetMetaDataFromTypeInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="6e71d-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="6e71d-103">指定したインスタンスによって参照されるタイプライブラリのメタデータシグネチャを表す[IMetaDataImport](imetadataimport-interface.md)インスタンスへのポインターを取得し `ITypeInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="6e71d-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e71d-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e71d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e71d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e71d-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="6e71d-106">から`ITypeInfo`タイプライブラリを参照するオブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="6e71d-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="6e71d-107">入出力メタデータシグネチャを表すインスタンスのアドレスを受け取る場所へのポインター `IMetaDataImport` 。</span><span class="sxs-lookup"><span data-stu-id="6e71d-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e71d-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="6e71d-108">Requirements</span></span>  
 <span data-ttu-id="6e71d-109">**プラットフォーム:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e71d-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e71d-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="6e71d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e71d-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e71d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e71d-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e71d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e71d-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e71d-113">See also</span></span>

- [<span data-ttu-id="6e71d-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e71d-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6e71d-115">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="6e71d-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
