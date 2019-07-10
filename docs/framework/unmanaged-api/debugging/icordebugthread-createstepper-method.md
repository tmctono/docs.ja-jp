---
title: ICorDebugThread::CreateStepper メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95a00e8646589e7897636c1698b7c2647cd233fd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771808"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="61bf7-102">ICorDebugThread::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="61bf7-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="61bf7-103">この ICorDebugThread のアクティブなフレームをステップ実行できるようにする ICorDebugStepper オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="61bf7-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61bf7-104">構文</span><span class="sxs-lookup"><span data-stu-id="61bf7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61bf7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61bf7-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="61bf7-106">[out]アドレスへのポインター、`ICorDebugStepper`このスレッドのアクティブなフレームをステップ実行できるようにするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61bf7-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61bf7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="61bf7-107">Remarks</span></span>  
 <span data-ttu-id="61bf7-108">アクティブなフレームには、アンマネージ コード可能性があります。</span><span class="sxs-lookup"><span data-stu-id="61bf7-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="61bf7-109">`ICorDebugStepper`インターフェイスは、実際のステップを実行するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61bf7-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61bf7-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="61bf7-110">Requirements</span></span>  
 <span data-ttu-id="61bf7-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61bf7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61bf7-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61bf7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61bf7-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61bf7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61bf7-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61bf7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
