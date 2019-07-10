---
title: ICorDebugProcess::GetThreadContext メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c137a10d5da94d04509385fc97d71535d33fae93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758741"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="cab47-102">ICorDebugProcess::GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="cab47-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="cab47-103">このプロセスで特定のスレッドのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="cab47-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cab47-104">構文</span><span class="sxs-lookup"><span data-stu-id="cab47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cab47-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cab47-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="cab47-106">[in]コンテキストを取得する対象のスレッドの ID。</span><span class="sxs-lookup"><span data-stu-id="cab47-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cab47-107">[in] `context` 配列のサイズ。</span><span class="sxs-lookup"><span data-stu-id="cab47-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="cab47-108">[入力、出力]スレッドのコンテキストを表すバイトの配列。</span><span class="sxs-lookup"><span data-stu-id="cab47-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="cab47-109">コンテキストには、スレッドが実行されているプロセッサのアーキテクチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="cab47-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cab47-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="cab47-110">Remarks</span></span>  
 <span data-ttu-id="cab47-111">デバッガーは、Win32 ではなく、このメソッドを呼び出す必要があります`GetThreadContext`メソッド、スレッドは、「ハイジャック」をそのコンテキストが一時的に変更された状態で実際にできるためです。</span><span class="sxs-lookup"><span data-stu-id="cab47-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="cab47-112">ネイティブ コードでスレッドがある場合にのみ、このメソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cab47-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="cab47-113">使用[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)マネージ コード内のスレッドにします。</span><span class="sxs-lookup"><span data-stu-id="cab47-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="cab47-114">返されるデータは、現在のプラットフォームのコンテキスト構造です。</span><span class="sxs-lookup"><span data-stu-id="cab47-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="cab47-115">Win32 と同様に、`GetThreadContext`メソッドを呼び出し元を初期化する必要があります、`context`このメソッドを呼び出す前にパラメーター。</span><span class="sxs-lookup"><span data-stu-id="cab47-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cab47-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="cab47-116">Requirements</span></span>  
 <span data-ttu-id="cab47-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cab47-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cab47-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cab47-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cab47-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cab47-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cab47-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cab47-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
