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
ms.openlocfilehash: 380181d8e309ba4b51d49aae9159f0bbf7e0250f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796725"
---
# <a name="iassemblycacheitemcommit-method"></a><span data-ttu-id="59329-102">IAssemblyCacheItem::Commit メソッド</span><span class="sxs-lookup"><span data-stu-id="59329-102">IAssemblyCacheItem::Commit Method</span></span>
<span data-ttu-id="59329-103">キャッシュされたアセンブリ参照をメモリにコミットします。</span><span class="sxs-lookup"><span data-stu-id="59329-103">Commits the cached assembly reference to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59329-104">構文</span><span class="sxs-lookup"><span data-stu-id="59329-104">Syntax</span></span>  
  
```cpp  
HRESULT Commit (  
    [in] DWORD dwFlags,   
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59329-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59329-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="59329-106">からFusion に定義されているフラグ。</span><span class="sxs-lookup"><span data-stu-id="59329-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="59329-107">[out、省略可能]操作の結果を示す値です。</span><span class="sxs-lookup"><span data-stu-id="59329-107">[out, optional] A value that indicates the result of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59329-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="59329-108">Requirements</span></span>  
 <span data-ttu-id="59329-109">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59329-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59329-110">**ヘッダー:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="59329-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="59329-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59329-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59329-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="59329-112">See also</span></span>

- [<span data-ttu-id="59329-113">IAssemblyCacheItem インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59329-113">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
