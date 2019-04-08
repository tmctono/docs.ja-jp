---
title: ICorDebugNativeFrame2::IsMatchingParentFrame メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a553f2cbac6110e82803e6d0dd872cfaa15d773
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099925"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="bc717-102">ICorDebugNativeFrame2::IsMatchingParentFrame メソッド</span><span class="sxs-lookup"><span data-stu-id="bc717-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="bc717-103">指定したフレームの現在のフレームの親であるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="bc717-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc717-104">構文</span><span class="sxs-lookup"><span data-stu-id="bc717-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc717-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc717-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="bc717-106">[in]親のステータスを評価するフレーム オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="bc717-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="bc717-107">[out]`true`場合`pPotentialParentFrame`現在のフレームの親が、それ以外の`false`します。</span><span class="sxs-lookup"><span data-stu-id="bc717-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bc717-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="bc717-108">Return Value</span></span>  
 <span data-ttu-id="bc717-109">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="bc717-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bc717-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bc717-110">HRESULT</span></span>|<span data-ttu-id="bc717-111">説明</span><span class="sxs-lookup"><span data-stu-id="bc717-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bc717-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bc717-112">S_OK</span></span>|<span data-ttu-id="bc717-113">親のステータスは正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="bc717-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="bc717-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bc717-114">E_FAIL</span></span>|<span data-ttu-id="bc717-115">親のステータスが返されませんでした。</span><span class="sxs-lookup"><span data-stu-id="bc717-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="bc717-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="bc717-116">E_INVALIDARG</span></span>|`pPotentialParentFrame` <span data-ttu-id="bc717-117">または`pIsParent`が null です。</span><span class="sxs-lookup"><span data-stu-id="bc717-117">or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="bc717-118">例外</span><span class="sxs-lookup"><span data-stu-id="bc717-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc717-119">Remarks</span><span class="sxs-lookup"><span data-stu-id="bc717-119">Remarks</span></span>  
 `IsMatchingParentFrame` <span data-ttu-id="bc717-120">返します`true`フレーム オブジェクトをメソッドに渡すメソッドが呼び出されたフレーム オブジェクトの親であるかどうか。</span><span class="sxs-lookup"><span data-stu-id="bc717-120">returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="bc717-121">指定したフレームの子ではない特定のフレーム、メソッドを呼び出す場合は、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="bc717-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc717-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="bc717-122">Requirements</span></span>  
 <span data-ttu-id="bc717-123">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc717-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc717-124">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bc717-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bc717-125">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc717-125">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bc717-126">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="bc717-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc717-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="bc717-127">See also</span></span>

- [<span data-ttu-id="bc717-128">ICorDebugNativeFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc717-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="bc717-129">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="bc717-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bc717-130">デバッグ</span><span class="sxs-lookup"><span data-stu-id="bc717-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
