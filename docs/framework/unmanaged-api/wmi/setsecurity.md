---
title: SetSecurity 関数 (アンマネージ API リファレンス)
description: SetSecurity 関数は、現在のスレッドの偽装トークンを取得します。
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94c76213acb66116105d181e9961a33976047ee7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798238"
---
# <a name="setsecurity-function"></a><span data-ttu-id="8f710-103">SetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="8f710-103">SetSecurity function</span></span>

<span data-ttu-id="8f710-104">現在のスレッドに関連付けられている偽装トークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="8f710-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8f710-105">構文</span><span class="sxs-lookup"><span data-stu-id="8f710-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="8f710-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8f710-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="8f710-107">入出力関数から制御が戻るときに、 `boolean` [resetsecurity](resetsecurity.md)関数を呼び出すことによってトークンをリセットする必要があるかどうかを示すへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="8f710-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="8f710-108">入出力関数から制御が戻るときに、現在のスレッドに関連付けられている偽装トークンのハンドルへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="8f710-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="8f710-109">現在のスレッドに`null`関連付けられているトークンが存在しない場合は、その値をにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8f710-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="8f710-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="8f710-110">Return value</span></span>

<span data-ttu-id="8f710-111">関数が成功した場合、戻り値`S_OK`は (0) になります。</span><span class="sxs-lookup"><span data-stu-id="8f710-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="8f710-112">関数が失敗した場合、戻り値は0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="8f710-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="8f710-113">拡張されたエラー情報を取得するには、 [GetErrorInfo](geterrorinfo.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8f710-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f710-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f710-114">Requirements</span></span>

 <span data-ttu-id="8f710-115">**・** [システム要件](../../get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f710-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8f710-116">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="8f710-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="8f710-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8f710-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8f710-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f710-118">See also</span></span>

- [<span data-ttu-id="8f710-119">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="8f710-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
