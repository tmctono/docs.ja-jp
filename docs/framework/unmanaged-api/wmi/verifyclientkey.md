---
title: VerifyClientKey 関数 (アンマネージ API リファレンス)
description: VerifyClientKey 関数により、クライアント キーが適切なセキュリティ。
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
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782487"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="59741-103">VerifyClientKey 関数</span><span class="sxs-lookup"><span data-stu-id="59741-103">VerifyClientKey function</span></span>
<span data-ttu-id="59741-104">クライアント キーに適切なセキュリティが確実に含められます。</span><span class="sxs-lookup"><span data-stu-id="59741-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="59741-105">構文</span><span class="sxs-lookup"><span data-stu-id="59741-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="59741-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="59741-106">Return value</span></span>

<span data-ttu-id="59741-107">関数が成功した場合、戻り値は`ERROR_SUCCESS`(0)。</span><span class="sxs-lookup"><span data-stu-id="59741-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="59741-108">戻り値で定義されたゼロ以外のエラー コードは、関数が失敗した場合、 *WinError.h*します。</span><span class="sxs-lookup"><span data-stu-id="59741-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="59741-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="59741-109">Requirements</span></span>  
 <span data-ttu-id="59741-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="59741-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59741-111">**ヘッダー:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="59741-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="59741-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="59741-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59741-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="59741-113">See also</span></span>

- [<span data-ttu-id="59741-114">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="59741-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
