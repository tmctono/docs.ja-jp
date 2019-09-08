---
title: ResetSecurity 関数 (アンマネージ API リファレンス)
description: ResetSecurity 関数は、現在のスレッドに偽装トークンを割り当てます。
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
ms.openlocfilehash: 1636d7de8273389e785131dbc1145affd5d3b45f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798256"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="263f4-103">ResetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="263f4-103">ResetSecurity function</span></span>
<span data-ttu-id="263f4-104">指定した偽装トークンが現在のスレッドに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="263f4-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="263f4-105">構文</span><span class="sxs-lookup"><span data-stu-id="263f4-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="263f4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="263f4-106">Parameters</span></span>

`token`  
<span data-ttu-id="263f4-107">から現在のスレッドに関連付ける偽装トークン。</span><span class="sxs-lookup"><span data-stu-id="263f4-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="263f4-108">この値は `null` の場合もあります。</span><span class="sxs-lookup"><span data-stu-id="263f4-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="263f4-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="263f4-109">Return value</span></span>

<span data-ttu-id="263f4-110">関数が成功した場合、戻り値`S_OK`は (0) になります。</span><span class="sxs-lookup"><span data-stu-id="263f4-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="263f4-111">関数が失敗した場合、戻り値は0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="263f4-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="263f4-112">拡張されたエラー情報を取得するには、 [GetErrorInfo](geterrorinfo.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="263f4-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="263f4-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="263f4-113">Requirements</span></span>  
 <span data-ttu-id="263f4-114">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="263f4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="263f4-115">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="263f4-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="263f4-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="263f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263f4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="263f4-117">See also</span></span>

- [<span data-ttu-id="263f4-118">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="263f4-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
