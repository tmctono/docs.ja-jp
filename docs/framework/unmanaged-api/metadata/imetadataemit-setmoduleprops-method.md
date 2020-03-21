---
title: IMetaDataEmit::SetModuleProps メソッド
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 69c3ee366dbb8505e0df744037c480da996bb836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175617"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="e6d3a-102">IMetaDataEmit::SetModuleProps メソッド</span><span class="sxs-lookup"><span data-stu-id="e6d3a-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="e6d3a-103">以前の呼び出しで定義されたモジュール[:D](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)への参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d3a-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6d3a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d3a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6d3a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="e6d3a-106">[in]ユニコードのモジュール名。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="e6d3a-107">これはファイル名のみであり、フルパス名ではありません。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d3a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6d3a-108">Requirements</span></span>  
 <span data-ttu-id="e6d3a-109">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d3a-110">**ヘッダー:** コル・h</span><span class="sxs-lookup"><span data-stu-id="e6d3a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6d3a-111">**ライブラリ:** MSCorEE.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6d3a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d3a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d3a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d3a-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6d3a-113">See also</span></span>

- [<span data-ttu-id="e6d3a-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6d3a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e6d3a-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e6d3a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
