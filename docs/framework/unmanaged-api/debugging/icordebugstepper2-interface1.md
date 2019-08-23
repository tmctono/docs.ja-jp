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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d86f4bbec8971d164966298734388f0744a2d41c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69953033"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="78422-102">ICorDebugStepper2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78422-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="78422-103">マイコードのみ (JMC) デバッグのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="78422-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78422-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="78422-104">Methods</span></span>  
  
|<span data-ttu-id="78422-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="78422-105">Method</span></span>|<span data-ttu-id="78422-106">説明</span><span class="sxs-lookup"><span data-stu-id="78422-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78422-107">SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="78422-107">SetJMC Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-setjmc-method.md)|<span data-ttu-id="78422-108">この ICorDebugStepper が、アプリケーションの開発者によって作成されたコードのみを使用するかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="78422-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78422-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="78422-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="78422-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="78422-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78422-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="78422-111">Requirements</span></span>  
 <span data-ttu-id="78422-112">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="78422-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78422-113">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="78422-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78422-114">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="78422-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78422-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78422-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78422-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="78422-116">See also</span></span>

- [<span data-ttu-id="78422-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="78422-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
