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
ms.openlocfilehash: f876187624d066b9e672fbf44a984d6d02a54c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175877"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="71628-102">IMetaDataEmit::ApplyEditAndContinue メソッド</span><span class="sxs-lookup"><span data-stu-id="71628-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="71628-103">指定したメタデータに加えられた変更を使用して、現在のアセンブリ スコープを更新します。</span><span class="sxs-lookup"><span data-stu-id="71628-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71628-104">構文</span><span class="sxs-lookup"><span data-stu-id="71628-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71628-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71628-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="71628-106">\[移植\]可能な実行可能 (PE) ファイルからのデルタ メタデータを表す[IUnknown](/cpp/atl/iunknown)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="71628-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="71628-107">デルタ メタデータは、モジュールの実際のメタデータのコピーに加えられた変更を含むメタデータのブロックです。</span><span class="sxs-lookup"><span data-stu-id="71628-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71628-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="71628-108">Requirements</span></span>  
 <span data-ttu-id="71628-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71628-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71628-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="71628-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71628-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="71628-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71628-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71628-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71628-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="71628-113">See also</span></span>

- [<span data-ttu-id="71628-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71628-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="71628-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71628-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
