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
ms.openlocfilehash: 7200e3a19fcadabb5e149c38b620b3f60907c392
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948540"
---
# <a name="setsecurity-function"></a><span data-ttu-id="1ccd6-103">SetSecurity 関数</span><span class="sxs-lookup"><span data-stu-id="1ccd6-103">SetSecurity function</span></span>

<span data-ttu-id="1ccd6-104">現在のスレッドに関連付けられている偽装トークンが取得されます。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1ccd6-105">構文</span><span class="sxs-lookup"><span data-stu-id="1ccd6-105">Syntax</span></span>

```
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="1ccd6-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ccd6-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="1ccd6-107">[out]関数から制御が戻るときにへのポインターを格納する`boolean`を呼び出してトークンをリセットするかどうかを示す、 [ResetSecurity](resetsecurity.md)関数。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="1ccd6-108">[out]関数から制御が戻るときは、現在のスレッドに関連付けられている権限借用トークンのハンドルへのポインターを格納します。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="1ccd6-109">その値を指定できます`null`かどうかは、現在のスレッドに関連付けられているトークンはありません。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="1ccd6-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="1ccd6-110">Return value</span></span>

<span data-ttu-id="1ccd6-111">関数が成功した場合、戻り値は`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="1ccd6-112">関数が失敗した場合、戻り値が 0 以外のエラー コードにします。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="1ccd6-113">拡張エラー情報を取得する、 [GetErrorInfo](geterrorinfo.md)関数。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ccd6-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ccd6-114">Requirements</span></span>

 <span data-ttu-id="1ccd6-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ccd6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="1ccd6-116">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="1ccd6-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="1ccd6-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1ccd6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1ccd6-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ccd6-118">See also</span></span>

- [<span data-ttu-id="1ccd6-119">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1ccd6-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)