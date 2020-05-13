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
ms.openlocfilehash: a74d32478bc88ee634fa5ff9b61ac2059bc8e302
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379715"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="09977-102">ICorDebugThread::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="09977-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="09977-103">この ICorDebugStepper スレッドのアクティブなフレームをステップ実行できるようにする、オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="09977-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09977-104">構文</span><span class="sxs-lookup"><span data-stu-id="09977-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09977-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09977-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="09977-106">入出力`ICorDebugStepper`このスレッドのアクティブフレームのステップ実行を可能にするオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="09977-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09977-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="09977-107">Remarks</span></span>  
 <span data-ttu-id="09977-108">アクティブなフレームはアンマネージコードである場合があります。</span><span class="sxs-lookup"><span data-stu-id="09977-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="09977-109">`ICorDebugStepper`実際のステップ実行には、インターフェイスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09977-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09977-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="09977-110">Requirements</span></span>  
 <span data-ttu-id="09977-111">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09977-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09977-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09977-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09977-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09977-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09977-114">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09977-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
