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
ms.openlocfilehash: f840438e175790a2b4c97302963b910f98dffb7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176566"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="47d89-102">IAssemblyCacheItem::Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="47d89-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="47d89-103">キャッシュされたアセンブリ参照をメモリにコミットします。</span><span class="sxs-lookup"><span data-stu-id="47d89-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d89-104">構文</span><span class="sxs-lookup"><span data-stu-id="47d89-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47d89-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47d89-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="47d89-106">[in]Fusion.idl で定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="47d89-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="47d89-107">[アウト、オプション]操作の結果を示す値。</span><span class="sxs-lookup"><span data-stu-id="47d89-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47d89-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="47d89-108">Requirements</span></span>  
 <span data-ttu-id="47d89-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47d89-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47d89-110">**ヘッダー:** フュージョン.h</span><span class="sxs-lookup"><span data-stu-id="47d89-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="47d89-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47d89-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47d89-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="47d89-112">See also</span></span>

- [<span data-ttu-id="47d89-113">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="47d89-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
