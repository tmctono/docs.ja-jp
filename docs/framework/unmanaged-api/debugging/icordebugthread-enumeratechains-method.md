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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f0ed843f72d3f1e1575da15776a94a9097fd02
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771103"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="71cbf-102">ICorDebugThread::EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="71cbf-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="71cbf-103">この ICorDebugThread オブジェクト内のすべてのスタック チェーンを含む ICorDebugChainEnum 列挙子へのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71cbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="71cbf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71cbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71cbf-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="71cbf-106">[out]アドレスへのポインター、`ICorDebugChainEnum`アクティブ (つまり、最も最近) チェーンから始まる、このスレッド内のチェーンをすべてのスタックの列挙を許可するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="71cbf-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71cbf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="71cbf-107">Remarks</span></span>  
 <span data-ttu-id="71cbf-108">スタック チェーンでは、スレッドの物理呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="71cbf-109">次の状況では、スタック チェーンの境界を作成します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="71cbf-110">マネージとアンマネージまたはアンマネージからマネージへの移行。</span><span class="sxs-lookup"><span data-stu-id="71cbf-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="71cbf-111">コンテキストの切り替え。</span><span class="sxs-lookup"><span data-stu-id="71cbf-111">A context switch.</span></span>  
  
- <span data-ttu-id="71cbf-112">A のユーザー スレッドのハイジャックのデバッガーです。</span><span class="sxs-lookup"><span data-stu-id="71cbf-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="71cbf-113">純粋なマネージ コードを 1 つのコンテキストで実行しているスレッドの単純な場合は、1 対 1 の対応はスレッドとスタック チェーンの間存在します。</span><span class="sxs-lookup"><span data-stu-id="71cbf-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="71cbf-114">デバッガーは、論理呼び出し履歴にすべてのスレッドの物理呼び出し履歴を再配置する場合があります。</span><span class="sxs-lookup"><span data-stu-id="71cbf-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="71cbf-115">これには、すべてのスレッドのチェーンを呼び出し元/呼び出し先のリレーションシップによって並べ替えられ、それらが含まれます。</span><span class="sxs-lookup"><span data-stu-id="71cbf-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71cbf-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="71cbf-116">Requirements</span></span>  
 <span data-ttu-id="71cbf-117">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71cbf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71cbf-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71cbf-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71cbf-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71cbf-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71cbf-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71cbf-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
