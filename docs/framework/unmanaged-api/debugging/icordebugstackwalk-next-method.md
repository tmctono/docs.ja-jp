---
title: ICorDebugStackWalk::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: b89e968e9b12943c8192af3b280f8bd321a02110
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378792"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="abfb3-102">ICorDebugStackWalk::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="abfb3-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="abfb3-103">このオブジェクトを次のフレームに[移動します](icordebugstackwalk-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="abfb3-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abfb3-104">構文</span><span class="sxs-lookup"><span data-stu-id="abfb3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="abfb3-105">戻り値</span><span class="sxs-lookup"><span data-stu-id="abfb3-105">Return Value</span></span>  
 <span data-ttu-id="abfb3-106">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="abfb3-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="abfb3-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abfb3-107">HRESULT</span></span>|<span data-ttu-id="abfb3-108">説明</span><span class="sxs-lookup"><span data-stu-id="abfb3-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abfb3-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="abfb3-109">S_OK</span></span>|<span data-ttu-id="abfb3-110">ランタイムが次のフレームに正常にアンワインドされました (「解説」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="abfb3-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="abfb3-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abfb3-111">E_FAIL</span></span>|<span data-ttu-id="abfb3-112">`ICorDebugStackWalk`オブジェクトを拡張できませんでした。</span><span class="sxs-lookup"><span data-stu-id="abfb3-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="abfb3-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="abfb3-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="abfb3-114">このアンワインドの結果、スタックの末尾に到達しました。</span><span class="sxs-lookup"><span data-stu-id="abfb3-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="abfb3-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="abfb3-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="abfb3-116">フレームポインターは既にスタックの末尾にあります。そのため、追加のフレームにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="abfb3-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="abfb3-117">例外</span><span class="sxs-lookup"><span data-stu-id="abfb3-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abfb3-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="abfb3-118">Remarks</span></span>  
 <span data-ttu-id="abfb3-119">メソッドは、 `Next` `ICorDebugStackWalk` ランタイムが現在のフレームをアンワインドできる場合にのみ、オブジェクトを呼び出し元のフレームに進めます。</span><span class="sxs-lookup"><span data-stu-id="abfb3-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="abfb3-120">それ以外の場合、オブジェクトは、ランタイムがアンワインドできる次のフレームに進みます。</span><span class="sxs-lookup"><span data-stu-id="abfb3-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abfb3-121">必要条件</span><span class="sxs-lookup"><span data-stu-id="abfb3-121">Requirements</span></span>  
 <span data-ttu-id="abfb3-122">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="abfb3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abfb3-123">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="abfb3-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="abfb3-124">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abfb3-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abfb3-125">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abfb3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfb3-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="abfb3-126">See also</span></span>

- [<span data-ttu-id="abfb3-127">ICorDebugStackWalk インターフェイス</span><span class="sxs-lookup"><span data-stu-id="abfb3-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="abfb3-128">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="abfb3-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="abfb3-129">デバッグ</span><span class="sxs-lookup"><span data-stu-id="abfb3-129">Debugging</span></span>](index.md)
