---
title: CoInitializeCor 関数
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e8d65e739504e01a7d11b37d1b34d7313b13a5e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138332"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="46be2-102">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="46be2-102">CoInitializeCor Function</span></span>
<span data-ttu-id="46be2-103">`CoInitializeCor` は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="46be2-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46be2-104">構文</span><span class="sxs-lookup"><span data-stu-id="46be2-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="46be2-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="46be2-105">Remarks</span></span>  
 <span data-ttu-id="46be2-106">共通言語ランタイムを初期化するには、 [Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)または[Corbindtoの entruntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="46be2-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46be2-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="46be2-107">Requirements</span></span>  
 <span data-ttu-id="46be2-108">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="46be2-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46be2-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="46be2-109">See also</span></span>

- [<span data-ttu-id="46be2-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="46be2-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
