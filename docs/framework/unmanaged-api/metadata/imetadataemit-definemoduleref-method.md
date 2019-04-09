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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59128818"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="d23e1-102">IMetaDataEmit::DefineModuleRef メソッド</span><span class="sxs-lookup"><span data-stu-id="d23e1-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="d23e1-103">指定した名前のモジュールのメタデータ署名を作成します。</span><span class="sxs-lookup"><span data-stu-id="d23e1-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23e1-104">構文</span><span class="sxs-lookup"><span data-stu-id="d23e1-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d23e1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d23e1-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d23e1-106">[in]その他のメタデータ ファイル、DLL では通常の名前。</span><span class="sxs-lookup"><span data-stu-id="d23e1-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="d23e1-107">これは、ファイル名のみです。</span><span class="sxs-lookup"><span data-stu-id="d23e1-107">This is the file name only.</span></span> <span data-ttu-id="d23e1-108">完全なパス名を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="d23e1-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="d23e1-109">[out]割り当てられている`mdModuleRef`トークンです。</span><span class="sxs-lookup"><span data-stu-id="d23e1-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23e1-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="d23e1-110">Requirements</span></span>  
 <span data-ttu-id="d23e1-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d23e1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23e1-112">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d23e1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d23e1-113">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="d23e1-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d23e1-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d23e1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d23e1-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d23e1-115">See also</span></span>

- [<span data-ttu-id="d23e1-116">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d23e1-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d23e1-117">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="d23e1-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
