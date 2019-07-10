---
title: ICorDebugNativeFrame2::GetStackParameterSize メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a5f0f767a7057064e285bf6ac9dcefc86eb9d79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757206"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="35db4-102">ICorDebugNativeFrame2::GetStackParameterSize メソッド</span><span class="sxs-lookup"><span data-stu-id="35db4-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="35db4-103">X86 オペレーティング システム上のスタックで、パラメーターの合計サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="35db4-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35db4-104">構文</span><span class="sxs-lookup"><span data-stu-id="35db4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="35db4-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35db4-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="35db4-106">[out]スタックのパラメーターの合計サイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="35db4-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35db4-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="35db4-107">Return Value</span></span>  
 <span data-ttu-id="35db4-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="35db4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="35db4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35db4-109">HRESULT</span></span>|<span data-ttu-id="35db4-110">説明</span><span class="sxs-lookup"><span data-stu-id="35db4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35db4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="35db4-111">S_OK</span></span>|<span data-ttu-id="35db4-112">スタック サイズが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="35db4-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="35db4-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="35db4-113">S_FALSE</span></span>|<span data-ttu-id="35db4-114">`GetStackParameterSize` x86 以外のプラットフォームで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="35db4-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="35db4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="35db4-115">E_FAIL</span></span>|<span data-ttu-id="35db4-116">`The size of the parameters could not be returned`。</span><span class="sxs-lookup"><span data-stu-id="35db4-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="35db4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="35db4-117">E_INVALIDARG</span></span>|<span data-ttu-id="35db4-118">`pSize` `null`します。</span><span class="sxs-lookup"><span data-stu-id="35db4-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="35db4-119">例外</span><span class="sxs-lookup"><span data-stu-id="35db4-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35db4-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="35db4-120">Remarks</span></span>  
 <span data-ttu-id="35db4-121">[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)メソッドは、スタックにプッシュされるパラメーターのスタック ポインターを調整できません。</span><span class="sxs-lookup"><span data-stu-id="35db4-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="35db4-122">によって返される値を使用する代わりに、`GetStackParameterSize`ネイティブ アンワインダー、これは、パラメーターの調整をシードするスタック ポインターを調整します。</span><span class="sxs-lookup"><span data-stu-id="35db4-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35db4-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="35db4-123">Requirements</span></span>  
 <span data-ttu-id="35db4-124">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="35db4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35db4-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35db4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35db4-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35db4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35db4-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35db4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35db4-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="35db4-128">See also</span></span>

- [<span data-ttu-id="35db4-129">ICorDebugNativeFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35db4-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="35db4-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="35db4-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="35db4-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="35db4-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
