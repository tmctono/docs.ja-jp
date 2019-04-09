---
title: ICorDebugProcess6::ProcessStateChanged メソッド
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4dcee3b396d9533f3169db1ea54a6cdc6086c8c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166147"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="c5e50-102">ICorDebugProcess6::ProcessStateChanged メソッド</span><span class="sxs-lookup"><span data-stu-id="c5e50-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="c5e50-103">通知[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)プロセスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c5e50-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5e50-104">構文</span><span class="sxs-lookup"><span data-stu-id="c5e50-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5e50-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c5e50-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="c5e50-106">[in]メンバー、 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md)列挙型</span><span class="sxs-lookup"><span data-stu-id="c5e50-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5e50-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c5e50-107">Remarks</span></span>  
 <span data-ttu-id="c5e50-108">デバッガーに通知するには、このメソッドを呼び出して[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)プロセスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="c5e50-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5e50-109">このメソッドは .NET ネイティブでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5e50-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5e50-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="c5e50-110">Requirements</span></span>  
 <span data-ttu-id="c5e50-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5e50-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e50-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5e50-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5e50-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5e50-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c5e50-114">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="c5e50-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5e50-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5e50-115">See also</span></span>

- [<span data-ttu-id="c5e50-116">ICorDebugProcess6 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5e50-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="c5e50-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="c5e50-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
