---
title: ICorDebugThread::EnumerateChains メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
ms.openlocfilehash: 38fe50f5a6608bb27d7a7818dee4784a7f8113ef
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133603"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="088ab-102">ICorDebugThread::EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="088ab-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="088ab-103">この ICorDebugChainEnum Thread オブジェクト内のすべてのスタックチェーンを含む、列挙子へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="088ab-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="088ab-104">構文</span><span class="sxs-lookup"><span data-stu-id="088ab-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="088ab-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="088ab-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="088ab-106">入出力アクティブな (つまり、最新の) チェーンを開始位置として、このスレッド内のすべてのスタックチェーンを列挙できるようにする `ICorDebugChainEnum` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="088ab-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="088ab-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="088ab-107">Remarks</span></span>  
 <span data-ttu-id="088ab-108">スタックチェーンは、スレッドの物理的な呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="088ab-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="088ab-109">次の状況では、スタックチェーン境界が作成されます。</span><span class="sxs-lookup"><span data-stu-id="088ab-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="088ab-110">マネージからアンマネージ、または管理対象外の遷移。</span><span class="sxs-lookup"><span data-stu-id="088ab-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="088ab-111">コンテキストスイッチ。</span><span class="sxs-lookup"><span data-stu-id="088ab-111">A context switch.</span></span>  
  
- <span data-ttu-id="088ab-112">ユーザースレッドのデバッガーハイジャック。</span><span class="sxs-lookup"><span data-stu-id="088ab-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="088ab-113">単一のコンテキストで純粋なマネージコードを実行しているスレッドの単純なケースでは、スレッドとスタックチェーンの間に1対1の対応が存在します。</span><span class="sxs-lookup"><span data-stu-id="088ab-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="088ab-114">デバッガーは、すべてのスレッドの物理的な呼び出し履歴を論理呼び出し履歴に再配置することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="088ab-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="088ab-115">これには、すべてのスレッドのチェーンを呼び出し元/呼び出し先の関係によって並べ替え、それらを再グループ化することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="088ab-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="088ab-116">［要件］</span><span class="sxs-lookup"><span data-stu-id="088ab-116">Requirements</span></span>  
 <span data-ttu-id="088ab-117">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="088ab-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="088ab-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="088ab-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="088ab-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="088ab-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="088ab-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="088ab-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
