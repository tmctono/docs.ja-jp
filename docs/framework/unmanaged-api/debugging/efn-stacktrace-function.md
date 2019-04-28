---
title: _EFN_StackTrace 関数
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfbdbb389f9945ffeea649bcddd45bee8caf2496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698318"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="e6dc7-102">_EFN_StackTrace 関数</span><span class="sxs-lookup"><span data-stu-id="e6dc7-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="e6dc7-103">マネージド スタック トレースのテキスト表現および `CONTEXT` レコードの配列 (アンマネージド コードとマネージド コードの間の各移行につき 1 つ) を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6dc7-104">構文</span><span class="sxs-lookup"><span data-stu-id="e6dc7-104">Syntax</span></span>  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6dc7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6dc7-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="e6dc7-106">[in]デバッグ中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="e6dc7-107">[out]スタック トレースのテキスト表現。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="e6dc7-108">[out]文字数へのポインター`wszTextOut`します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="e6dc7-109">[out]コンテキストの切り替えの配列。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="e6dc7-110">[out]配列内の遷移のコンテキストの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="e6dc7-111">[in]Context 構造体のサイズ。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="e6dc7-112">[in]0 または SOS_STACKTRACE_SHOWADDRESSES (0x01) のいずれかに設定すると、EBP レジスタとそれぞれの前に入力スタック ポインター (ESP) を表示する`module!functionname`行。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6dc7-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="e6dc7-113">Remarks</span></span>  
 <span data-ttu-id="e6dc7-114">`_EFN_StackTrace`構造体は、WinDbg プログラマティック インターフェイスから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="e6dc7-115">パラメーターは、次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="e6dc7-116">場合`wszTextOut`が null と`puiTextLength`が null でない関数は、返す文字列の長さで`puiTextLength`します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="e6dc7-117">場合`wszTextOut`が null でないテキストでは、関数には格納`wszTextOut`によって示される位置まで`puiTextLength`します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="e6dc7-118">バッファーの長さが不足している場合、バッファー、または返します E_OUTOFMEMORY で十分な空き領域が認識されたかどうかを正常に返します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="e6dc7-119">場合、関数の遷移の部分は無視されます`pTransitionContexts`と`puiTransitionContextCount`はどちらも null です。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="e6dc7-120">この場合、関数は、関数名のみのテキスト出力を持つ呼び出し元を提供します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="e6dc7-121">場合`pTransitionContexts`が null と`puiTransitionContextCount`が null でない関数返しますコンテキスト エントリのために必要な数`puiTransitionContextCount`します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="e6dc7-122">場合`pTransitionContexts`が null でない関数として扱われます長さの構造体の配列`puiTransitionContextCount`します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="e6dc7-123">構造体のサイズがで指定された`uiSizeOfContext`のサイズを指定する必要があります[SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)または`CONTEXT`のアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="e6dc7-124">`wszTextOut` 次の形式で書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="e6dc7-125">16 進数でオフセットが「0x0」の場合、オフセットは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="e6dc7-126">コードがないマネージ スレッドの現在のコンテキストで、関数は SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="e6dc7-127">`Flags`パラメーターが 0 またはそれぞれの前に、EBP と ESP を表示する SOS_STACKTRACE_SHOWADDRESSES`module!functionname`行。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="e6dc7-128">既定では、これは 0 です。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="e6dc7-129">必要条件</span><span class="sxs-lookup"><span data-stu-id="e6dc7-129">Requirements</span></span>  
 <span data-ttu-id="e6dc7-130">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6dc7-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6dc7-131">**ヘッダー:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="e6dc7-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="e6dc7-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6dc7-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6dc7-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="e6dc7-133">See also</span></span>

- [<span data-ttu-id="e6dc7-134">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="e6dc7-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
