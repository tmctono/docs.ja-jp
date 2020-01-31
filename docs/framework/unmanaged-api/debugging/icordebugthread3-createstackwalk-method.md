---
title: ICorDebugThread3::CreateStackWalk メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: 64f6bc9abb8105cdfa942c2aaca71994e8a91765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791414"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="94780-102">ICorDebugThread3::CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="94780-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="94780-103">スタックをアンワインドするスレッドに対し[て、このオブジェクトを](icordebugstackwalk-interface.md)作成します。</span><span class="sxs-lookup"><span data-stu-id="94780-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94780-104">構文</span><span class="sxs-lookup"><span data-stu-id="94780-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94780-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="94780-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="94780-106">入出力スタックをアンワインドするスレッド[の、説明オブジェクトの](icordebugstackwalk-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="94780-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94780-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="94780-107">Return Value</span></span>  
 <span data-ttu-id="94780-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="94780-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="94780-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94780-109">HRESULT</span></span>|<span data-ttu-id="94780-110">説明</span><span class="sxs-lookup"><span data-stu-id="94780-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94780-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="94780-111">S_OK</span></span>|<span data-ttu-id="94780-112">`ICorDebugStackWalk` オブジェクトが正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="94780-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="94780-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94780-113">E_FAIL</span></span>|<span data-ttu-id="94780-114">`ICorDebugStackWalk` オブジェクトは作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="94780-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="94780-115">例外</span><span class="sxs-lookup"><span data-stu-id="94780-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94780-116">コメント</span><span class="sxs-lookup"><span data-stu-id="94780-116">Remarks</span></span>  
 <span data-ttu-id="94780-117">`CreateStackWalk` メソッドが成功すると、返された `ICorDebugStackWalk` オブジェクトのコンテキストが、スレッドの現在のコンテキストに設定されます。</span><span class="sxs-lookup"><span data-stu-id="94780-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94780-118">要件</span><span class="sxs-lookup"><span data-stu-id="94780-118">Requirements</span></span>  
 <span data-ttu-id="94780-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94780-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94780-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94780-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94780-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94780-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94780-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94780-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94780-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="94780-123">See also</span></span>

- [<span data-ttu-id="94780-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="94780-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="94780-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="94780-125">Debugging</span></span>](index.md)
