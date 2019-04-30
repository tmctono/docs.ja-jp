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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995502"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="a951e-102">ICorDebugInternalFrame2::IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="a951e-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="a951e-103">チェックするかどうか、`this`内部フレームは、指定した ICorDebugFrame オブジェクトよりも、リーフに近いです。</span><span class="sxs-lookup"><span data-stu-id="a951e-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a951e-104">構文</span><span class="sxs-lookup"><span data-stu-id="a951e-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a951e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a951e-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="a951e-106">[in]比較へのポインター`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="a951e-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="a951e-107">[out]`true`場合、`this`内部フレームがで指定されたフレームよりも近いリーフのため`pFrameToCompare`、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="a951e-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a951e-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a951e-108">Return Value</span></span>  
 <span data-ttu-id="a951e-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="a951e-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a951e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a951e-110">HRESULT</span></span>|<span data-ttu-id="a951e-111">説明</span><span class="sxs-lookup"><span data-stu-id="a951e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a951e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="a951e-112">S_OK</span></span>|<span data-ttu-id="a951e-113">比較が正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="a951e-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="a951e-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a951e-114">E_FAIL</span></span>|<span data-ttu-id="a951e-115">比較を実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="a951e-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="a951e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a951e-116">E_INVALIDARG</span></span>|<span data-ttu-id="a951e-117">`pFrameToCompare` または `pIsCloser` が null です。</span><span class="sxs-lookup"><span data-stu-id="a951e-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a951e-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="a951e-118">Remarks</span></span>  
 <span data-ttu-id="a951e-119">`IsCloserToLeaf` スタック上の他のフレームを持つ内部フレームをインターリーブのポリシーを実装するために使用します。</span><span class="sxs-lookup"><span data-stu-id="a951e-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a951e-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="a951e-120">Requirements</span></span>  
 <span data-ttu-id="a951e-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a951e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a951e-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a951e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a951e-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a951e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a951e-124">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a951e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a951e-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a951e-125">See also</span></span>

- [<span data-ttu-id="a951e-126">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a951e-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="a951e-127">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="a951e-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a951e-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="a951e-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
