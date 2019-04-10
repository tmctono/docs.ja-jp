---
title: ICorDebugExceptionDebugEvent::GetFlags メソッド
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af4c7feb7076eeac6089a3255c7832c17a43469b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208840"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="61492-102">ICorDebugExceptionDebugEvent::GetFlags メソッド</span><span class="sxs-lookup"><span data-stu-id="61492-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="61492-103">例外をインターセプトできるかどうかを示すフラグを取得します。</span><span class="sxs-lookup"><span data-stu-id="61492-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61492-104">構文</span><span class="sxs-lookup"><span data-stu-id="61492-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61492-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="61492-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="61492-106">[out]ポインターを[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)例外をインターセプトできるかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="61492-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61492-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="61492-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61492-108">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="61492-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61492-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="61492-109">Requirements</span></span>  
 <span data-ttu-id="61492-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61492-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61492-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61492-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61492-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61492-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="61492-113">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="61492-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61492-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="61492-114">See also</span></span>

- [<span data-ttu-id="61492-115">ICorDebugExceptionDebugEvent インターフェイス</span><span class="sxs-lookup"><span data-stu-id="61492-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="61492-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="61492-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
