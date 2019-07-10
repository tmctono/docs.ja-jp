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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b2b7b89c73b59f4f735369659daabb6a8f88300
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779101"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="d460a-102">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="d460a-102">CoInitializeCor Function</span></span>
<span data-ttu-id="d460a-103">`CoInitializeCor` は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="d460a-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d460a-104">構文</span><span class="sxs-lookup"><span data-stu-id="d460a-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d460a-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="d460a-105">Remarks</span></span>  
 <span data-ttu-id="d460a-106">共通言語ランタイムを初期化するためにいずれかの操作を使用して[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)または[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="d460a-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d460a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="d460a-107">Requirements</span></span>  
 <span data-ttu-id="d460a-108">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d460a-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d460a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d460a-109">See also</span></span>

- [<span data-ttu-id="d460a-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="d460a-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
