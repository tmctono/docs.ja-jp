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
ms.openlocfilehash: b88b3907eb555050de93f35411629b2bd30c7375
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212946"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="75440-102">ICorDebugNativeFrame2::GetStackParameterSize メソッド</span><span class="sxs-lookup"><span data-stu-id="75440-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="75440-103">X86 オペレーティングシステムのスタックのパラメーターの累積サイズを返します。</span><span class="sxs-lookup"><span data-stu-id="75440-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75440-104">構文</span><span class="sxs-lookup"><span data-stu-id="75440-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="75440-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="75440-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="75440-106">入出力スタック上のパラメーターの累積サイズへのポインター。</span><span class="sxs-lookup"><span data-stu-id="75440-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="75440-107">戻り値</span><span class="sxs-lookup"><span data-stu-id="75440-107">Return Value</span></span>  
 <span data-ttu-id="75440-108">このメソッドは、次の特定の HRESULT と、メソッドの失敗を示す HRESULT エラーも返します。</span><span class="sxs-lookup"><span data-stu-id="75440-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="75440-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75440-109">HRESULT</span></span>|<span data-ttu-id="75440-110">説明</span><span class="sxs-lookup"><span data-stu-id="75440-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75440-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="75440-111">S_OK</span></span>|<span data-ttu-id="75440-112">スタックサイズが正常に返されました。</span><span class="sxs-lookup"><span data-stu-id="75440-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="75440-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="75440-113">S_FALSE</span></span>|<span data-ttu-id="75440-114">`GetStackParameterSize`は、x86 以外のプラットフォームで呼び出されました。</span><span class="sxs-lookup"><span data-stu-id="75440-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="75440-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75440-115">E_FAIL</span></span>|<span data-ttu-id="75440-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="75440-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="75440-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="75440-117">E_INVALIDARG</span></span>|<span data-ttu-id="75440-118">`pSize`が `null` です。</span><span class="sxs-lookup"><span data-stu-id="75440-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="75440-119">例外</span><span class="sxs-lookup"><span data-stu-id="75440-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75440-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="75440-120">Remarks</span></span>  
 <span data-ttu-id="75440-121">この[方法では、スタック](icordebugstackwalk-interface.md)にプッシュされるパラメーターのスタックポインターは調整されません。</span><span class="sxs-lookup"><span data-stu-id="75440-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="75440-122">代わりに、によって返される値を使用して、スタックポインターを調整してネイティブアンワインダーをシード処理することができます。これにより、 `GetStackParameterSize` パラメーターが調整されます。</span><span class="sxs-lookup"><span data-stu-id="75440-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75440-123">必要条件</span><span class="sxs-lookup"><span data-stu-id="75440-123">Requirements</span></span>  
 <span data-ttu-id="75440-124">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75440-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75440-125">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75440-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75440-126">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75440-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75440-127">**.NET Framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75440-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75440-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="75440-128">See also</span></span>

- [<span data-ttu-id="75440-129">ICorDebugNativeFrame2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="75440-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="75440-130">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="75440-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="75440-131">デバッグ</span><span class="sxs-lookup"><span data-stu-id="75440-131">Debugging</span></span>](index.md)
