---
title: IAssemblyCacheItem::Commit メソッド
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.Commit
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::Commit
helpviewer_keywords:
- IAssemblyCacheItem::Commit method [.NET Framework fusion]
- Commit method, IAssemblyCacheItem interface [.NET Framework fusion]
ms.assetid: c2321f17-f46f-4815-ae41-b28678753613
topic_type:
- apiref
ms.openlocfilehash: 5de522c00da76e7c01369c706cb7f9e2bdad4b3b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134517"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="7668d-102">IAssemblyCacheItem::Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="7668d-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="7668d-103">キャッシュされたアセンブリ参照をメモリにコミットします。</span><span class="sxs-lookup"><span data-stu-id="7668d-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7668d-104">構文</span><span class="sxs-lookup"><span data-stu-id="7668d-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7668d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7668d-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="7668d-106">からFusion に定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="7668d-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="7668d-107">[out、省略可能]操作の結果を示す値です。</span><span class="sxs-lookup"><span data-stu-id="7668d-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7668d-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="7668d-108">Requirements</span></span>  
 <span data-ttu-id="7668d-109">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7668d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7668d-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7668d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7668d-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7668d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7668d-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="7668d-112">See also</span></span>

- [<span data-ttu-id="7668d-113">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7668d-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
