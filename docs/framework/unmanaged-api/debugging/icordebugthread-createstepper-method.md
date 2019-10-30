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
ms.openlocfilehash: d1b058aef66ed32c2cadcc3cfd72320dd8eb7729
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133593"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="c8f6c-102">ICorDebugThread::CreateStepper メソッド</span><span class="sxs-lookup"><span data-stu-id="c8f6c-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="c8f6c-103">この ICorDebugStepper スレッドのアクティブなフレームをステップ実行できるようにする、オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c8f6c-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f6c-104">構文</span><span class="sxs-lookup"><span data-stu-id="c8f6c-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8f6c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c8f6c-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="c8f6c-106">入出力このスレッドのアクティブフレームのステップ実行を許可する `ICorDebugStepper` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c8f6c-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8f6c-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8f6c-107">Remarks</span></span>  
 <span data-ttu-id="c8f6c-108">アクティブなフレームはアンマネージコードである場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8f6c-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="c8f6c-109">実際のステップ実行には、`ICorDebugStepper` インターフェイスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8f6c-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f6c-110">［要件］</span><span class="sxs-lookup"><span data-stu-id="c8f6c-110">Requirements</span></span>  
 <span data-ttu-id="c8f6c-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8f6c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f6c-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8f6c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8f6c-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8f6c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8f6c-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f6c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
