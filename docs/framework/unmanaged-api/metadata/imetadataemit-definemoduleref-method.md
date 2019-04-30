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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050130"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="9a74b-102">IMetaDataEmit::DefineModuleRef メソッド</span><span class="sxs-lookup"><span data-stu-id="9a74b-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="9a74b-103">指定した名前のモジュールのメタデータ署名を作成します。</span><span class="sxs-lookup"><span data-stu-id="9a74b-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a74b-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a74b-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a74b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a74b-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="9a74b-106">[in]その他のメタデータ ファイル、DLL では通常の名前。</span><span class="sxs-lookup"><span data-stu-id="9a74b-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="9a74b-107">これは、ファイル名のみです。</span><span class="sxs-lookup"><span data-stu-id="9a74b-107">This is the file name only.</span></span> <span data-ttu-id="9a74b-108">完全なパス名を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="9a74b-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="9a74b-109">[out]割り当てられている`mdModuleRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="9a74b-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a74b-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a74b-110">Requirements</span></span>  
 <span data-ttu-id="9a74b-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a74b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a74b-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a74b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a74b-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="9a74b-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a74b-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a74b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a74b-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a74b-115">See also</span></span>

- [<span data-ttu-id="9a74b-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a74b-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9a74b-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9a74b-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
