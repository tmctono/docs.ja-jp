---
title: ICorDebugStepper2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: 28ec18864158641a337ebdea189080ba4247a7c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120520"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="b908d-102">ICorDebugStepper2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b908d-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="b908d-103">マイコードのみ (JMC) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="b908d-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b908d-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="b908d-104">Methods</span></span>  
  
|<span data-ttu-id="b908d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="b908d-105">Method</span></span>|<span data-ttu-id="b908d-106">説明</span><span class="sxs-lookup"><span data-stu-id="b908d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b908d-107">SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="b908d-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="b908d-108">この ICorDebugStepper が、アプリケーションの開発者によって作成されたコードのみを使用するかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="b908d-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b908d-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="b908d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b908d-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="b908d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b908d-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="b908d-111">Requirements</span></span>  
 <span data-ttu-id="b908d-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b908d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b908d-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b908d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b908d-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b908d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b908d-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b908d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b908d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b908d-116">See also</span></span>

- [<span data-ttu-id="b908d-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b908d-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
