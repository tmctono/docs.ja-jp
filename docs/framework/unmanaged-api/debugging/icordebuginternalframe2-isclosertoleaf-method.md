---
title: ICorDebugInternalFrame2::IsCloserToLeaf メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 8b9ec94184945c19b77247175e51bd5e8dc1ceee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122660"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="1fa57-102">ICorDebugInternalFrame2::IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="1fa57-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="1fa57-103">`this` 内部フレームが、指定されたは、指定されたテキストボックスオブジェクトよりもリーフに近いかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fa57-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fa57-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fa57-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fa57-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fa57-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="1fa57-106">から比較 `ICorDebugFrame` オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1fa57-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="1fa57-107">[out] `this` 内部フレームが `pFrameToCompare`で指定されたフレームよりもリーフの近くにある場合に `true` ます。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="1fa57-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fa57-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1fa57-108">Return Value</span></span>  
 <span data-ttu-id="1fa57-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="1fa57-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1fa57-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1fa57-110">HRESULT</span></span>|<span data-ttu-id="1fa57-111">説明</span><span class="sxs-lookup"><span data-stu-id="1fa57-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1fa57-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="1fa57-112">S_OK</span></span>|<span data-ttu-id="1fa57-113">比較が正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="1fa57-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="1fa57-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1fa57-114">E_FAIL</span></span>|<span data-ttu-id="1fa57-115">比較を実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="1fa57-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="1fa57-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1fa57-116">E_INVALIDARG</span></span>|<span data-ttu-id="1fa57-117">`pFrameToCompare` または `pIsCloser` が null です。</span><span class="sxs-lookup"><span data-stu-id="1fa57-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1fa57-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="1fa57-118">Remarks</span></span>  
 <span data-ttu-id="1fa57-119">`IsCloserToLeaf` を使用すると、スタック上の他のフレームと内部フレームをインターリーブするポリシーを実装できます。</span><span class="sxs-lookup"><span data-stu-id="1fa57-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fa57-120">［要件］</span><span class="sxs-lookup"><span data-stu-id="1fa57-120">Requirements</span></span>  
 <span data-ttu-id="1fa57-121">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa57-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fa57-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fa57-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fa57-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fa57-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fa57-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fa57-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fa57-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fa57-125">See also</span></span>

- [<span data-ttu-id="1fa57-126">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fa57-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="1fa57-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1fa57-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="1fa57-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="1fa57-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
