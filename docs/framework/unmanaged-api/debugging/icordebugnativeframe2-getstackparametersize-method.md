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
ms.openlocfilehash: ca742ba9e89e1d189cfa38dead314df0d8b4e9d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792764"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="2198e-102">ICorDebugNativeFrame2::GetStackParameterSize メソッド</span><span class="sxs-lookup"><span data-stu-id="2198e-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="2198e-103">X86 オペレーティングシステムのスタックのパラメーターの累積サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="2198e-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2198e-104">構文</span><span class="sxs-lookup"><span data-stu-id="2198e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="2198e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2198e-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="2198e-106">入出力スタック上のパラメーターの累積サイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2198e-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2198e-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="2198e-107">Return Value</span></span>  
 <span data-ttu-id="2198e-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="2198e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2198e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2198e-109">HRESULT</span></span>|<span data-ttu-id="2198e-110">説明</span><span class="sxs-lookup"><span data-stu-id="2198e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2198e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2198e-111">S_OK</span></span>|<span data-ttu-id="2198e-112">スタックサイズが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="2198e-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="2198e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2198e-113">S_FALSE</span></span>|<span data-ttu-id="2198e-114">`GetStackParameterSize` が x86 以外のプラットフォームで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="2198e-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="2198e-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2198e-115">E_FAIL</span></span>|<span data-ttu-id="2198e-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="2198e-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="2198e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2198e-117">E_INVALIDARG</span></span>|<span data-ttu-id="2198e-118">`pSize` は `null`です。</span><span class="sxs-lookup"><span data-stu-id="2198e-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="2198e-119">例外</span><span class="sxs-lookup"><span data-stu-id="2198e-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2198e-120">コメント</span><span class="sxs-lookup"><span data-stu-id="2198e-120">Remarks</span></span>  
 <span data-ttu-id="2198e-121">この[方法では、スタック](icordebugstackwalk-interface.md)にプッシュされるパラメーターのスタックポインターは調整されません。</span><span class="sxs-lookup"><span data-stu-id="2198e-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="2198e-122">代わりに、`GetStackParameterSize` によって返された値を使用して、スタックポインターを調整してネイティブアンワインダーをシード処理することができます。これにより、パラメーターが調整されます。</span><span class="sxs-lookup"><span data-stu-id="2198e-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2198e-123">要件</span><span class="sxs-lookup"><span data-stu-id="2198e-123">Requirements</span></span>  
 <span data-ttu-id="2198e-124">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2198e-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2198e-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2198e-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2198e-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2198e-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2198e-127">**.NET Framework のバージョン:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2198e-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2198e-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="2198e-128">See also</span></span>

- [<span data-ttu-id="2198e-129">ICorDebugNativeFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2198e-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="2198e-130">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2198e-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2198e-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="2198e-131">Debugging</span></span>](index.md)
