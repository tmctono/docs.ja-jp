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
ms.openlocfilehash: c0943971dc4858e2dce4d977f6f906b26f8ad51e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59231014"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="50570-102">IMetaDataConverter::GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="50570-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="50570-103">ポインターを取得、`ITypeLib`を指定したライブラリとモジュールの名前を持つタイプ ライブラリを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="50570-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50570-104">構文</span><span class="sxs-lookup"><span data-stu-id="50570-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,   
    [in]  BSTR     strTlbName,   
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50570-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50570-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="50570-106">[in]タイプ ライブラリのモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="50570-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="50570-107">[in]タイプ ライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="50570-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="50570-108">[out]アドレスを受け取る場所へのポインター、`ITypeLib`タイプ ライブラリを表すインスタンス。</span><span class="sxs-lookup"><span data-stu-id="50570-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50570-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="50570-109">Requirements</span></span>  
 <span data-ttu-id="50570-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="50570-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50570-111">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50570-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50570-112">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="50570-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50570-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50570-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50570-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="50570-114">See also</span></span>

- [<span data-ttu-id="50570-115">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="50570-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
