---
title: IMetaDataEmit::ApplyEditAndContinue メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05de7d45c53d8aeaafaa06ae351050cc8bca3622
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777692"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="8ebd0-102">IMetaDataEmit::ApplyEditAndContinue メソッド</span><span class="sxs-lookup"><span data-stu-id="8ebd0-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="8ebd0-103">指定したメタデータで行われた変更では、現在のアセンブリのスコープを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ebd0-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ebd0-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ebd0-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ebd0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ebd0-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="8ebd0-106">\[\]へのポインター、 [IUnknown](/cpp/atl/iunknown)ポータブル実行可能 (PE) ファイルからデルタ メタデータを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="8ebd0-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="8ebd0-107">デルタのメタデータは、モジュールの実際のメタデータのコピーに加えられた変更を含むメタデータのブロックです。</span><span class="sxs-lookup"><span data-stu-id="8ebd0-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ebd0-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ebd0-108">Requirements</span></span>  
 <span data-ttu-id="8ebd0-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ebd0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ebd0-110">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8ebd0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ebd0-111">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="8ebd0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ebd0-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ebd0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebd0-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ebd0-113">See also</span></span>

- [<span data-ttu-id="8ebd0-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ebd0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8ebd0-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8ebd0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
