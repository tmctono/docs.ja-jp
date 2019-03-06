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
ms.openlocfilehash: e01f94e9574ebc032bc45490fd88ff92e9104aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482861"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="77944-102">ICorDebugThread::EnumerateChains メソッド</span><span class="sxs-lookup"><span data-stu-id="77944-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="77944-103">この ICorDebugThread オブジェクト内のすべてのスタック チェーンを含む ICorDebugChainEnum 列挙子へのインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="77944-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77944-104">構文</span><span class="sxs-lookup"><span data-stu-id="77944-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77944-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77944-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="77944-106">[out]アドレスへのポインター、`ICorDebugChainEnum`アクティブ (つまり、最も最近) チェーンから始まる、このスレッド内のチェーンをすべてのスタックの列挙を許可するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="77944-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77944-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="77944-107">Remarks</span></span>  
 <span data-ttu-id="77944-108">スタック チェーンでは、スレッドの物理呼び出し履歴を表します。</span><span class="sxs-lookup"><span data-stu-id="77944-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="77944-109">次の状況では、スタック チェーンの境界を作成します。</span><span class="sxs-lookup"><span data-stu-id="77944-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="77944-110">マネージとアンマネージまたはアンマネージからマネージへの移行。</span><span class="sxs-lookup"><span data-stu-id="77944-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="77944-111">コンテキストの切り替え。</span><span class="sxs-lookup"><span data-stu-id="77944-111">A context switch.</span></span>  
  
-   <span data-ttu-id="77944-112">A のユーザー スレッドのハイジャックのデバッガーです。</span><span class="sxs-lookup"><span data-stu-id="77944-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="77944-113">純粋なマネージ コードを 1 つのコンテキストで実行しているスレッドの単純な場合は、1 対 1 の対応はスレッドとスタック チェーンの間存在します。</span><span class="sxs-lookup"><span data-stu-id="77944-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="77944-114">デバッガーは、論理呼び出し履歴にすべてのスレッドの物理呼び出し履歴を再配置する場合があります。</span><span class="sxs-lookup"><span data-stu-id="77944-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="77944-115">これには、すべてのスレッドのチェーンを呼び出し元/呼び出し先のリレーションシップによって並べ替えられ、それらが含まれます。</span><span class="sxs-lookup"><span data-stu-id="77944-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77944-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="77944-116">Requirements</span></span>  
 <span data-ttu-id="77944-117">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="77944-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77944-118">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77944-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77944-119">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77944-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77944-120">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77944-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
