---
title: IMetaDataEmit::DeleteClassLayout メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84de8e3c688a23198762fca5219d317fabb69c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777458"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="259a5-102">IMetaDataEmit::DeleteClassLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="259a5-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="259a5-103">指定したトークンによって表される型のクラス レイアウト メタデータ シグネチャを破棄します。</span><span class="sxs-lookup"><span data-stu-id="259a5-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="259a5-104">構文</span><span class="sxs-lookup"><span data-stu-id="259a5-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="259a5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="259a5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="259a5-106">[in]`mdTypeDef`クラス レイアウトを削除する対象の型を表すメタデータ トークン。</span><span class="sxs-lookup"><span data-stu-id="259a5-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="259a5-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="259a5-107">Requirements</span></span>  
 <span data-ttu-id="259a5-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="259a5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="259a5-109">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="259a5-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="259a5-110">**ライブラリ:** MSCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="259a5-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="259a5-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="259a5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="259a5-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="259a5-112">See also</span></span>

- [<span data-ttu-id="259a5-113">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="259a5-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="259a5-114">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="259a5-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
