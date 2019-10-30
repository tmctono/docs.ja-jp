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
ms.openlocfilehash: ca5db8c8570cedd9b0412b71058d453112a1831c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140134"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="a0c98-102">ICorDebugThread3::CreateStackWalk メソッド</span><span class="sxs-lookup"><span data-stu-id="a0c98-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="a0c98-103">スタックをアンワインドするスレッドに対し[て、このオブジェクトを](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)作成します。</span><span class="sxs-lookup"><span data-stu-id="a0c98-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0c98-104">構文</span><span class="sxs-lookup"><span data-stu-id="a0c98-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0c98-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a0c98-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="a0c98-106">入出力スタックをアンワインドするスレッド[の、説明オブジェクトの](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)アドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a0c98-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0c98-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="a0c98-107">Return Value</span></span>  
 <span data-ttu-id="a0c98-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a0c98-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a0c98-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0c98-109">HRESULT</span></span>|<span data-ttu-id="a0c98-110">説明</span><span class="sxs-lookup"><span data-stu-id="a0c98-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0c98-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0c98-111">S_OK</span></span>|<span data-ttu-id="a0c98-112">`ICorDebugStackWalk` オブジェクトが正常に作成されました。</span><span class="sxs-lookup"><span data-stu-id="a0c98-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="a0c98-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0c98-113">E_FAIL</span></span>|<span data-ttu-id="a0c98-114">`ICorDebugStackWalk` オブジェクトは作成されませんでした。</span><span class="sxs-lookup"><span data-stu-id="a0c98-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a0c98-115">例外</span><span class="sxs-lookup"><span data-stu-id="a0c98-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0c98-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="a0c98-116">Remarks</span></span>  
 <span data-ttu-id="a0c98-117">`CreateStackWalk` メソッドが成功すると、返された `ICorDebugStackWalk` オブジェクトのコンテキストが、スレッドの現在のコンテキストに設定されます。</span><span class="sxs-lookup"><span data-stu-id="a0c98-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0c98-118">［要件］</span><span class="sxs-lookup"><span data-stu-id="a0c98-118">Requirements</span></span>  
 <span data-ttu-id="a0c98-119">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0c98-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0c98-120">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0c98-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0c98-121">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0c98-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0c98-122">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0c98-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c98-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0c98-123">See also</span></span>

- [<span data-ttu-id="a0c98-124">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a0c98-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a0c98-125">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a0c98-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
