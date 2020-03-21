---
title: クライアントキー関数の確認 (アンマネージ API リファレンス)
description: 検証クライアントキー機能は、クライアントキーに正しいセキュリティを保証します。
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176709"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="ea797-103">クライアントキー機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="ea797-103">VerifyClientKey function</span></span>
<span data-ttu-id="ea797-104">クライアント キーに適切なセキュリティが確実に含められます。</span><span class="sxs-lookup"><span data-stu-id="ea797-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ea797-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea797-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="ea797-106">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea797-106">Return value</span></span>

<span data-ttu-id="ea797-107">関数が成功した場合、戻り値は`ERROR_SUCCESS`(0) になります。</span><span class="sxs-lookup"><span data-stu-id="ea797-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="ea797-108">関数が失敗した場合、戻り値は*WinError.h*で定義された 0 以外のエラー コードです。</span><span class="sxs-lookup"><span data-stu-id="ea797-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea797-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="ea797-109">Requirements</span></span>  
 <span data-ttu-id="ea797-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea797-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea797-111">**ヘッダー:** WMINet_Utilsデフ</span><span class="sxs-lookup"><span data-stu-id="ea797-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="ea797-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea797-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea797-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea797-113">See also</span></span>

- [<span data-ttu-id="ea797-114">WMI およびパフォーマンス カウンター (アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="ea797-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
