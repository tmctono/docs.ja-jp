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
ms.openlocfilehash: d01936481ec139757566d5b96cb95ea887cb8c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378063"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="5dd2f-102">ICorDebugThread::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="5dd2f-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="5dd2f-103">このコンポーネントのアクティブな部分の現在のオペレーティングシステム識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5dd2f-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dd2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="5dd2f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dd2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5dd2f-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="5dd2f-106">入出力スレッドの識別子。</span><span class="sxs-lookup"><span data-stu-id="5dd2f-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5dd2f-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5dd2f-107">Remarks</span></span>  
 <span data-ttu-id="5dd2f-108">オペレーティングシステムの識別子は、プロセスの実行中に変更される可能性があり、スレッドのさまざまな部分に対して異なる値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5dd2f-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dd2f-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5dd2f-109">Requirements</span></span>  
 <span data-ttu-id="5dd2f-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dd2f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dd2f-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dd2f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dd2f-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dd2f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dd2f-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dd2f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
