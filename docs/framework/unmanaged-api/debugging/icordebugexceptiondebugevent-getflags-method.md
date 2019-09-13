---
title: ICorDebugExceptionDebugEvent::GetFlags メソッド
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb92deee21c63c935454ff7c7c4e70be6f770436
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895003"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="9465a-102">ICorDebugExceptionDebugEvent::GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="9465a-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="9465a-103">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="9465a-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9465a-104">構文</span><span class="sxs-lookup"><span data-stu-id="9465a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9465a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9465a-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="9465a-106">入出力例外をインターセプトできるかどうかを示す[Cordebugexceptionflags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="9465a-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9465a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9465a-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9465a-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9465a-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9465a-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9465a-109">Requirements</span></span>  
 <span data-ttu-id="9465a-110">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9465a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9465a-111">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="9465a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9465a-112">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="9465a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9465a-113">**.NET Framework のバージョン:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9465a-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9465a-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="9465a-114">See also</span></span>

- [<span data-ttu-id="9465a-115">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9465a-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="9465a-116">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9465a-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
