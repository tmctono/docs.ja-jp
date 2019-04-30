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
ms.openlocfilehash: 89182739633984011aaab3d7900d376b6db5ef99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987190"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="f85ba-102">ICorDebugThread::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="f85ba-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="f85ba-103">この ICorDebugThread のアクティブなフレームをステップ実行できるようにする ICorDebugStepper オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f85ba-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f85ba-104">構文</span><span class="sxs-lookup"><span data-stu-id="f85ba-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f85ba-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f85ba-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="f85ba-106">[out]アドレスへのポインター、`ICorDebugStepper`このスレッドのアクティブなフレームをステップ実行できるようにするオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="f85ba-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f85ba-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="f85ba-107">Remarks</span></span>  
 <span data-ttu-id="f85ba-108">アクティブなフレームには、アンマネージ コード可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f85ba-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="f85ba-109">`ICorDebugStepper`インターフェイスは、実際のステップを実行するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f85ba-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f85ba-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="f85ba-110">Requirements</span></span>  
 <span data-ttu-id="f85ba-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f85ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f85ba-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f85ba-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f85ba-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f85ba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f85ba-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f85ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
