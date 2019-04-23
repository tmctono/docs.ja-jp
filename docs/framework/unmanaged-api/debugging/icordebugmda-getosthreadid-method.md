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
ms.openlocfilehash: 51d29fed3d53611daa0042251ce09638399f7ed5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195801"
---
# <a name="icordebugmdagetosthreadid-method"></a><span data-ttu-id="faa7d-102">ICorDebugMDA::GetOSThreadId メソッド</span><span class="sxs-lookup"><span data-stu-id="faa7d-102">ICorDebugMDA::GetOSThreadId Method</span></span>
<span data-ttu-id="faa7d-103">マネージ デバッグ アシスタント (MDA) が表さとなるオペレーティング システム (OS) のスレッド識別子を取得[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)を実行します。</span><span class="sxs-lookup"><span data-stu-id="faa7d-103">Gets the operating system (OS) thread identifier upon which the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faa7d-104">構文</span><span class="sxs-lookup"><span data-stu-id="faa7d-104">Syntax</span></span>  
  
```  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faa7d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="faa7d-105">Parameters</span></span>  
 `pOsTid`  
 <span data-ttu-id="faa7d-106">[out]OS スレッド識別子へのポインター。</span><span class="sxs-lookup"><span data-stu-id="faa7d-106">[out] A pointer to the OS thread identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="faa7d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="faa7d-107">Remarks</span></span>  
 <span data-ttu-id="faa7d-108">OS スレッドは、ネイティブ スレッドまたはマネージ コードを入力がないマネージ スレッドのいずれかの MDA が発生する状況を考慮に、ICorDebugThread の代わりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="faa7d-108">The OS thread is used instead of an ICorDebugThread to allow for situations in which an MDA is fired either on a native thread or on a managed thread that has not yet entered managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faa7d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="faa7d-109">Requirements</span></span>  
 <span data-ttu-id="faa7d-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="faa7d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faa7d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faa7d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faa7d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faa7d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faa7d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faa7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa7d-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="faa7d-114">See also</span></span>

- [<span data-ttu-id="faa7d-115">ICorDebugMDA インターフェイス</span><span class="sxs-lookup"><span data-stu-id="faa7d-115">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="faa7d-116">マネージド デバッグ アシスタントによるエラーの診断</span><span class="sxs-lookup"><span data-stu-id="faa7d-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
