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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120901"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="ae213-102">ICorDebugInternalFrame2::IsCloserToLeaf メソッド</span><span class="sxs-lookup"><span data-stu-id="ae213-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="ae213-103">チェックするかどうか、`this`内部フレームは、指定した ICorDebugFrame オブジェクトよりも、リーフに近いです。</span><span class="sxs-lookup"><span data-stu-id="ae213-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae213-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae213-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae213-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ae213-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="ae213-106">[in]比較へのポインター`ICorDebugFrame`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ae213-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="ae213-107">[out]`true`場合、`this`内部フレームがで指定されたフレームよりも近いリーフのため`pFrameToCompare`、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="ae213-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae213-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ae213-108">Return Value</span></span>  
 <span data-ttu-id="ae213-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="ae213-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ae213-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae213-110">HRESULT</span></span>|<span data-ttu-id="ae213-111">説明</span><span class="sxs-lookup"><span data-stu-id="ae213-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae213-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae213-112">S_OK</span></span>|<span data-ttu-id="ae213-113">比較が正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="ae213-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="ae213-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae213-114">E_FAIL</span></span>|<span data-ttu-id="ae213-115">比較を実行できませんでした。</span><span class="sxs-lookup"><span data-stu-id="ae213-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="ae213-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ae213-116">E_INVALIDARG</span></span>|`pFrameToCompare` <span data-ttu-id="ae213-117">または`pIsCloser`が null です。</span><span class="sxs-lookup"><span data-stu-id="ae213-117">or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae213-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="ae213-118">Remarks</span></span>  
 `IsCloserToLeaf` <span data-ttu-id="ae213-119">スタック上の他のフレームを持つ内部フレームをインターリーブのポリシーを実装するために使用します。</span><span class="sxs-lookup"><span data-stu-id="ae213-119">can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae213-120">必要条件</span><span class="sxs-lookup"><span data-stu-id="ae213-120">Requirements</span></span>  
 <span data-ttu-id="ae213-121">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae213-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae213-122">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae213-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae213-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae213-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ae213-124">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="ae213-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ae213-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae213-125">See also</span></span>

- [<span data-ttu-id="ae213-126">ICorDebugInternalFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae213-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="ae213-127">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ae213-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ae213-128">デバッグ</span><span class="sxs-lookup"><span data-stu-id="ae213-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
