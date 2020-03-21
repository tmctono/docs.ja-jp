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
ms.openlocfilehash: ef573eb9a572c27e685289b2740a55e898be2093
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177634"
---
# <a name="imetadataconvertergettypelibfrommetadata-method"></a><span data-ttu-id="c53c6-102">IMetaDataConverter::GetTypeLibFromMetaData メソッド</span><span class="sxs-lookup"><span data-stu-id="c53c6-102">IMetaDataConverter::GetTypeLibFromMetaData Method</span></span>
<span data-ttu-id="c53c6-103">指定したライブラリ名と`ITypeLib`モジュール名を持つタイプ ライブラリを表すインスタンスへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c53c6-103">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified library and module names.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53c6-104">構文</span><span class="sxs-lookup"><span data-stu-id="c53c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibFromMetaData (  
    [in]  BSTR     strModule,
    [in]  BSTR     strTlbName,
    [out] ITypeLib **ppITL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c53c6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c53c6-105">Parameters</span></span>  
 `strModule`  
 <span data-ttu-id="c53c6-106">[in]タイプ ライブラリのモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="c53c6-106">[in] The name of the type library's module.</span></span>  
  
 `strTlbName`  
 <span data-ttu-id="c53c6-107">[in]タイプ ライブラリの名前。</span><span class="sxs-lookup"><span data-stu-id="c53c6-107">[in] The name of the type library.</span></span>  
  
 `ppITL`  
 <span data-ttu-id="c53c6-108">[アウト]タイプ ライブラリを表すインスタンスのアドレスを`ITypeLib`受け取る場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="c53c6-108">[out] A pointer to a location that receives the address of the `ITypeLib` instance that represents the type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53c6-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c53c6-109">Requirements</span></span>  
 <span data-ttu-id="c53c6-110">**プラットフォーム:**[「システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c53c6-110">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c53c6-111">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="c53c6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c53c6-112">**ライブラリ:** MsCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="c53c6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c53c6-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c53c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53c6-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="c53c6-114">See also</span></span>

- [<span data-ttu-id="c53c6-115">IMetaDataConverter インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c53c6-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)
