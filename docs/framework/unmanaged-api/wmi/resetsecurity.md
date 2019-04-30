---
title: ResetSecurity 関数 (アンマネージ API リファレンス)
description: ResetSecurity 関数では、現在のスレッドに偽装トークンが割り当てられます。
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e937690c184d810549e8ab11ef1fc2273a45c5f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049246"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="dca62-103">ResetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="dca62-103">ResetSecurity function</span></span>
<span data-ttu-id="dca62-104">指定した偽装トークンが現在のスレッドに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="dca62-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="dca62-105">構文</span><span class="sxs-lookup"><span data-stu-id="dca62-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="dca62-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dca62-106">Parameters</span></span>

`token`  
<span data-ttu-id="dca62-107">[in]現在のスレッドに関連付ける権限借用トークンです。</span><span class="sxs-lookup"><span data-stu-id="dca62-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="dca62-108">この値は `null` の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="dca62-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="dca62-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dca62-109">Return value</span></span>

<span data-ttu-id="dca62-110">関数が成功した場合、戻り値は`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="dca62-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="dca62-111">関数が失敗した場合、戻り値が 0 以外のエラー コードにします。</span><span class="sxs-lookup"><span data-stu-id="dca62-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="dca62-112">拡張エラー情報を取得する、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="dca62-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="dca62-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="dca62-113">Requirements</span></span>  
 <span data-ttu-id="dca62-114">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dca62-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca62-115">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="dca62-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="dca62-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dca62-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dca62-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="dca62-117">See also</span></span>

- [<span data-ttu-id="dca62-118">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dca62-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
