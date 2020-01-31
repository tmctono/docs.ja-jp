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
ms.openlocfilehash: d154cf10e60935d12653c70875323079f92ae288
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791742"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="cfe44-102">ICorDebugStepper2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfe44-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="cfe44-103">マイコードのみ (JMC) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="cfe44-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cfe44-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="cfe44-104">Methods</span></span>  
  
|<span data-ttu-id="cfe44-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="cfe44-105">Method</span></span>|<span data-ttu-id="cfe44-106">説明</span><span class="sxs-lookup"><span data-stu-id="cfe44-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cfe44-107">SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="cfe44-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="cfe44-108">この ICorDebugStepper が、アプリケーションの開発者によって作成されたコードのみを使用するかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="cfe44-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cfe44-109">コメント</span><span class="sxs-lookup"><span data-stu-id="cfe44-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cfe44-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="cfe44-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfe44-111">要件</span><span class="sxs-lookup"><span data-stu-id="cfe44-111">Requirements</span></span>  
 <span data-ttu-id="cfe44-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfe44-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfe44-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cfe44-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cfe44-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfe44-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cfe44-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfe44-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfe44-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cfe44-116">See also</span></span>

- [<span data-ttu-id="cfe44-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cfe44-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
