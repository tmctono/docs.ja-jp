---
title: VerifyClientKey 関数 (アンマネージ API リファレンス)
description: VerifyClientKey 関数によって、クライアントキーのセキュリティが適切であることが確認されます。
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107357"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="6a43b-103">VerifyClientKey 関数</span><span class="sxs-lookup"><span data-stu-id="6a43b-103">VerifyClientKey function</span></span>
<span data-ttu-id="6a43b-104">クライアント キーに適切なセキュリティが確実に含められます。</span><span class="sxs-lookup"><span data-stu-id="6a43b-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="6a43b-105">構文</span><span class="sxs-lookup"><span data-stu-id="6a43b-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="6a43b-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="6a43b-106">Return value</span></span>

<span data-ttu-id="6a43b-107">関数が成功した場合、戻り値は `ERROR_SUCCESS` (0) になります。</span><span class="sxs-lookup"><span data-stu-id="6a43b-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="6a43b-108">関数が失敗した場合、戻り値は、 *winerror.h*で定義されている0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="6a43b-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="6a43b-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="6a43b-109">Requirements</span></span>  
 <span data-ttu-id="6a43b-110">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a43b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a43b-111">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="6a43b-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="6a43b-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6a43b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a43b-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6a43b-113">See also</span></span>

- [<span data-ttu-id="6a43b-114">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6a43b-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
