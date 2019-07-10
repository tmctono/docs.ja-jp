---
title: ICorDebugMDA::GetOSThreadId メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5d676e0fad33ca994b2e5bcd7adf269e306cb55
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761923"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="71d09-102">ICorDebugMDA::GetOSThreadId メソッド</span><span class="sxs-lookup"><span data-stu-id="71d09-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="71d09-103">マネージ デバッグ アシスタント (MDA) が表さとなるオペレーティング システム (OS) のスレッド識別子を取得[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="71d09-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71d09-104">構文</span><span class="sxs-lookup"><span data-stu-id="71d09-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71d09-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="71d09-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="71d09-106">[out]OS スレッド識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="71d09-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71d09-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="71d09-107">Remarks</span></span>  
 <span data-ttu-id="71d09-108">OS スレッドは、ネイティブ スレッドまたはマネージ コードを入力がないマネージ スレッドのいずれかの MDA が発生する状況を考慮に、ICorDebugThread の代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="71d09-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71d09-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="71d09-109">Requirements</span></span>  
 <span data-ttu-id="71d09-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="71d09-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71d09-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71d09-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71d09-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71d09-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71d09-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71d09-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71d09-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="71d09-114">See also</span></span>

- [<span data-ttu-id="71d09-115">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="71d09-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="71d09-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="71d09-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
