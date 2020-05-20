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
ms.openlocfilehash: 188f98504fa73c4a85615a4e688bae02d966b9b6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616750"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="8134f-102">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="8134f-102">CoInitializeCor Function</span></span>
<span data-ttu-id="8134f-103">`CoInitializeCor` は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="8134f-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8134f-104">構文</span><span class="sxs-lookup"><span data-stu-id="8134f-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8134f-105">解説</span><span class="sxs-lookup"><span data-stu-id="8134f-105">Remarks</span></span>  
 <span data-ttu-id="8134f-106">共通言語ランタイムを初期化するには、 [Corbindtoruntimeex](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)または[Corbindtoの entruntime](corbindtocurrentruntime-function.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="8134f-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8134f-107">要件</span><span class="sxs-lookup"><span data-stu-id="8134f-107">Requirements</span></span>  
 <span data-ttu-id="8134f-108">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="8134f-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8134f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="8134f-109">See also</span></span>

- [<span data-ttu-id="8134f-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="8134f-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
