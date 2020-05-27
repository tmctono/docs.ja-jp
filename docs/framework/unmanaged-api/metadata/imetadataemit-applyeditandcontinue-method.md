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
ms.openlocfilehash: 7ce9ac95c7183a7d47c367914d80f77c57dde0d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005766"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="abed9-102">IMetaDataEmit::ApplyEditAndContinue メソッド</span><span class="sxs-lookup"><span data-stu-id="abed9-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="abed9-103">指定したメタデータに加えられた変更を使用して、現在のアセンブリスコープを更新します。</span><span class="sxs-lookup"><span data-stu-id="abed9-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abed9-104">構文</span><span class="sxs-lookup"><span data-stu-id="abed9-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abed9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abed9-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="abed9-106">\[\]ポータブル実行可能 (PE) ファイルからのデルタメタデータを表す[IUnknown](/cpp/atl/iunknown)オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="abed9-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="abed9-107">差分メタデータは、モジュールの実際のメタデータのコピーに加えられた変更を含むメタデータのブロックです。</span><span class="sxs-lookup"><span data-stu-id="abed9-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abed9-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="abed9-108">Requirements</span></span>  
 <span data-ttu-id="abed9-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abed9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abed9-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="abed9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="abed9-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="abed9-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abed9-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abed9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abed9-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="abed9-113">See also</span></span>

- [<span data-ttu-id="abed9-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abed9-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="abed9-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abed9-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
