---
title: CoUninitializeEE 関数
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05bc472711838236ed18b00ce808d022d9581dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758205"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="08120-102">CoUninitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="08120-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="08120-103">`CoUninitializeEE` 廃止され、機能はありません。</span><span class="sxs-lookup"><span data-stu-id="08120-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08120-104">構文</span><span class="sxs-lookup"><span data-stu-id="08120-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="08120-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="08120-105">Remarks</span></span>  
 <span data-ttu-id="08120-106">共通言語ランタイムの実行エンジンは、プロセスからアンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="08120-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="08120-107">実行エンジンの呼び出しをシャット ダウン[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)します。</span><span class="sxs-lookup"><span data-stu-id="08120-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08120-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="08120-108">See also</span></span>

- [<span data-ttu-id="08120-109">CoInitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="08120-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="08120-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="08120-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
