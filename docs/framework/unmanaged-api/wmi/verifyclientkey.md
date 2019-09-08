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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798189"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="e1a21-103">VerifyClientKey 関数</span><span class="sxs-lookup"><span data-stu-id="e1a21-103">VerifyClientKey function</span></span>
<span data-ttu-id="e1a21-104">クライアント キーに適切なセキュリティが確実に含められます。</span><span class="sxs-lookup"><span data-stu-id="e1a21-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e1a21-105">構文</span><span class="sxs-lookup"><span data-stu-id="e1a21-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="e1a21-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="e1a21-106">Return value</span></span>

<span data-ttu-id="e1a21-107">関数が成功した場合、戻り値`ERROR_SUCCESS`は (0) になります。</span><span class="sxs-lookup"><span data-stu-id="e1a21-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="e1a21-108">関数が失敗した場合、戻り値は、 *winerror.h*で定義されている0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="e1a21-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1a21-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="e1a21-109">Requirements</span></span>  
 <span data-ttu-id="e1a21-110">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1a21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a21-111">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="e1a21-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="e1a21-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a21-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1a21-113">See also</span></span>

- [<span data-ttu-id="e1a21-114">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="e1a21-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
