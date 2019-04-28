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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3757eee4c013ccf4f0f6d21ef64a92a5ffd70f19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697504"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="457fc-102">IAssemblyCacheItem::Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="457fc-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="457fc-103">メモリにキャッシュされたアセンブリ参照をコミットします。</span><span class="sxs-lookup"><span data-stu-id="457fc-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="457fc-104">Syntax</span></span>  
  
```  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="457fc-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="457fc-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="457fc-106">[in]ものがありますで定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="457fc-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="457fc-107">[out] 省略可能操作の結果を示す値。</span><span class="sxs-lookup"><span data-stu-id="457fc-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457fc-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="457fc-108">Requirements</span></span>  
 <span data-ttu-id="457fc-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="457fc-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457fc-110">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="457fc-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="457fc-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457fc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457fc-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="457fc-112">See also</span></span>

- [<span data-ttu-id="457fc-113">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="457fc-113">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
