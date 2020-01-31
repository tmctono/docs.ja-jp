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
ms.openlocfilehash: cc5093a5ba0afcccaf960e9b8776f93a061cc2f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785680"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="772ff-102">\_EFN\_StackTrace 関数</span><span class="sxs-lookup"><span data-stu-id="772ff-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="772ff-103">マネージド スタック トレースのテキスト表現および `CONTEXT` レコードの配列 (アンマネージド コードとマネージド コードの間の各移行につき 1 つ) を提供します。</span><span class="sxs-lookup"><span data-stu-id="772ff-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="772ff-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="772ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="772ff-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="772ff-106">からデバッグ中のクライアント。</span><span class="sxs-lookup"><span data-stu-id="772ff-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="772ff-107">入出力スタックトレースのテキスト表現。</span><span class="sxs-lookup"><span data-stu-id="772ff-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="772ff-108">入出力`wszTextOut`内の文字数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="772ff-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="772ff-109">入出力遷移コンテキストの配列。</span><span class="sxs-lookup"><span data-stu-id="772ff-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="772ff-110">入出力配列内の遷移コンテキストの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="772ff-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="772ff-111">からコンテキスト構造のサイズ。</span><span class="sxs-lookup"><span data-stu-id="772ff-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="772ff-112">から各 `module!functionname` 行の前に EBP レジスタと enter stack ポインター (ESP) を表示するには、0または SOS_STACKTRACE_SHOWADDRESSES (0x01) のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="772ff-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="772ff-113">コメント</span><span class="sxs-lookup"><span data-stu-id="772ff-113">Remarks</span></span>  
 <span data-ttu-id="772ff-114">`_EFN_StackTrace` 構造体は、WinDbg プログラムインターフェイスから呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="772ff-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="772ff-115">パラメーターは次のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="772ff-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="772ff-116">`wszTextOut` が null で `puiTextLength` が null でない場合、関数は `puiTextLength`に文字列の長さを返します。</span><span class="sxs-lookup"><span data-stu-id="772ff-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="772ff-117">`wszTextOut` が null でない場合、関数は `puiTextLength`によって示される場所まで `wszTextOut` にテキストを格納します。</span><span class="sxs-lookup"><span data-stu-id="772ff-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="772ff-118">バッファーに十分な空き領域がある場合は、正常に返されます。バッファーの長さが十分でない場合は E_OUTOFMEMORY を返します。</span><span class="sxs-lookup"><span data-stu-id="772ff-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="772ff-119">`pTransitionContexts` と `puiTransitionContextCount` が両方とも null の場合、関数の移行部分は無視されます。</span><span class="sxs-lookup"><span data-stu-id="772ff-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="772ff-120">この場合、関数は呼び出し元に関数名のみのテキスト出力を提供します。</span><span class="sxs-lookup"><span data-stu-id="772ff-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="772ff-121">`pTransitionContexts` が null で `puiTransitionContextCount` が null でない場合、関数は `puiTransitionContextCount`に必要なコンテキストエントリの数を返します。</span><span class="sxs-lookup"><span data-stu-id="772ff-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="772ff-122">`pTransitionContexts` が null でない場合、関数はそれを `puiTransitionContextCount`長さの構造体の配列として扱います。</span><span class="sxs-lookup"><span data-stu-id="772ff-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="772ff-123">構造体のサイズは `uiSizeOfContext`によって指定され、 [Simplecontext](stacktrace-simplecontext-structure.md)のサイズまたはアーキテクチャの `CONTEXT` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="772ff-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="772ff-124">`wszTextOut` は次の形式で記述されます。</span><span class="sxs-lookup"><span data-stu-id="772ff-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="772ff-125">16進数のオフセットが0x0 の場合、オフセットは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="772ff-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="772ff-126">現在コンテキスト内にあるスレッドにマネージコードがない場合、関数は SOS_E_NOMANAGEDCODE を返します。</span><span class="sxs-lookup"><span data-stu-id="772ff-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="772ff-127">`Flags` パラメーターは0または SOS_STACKTRACE_SHOWADDRESSES のいずれかになり、各 `module!functionname` 行の前に EBP と ESP が表示されます。</span><span class="sxs-lookup"><span data-stu-id="772ff-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="772ff-128">既定値は0です。</span><span class="sxs-lookup"><span data-stu-id="772ff-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="772ff-129">要件</span><span class="sxs-lookup"><span data-stu-id="772ff-129">Requirements</span></span>  
 <span data-ttu-id="772ff-130">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="772ff-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="772ff-131">**ヘッダー:** SOS_Stacktrace</span><span class="sxs-lookup"><span data-stu-id="772ff-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="772ff-132">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="772ff-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772ff-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="772ff-133">See also</span></span>

- [<span data-ttu-id="772ff-134">デバッグ グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="772ff-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
