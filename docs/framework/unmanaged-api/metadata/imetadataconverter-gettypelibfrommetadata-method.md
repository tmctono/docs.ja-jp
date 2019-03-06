---
title: IMetaDataConverter::GetTypeLibFromMetaData メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetTypeLibFromMetaData
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetTypeLibFromMetaData
helpviewer_keywords:
- GetTypeLibFromMetaData method [.NET Framework metadata]
- IMetaDataConverter::GetTypeLibFromMetaData method [.NET Framework metadata]
ms.assetid: 90eab7b3-1fae-4af4-8bce-f7bc0e188a99
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ab1d39ddb53e08e6fd36016f544162e2b11edb0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472071"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="7b66d-102">IMetaDataConverter::GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="7b66d-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="7b66d-103">ポインターを取得、`ITypeLib`を指定したライブラリとモジュールの名前を持つタイプ ライブラリを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="7b66d-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b66d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7b66d-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b66d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7b66d-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="7b66d-106">[in]タイプ ライブラリのモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="7b66d-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="7b66d-107">[in]タイプ ライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="7b66d-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="7b66d-108">[out]アドレスを受け取る場所へのポインター、`ITypeLib`タイプ ライブラリを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="7b66d-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b66d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="7b66d-109">Requirements</span></span>  
 <span data-ttu-id="7b66d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b66d-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b66d-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b66d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b66d-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="7b66d-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b66d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b66d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b66d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b66d-114">See also</span></span>
- [<span data-ttu-id="7b66d-115">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7b66d-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
