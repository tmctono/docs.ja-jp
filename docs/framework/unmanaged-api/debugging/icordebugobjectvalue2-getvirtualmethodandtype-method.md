---
title: ICorDebugObjectValue2::GetVirtualMethodAndType メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue2.GetVirtualMethodAndType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue2::GetVirtualMethodAndType
helpviewer_keywords:
- GetVirtualMethodAndType method [.NET Framework debugging]
- ICorDebugObjectValue2::GetVirtualMethodAndType method
ms.assetid: 621b4543-a8f7-4117-98e4-930992cd688a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 252a65c66764d60f5e307ba1eaad4ded34d9744d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975742"
---
# <a name="icordebugobjectvalue2getvirtualmethodandtype-method"></a><span data-ttu-id="9c97c-102">ICorDebugObjectValue2::GetVirtualMethodAndType メソッド</span><span class="sxs-lookup"><span data-stu-id="9c97c-102">ICorDebugObjectValue2::GetVirtualMethodAndType Method</span></span>
<span data-ttu-id="9c97c-103">このメソッドはまだ実装されていません。</span><span class="sxs-lookup"><span data-stu-id="9c97c-103">This method is not yet implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c97c-104">構文</span><span class="sxs-lookup"><span data-stu-id="9c97c-104">Syntax</span></span>  
  
```  
HRESULT GetVirtualMethodAndType (  
    [in] mdMemberRef          memberRef,  
    [out] ICorDebugFunction   **ppFunction,  
    [out] ICorDebugType       **ppType  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="9c97c-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="9c97c-105">Remarks</span></span>  
 <span data-ttu-id="9c97c-106">取得、最派生メソッドと、指定したメンバーの参照の型を表す"ICorDebugFunction"と"ICorDebugType"のインスタンスへのポインターをインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="9c97c-106">Gets interface pointers to the "ICorDebugFunction" and "ICorDebugType" instances that represent the most derived method and type for the specified member reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c97c-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c97c-107">See also</span></span>
