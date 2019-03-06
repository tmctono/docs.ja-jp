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
ms.openlocfilehash: 8eef616d51febd1b919e0a1936406551f441b98c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468976"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="08cc8-102">ICorDebugThread::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="08cc8-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="08cc8-103">この ICorDebugThread のアクティブな部分の現在のオペレーティング システムの識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="08cc8-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08cc8-104">構文</span><span class="sxs-lookup"><span data-stu-id="08cc8-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08cc8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="08cc8-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="08cc8-106">[out]スレッドの識別子です。</span><span class="sxs-lookup"><span data-stu-id="08cc8-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08cc8-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="08cc8-107">Remarks</span></span>  
 <span data-ttu-id="08cc8-108">オペレーティング システムの識別子は、プロセスの実行中に変更できます可能性があると別のスレッドのさまざまな部分の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="08cc8-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08cc8-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="08cc8-109">Requirements</span></span>  
 <span data-ttu-id="08cc8-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08cc8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08cc8-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08cc8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08cc8-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08cc8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08cc8-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08cc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
