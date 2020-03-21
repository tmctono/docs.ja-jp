---
title: IMetaDataEmit::DefineModuleRef メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177734"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="fa2ae-102">IMetaDataEmit::DefineModuleRef メソッド</span><span class="sxs-lookup"><span data-stu-id="fa2ae-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="fa2ae-103">指定した名前のモジュールのメタデータ シグネチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2ae-104">構文</span><span class="sxs-lookup"><span data-stu-id="fa2ae-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa2ae-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fa2ae-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fa2ae-106">[in]他のメタデータ ファイルの名前 (通常は DLL)。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="fa2ae-107">これはファイル名のみです。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-107">This is the file name only.</span></span> <span data-ttu-id="fa2ae-108">フル パス名は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="fa2ae-109">[アウト]割り`mdModuleRef`当てられたトークン。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2ae-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="fa2ae-110">Requirements</span></span>  
 <span data-ttu-id="fa2ae-111">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2ae-112">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="fa2ae-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa2ae-113">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="fa2ae-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa2ae-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2ae-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2ae-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fa2ae-115">See also</span></span>

- [<span data-ttu-id="fa2ae-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa2ae-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="fa2ae-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fa2ae-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
