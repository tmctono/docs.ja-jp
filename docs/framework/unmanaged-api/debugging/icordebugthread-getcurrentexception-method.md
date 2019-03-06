---
title: ICorDebugThread::GetCurrentException メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4baa4eb4da48b923ab0137ca25d9d819c94e33d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487344"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="2f8fb-102">ICorDebugThread::GetCurrentException メソッド</span><span class="sxs-lookup"><span data-stu-id="2f8fb-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="2f8fb-103">マネージ コードによってスローされる例外を表す ICorDebugValue オブジェクトへのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f8fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="2f8fb-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f8fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f8fb-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="2f8fb-106">[out]アドレスへのポインター、`ICorDebugValue`によってスローされる例外を表すオブジェクトをマネージ コード。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f8fb-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="2f8fb-107">Remarks</span></span>  
 <span data-ttu-id="2f8fb-108">例外オブジェクトが存在してが終わるまで、例外がスローされたときから、`catch`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="2f8fb-109">ICorDebugEval メソッドによって実行される関数の評価は、セットアップの例外オブジェクトをクリアし、完了時に復元します。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="2f8fb-110">例外は、(たとえば、フィルターまたは関数の評価で例外がスローされた) 場合、入れ子になんだことができます、単一のスレッドで複数の未処理の例外が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="2f8fb-111">`GetCurrentException` 最新の例外を返します。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="2f8fb-112">例外オブジェクトと型は、例外の有効期間にわたって変更可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="2f8fb-113">たとえば、x の型の例外がスローされた後共通言語ランタイム (CLR) 可能性がありますメモリが不足し、メモリ不足の例外に昇格させることです。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f8fb-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f8fb-114">Requirements</span></span>  
 <span data-ttu-id="2f8fb-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f8fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f8fb-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2f8fb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2f8fb-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f8fb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f8fb-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f8fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
