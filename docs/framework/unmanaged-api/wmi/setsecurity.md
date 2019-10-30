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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120223"
---
# <a name="setsecurity-function"></a><span data-ttu-id="be3c1-103">SetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="be3c1-103">SetSecurity function</span></span>

<span data-ttu-id="be3c1-104">現在のスレッドに関連付けられている偽装トークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="be3c1-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="be3c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="be3c1-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="be3c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be3c1-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="be3c1-107">入出力関数から制御が戻るときに、 [Resetsecurity](resetsecurity.md)関数を呼び出すことによってトークンをリセットする必要があるかどうかを示す `boolean` へのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="be3c1-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="be3c1-108">入出力関数から制御が戻るときに、現在のスレッドに関連付けられている偽装トークンのハンドルへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="be3c1-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="be3c1-109">現在のスレッドに関連付けられているトークンが存在しない場合は、その値を `null` できます。</span><span class="sxs-lookup"><span data-stu-id="be3c1-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="be3c1-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="be3c1-110">Return value</span></span>

<span data-ttu-id="be3c1-111">関数が成功した場合、戻り値は `S_OK` (0) になります。</span><span class="sxs-lookup"><span data-stu-id="be3c1-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="be3c1-112">関数が失敗した場合、戻り値は0以外のエラーコードです。</span><span class="sxs-lookup"><span data-stu-id="be3c1-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="be3c1-113">拡張されたエラー情報を取得するには、 [GetErrorInfo](geterrorinfo.md)関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be3c1-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="be3c1-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="be3c1-114">Requirements</span></span>

 <span data-ttu-id="be3c1-115">**:** 「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be3c1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="be3c1-116">**ヘッダー:** WMINet_Utils</span><span class="sxs-lookup"><span data-stu-id="be3c1-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="be3c1-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="be3c1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="be3c1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="be3c1-118">See also</span></span>

- [<span data-ttu-id="be3c1-119">WMI およびパフォーマンスカウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="be3c1-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
