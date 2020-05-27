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
ms.openlocfilehash: efff491d92ac7910f43f76965ef98d1d0e4ba0aa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004440"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="2961c-102">IMetaDataEmit::DefineModuleRef メソッド</span><span class="sxs-lookup"><span data-stu-id="2961c-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="2961c-103">指定された名前を持つモジュールのメタデータシグネチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="2961c-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2961c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2961c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2961c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2961c-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="2961c-106">から他のメタデータファイルの名前 (通常は DLL)。</span><span class="sxs-lookup"><span data-stu-id="2961c-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="2961c-107">これはファイル名のみです。</span><span class="sxs-lookup"><span data-stu-id="2961c-107">This is the file name only.</span></span> <span data-ttu-id="2961c-108">完全なパス名は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2961c-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="2961c-109">入出力割り当てられた `mdModuleRef` トークン。</span><span class="sxs-lookup"><span data-stu-id="2961c-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2961c-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="2961c-110">Requirements</span></span>  
 <span data-ttu-id="2961c-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2961c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2961c-112">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="2961c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2961c-113">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2961c-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2961c-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2961c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2961c-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="2961c-115">See also</span></span>

- [<span data-ttu-id="2961c-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2961c-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2961c-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2961c-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
