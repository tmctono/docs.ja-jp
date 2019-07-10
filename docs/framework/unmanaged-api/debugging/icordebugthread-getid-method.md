---
title: ICorDebugThread::GetID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769970"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="60725-102">ICorDebugThread::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="60725-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="60725-103">この ICorDebugThread のアクティブな部分の現在のオペレーティング システムの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="60725-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60725-104">構文</span><span class="sxs-lookup"><span data-stu-id="60725-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60725-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="60725-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="60725-106">[out]スレッドの識別子です。</span><span class="sxs-lookup"><span data-stu-id="60725-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60725-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="60725-107">Remarks</span></span>  
 <span data-ttu-id="60725-108">オペレーティング システムの識別子は、プロセスの実行中に変更できます可能性があると別のスレッドのさまざまな部分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="60725-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60725-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="60725-109">Requirements</span></span>  
 <span data-ttu-id="60725-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="60725-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60725-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60725-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60725-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60725-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60725-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60725-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
