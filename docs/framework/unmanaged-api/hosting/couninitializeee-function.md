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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616464"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="00429-102">CoUninitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="00429-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="00429-103">`CoUninitializeEE`は互換性のために残されており、機能を提供しません。</span><span class="sxs-lookup"><span data-stu-id="00429-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00429-104">構文</span><span class="sxs-lookup"><span data-stu-id="00429-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="00429-105">解説</span><span class="sxs-lookup"><span data-stu-id="00429-105">Remarks</span></span>  
 <span data-ttu-id="00429-106">共通言語ランタイムの実行エンジンをプロセスからアンロードできません。</span><span class="sxs-lookup"><span data-stu-id="00429-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="00429-107">実行エンジンをシャットダウンするには、 [CorExitProcess](corexitprocess-function.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00429-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00429-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="00429-108">See also</span></span>

- [<span data-ttu-id="00429-109">CoInitializeEE 関数</span><span class="sxs-lookup"><span data-stu-id="00429-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="00429-110">メタデータ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="00429-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
