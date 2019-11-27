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
ms.openlocfilehash: 2d3c820975488fa722e7af6070611ba7e9686ce8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445446"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="76540-102">IMetaDataEmit::SetModuleProps メソッド</span><span class="sxs-lookup"><span data-stu-id="76540-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="76540-103">[IMetaDataEmit::D efinemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)の前の呼び出しで定義されているモジュールへの参照を更新します。</span><span class="sxs-lookup"><span data-stu-id="76540-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76540-104">構文</span><span class="sxs-lookup"><span data-stu-id="76540-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76540-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="76540-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="76540-106">からUnicode のモジュール名。</span><span class="sxs-lookup"><span data-stu-id="76540-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="76540-107">これはファイル名のみで、完全なパス名ではありません。</span><span class="sxs-lookup"><span data-stu-id="76540-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76540-108">要件</span><span class="sxs-lookup"><span data-stu-id="76540-108">Requirements</span></span>  
 <span data-ttu-id="76540-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76540-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76540-110">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="76540-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76540-111">**ライブラリ:** Mscoree.dll のリソースとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="76540-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76540-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76540-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76540-113">参照</span><span class="sxs-lookup"><span data-stu-id="76540-113">See also</span></span>

- [<span data-ttu-id="76540-114">IMetaDataEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76540-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="76540-115">IMetaDataEmit2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="76540-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
