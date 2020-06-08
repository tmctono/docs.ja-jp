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
ms.openlocfilehash: 1263467fc5db92d4dd21c4f09a98af309e2c4d55
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504421"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="fcd5a-102">CoInitializeCor 関数</span><span class="sxs-lookup"><span data-stu-id="fcd5a-102">CoInitializeCor Function</span></span>
<span data-ttu-id="fcd5a-103">`CoInitializeCor` は互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="fcd5a-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcd5a-104">構文</span><span class="sxs-lookup"><span data-stu-id="fcd5a-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="fcd5a-105">解説</span><span class="sxs-lookup"><span data-stu-id="fcd5a-105">Remarks</span></span>  
 <span data-ttu-id="fcd5a-106">共通言語ランタイムを初期化するには、 [Corbindtoruntimeex](corbindtoruntimeex-function.md)または[Corbindtoの entruntime](corbindtocurrentruntime-function.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcd5a-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcd5a-107">要件</span><span class="sxs-lookup"><span data-stu-id="fcd5a-107">Requirements</span></span>  
 <span data-ttu-id="fcd5a-108">**ヘッダー:** Cor</span><span class="sxs-lookup"><span data-stu-id="fcd5a-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcd5a-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcd5a-109">See also</span></span>

- [<span data-ttu-id="fcd5a-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="fcd5a-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
