---
title: ICorDebugChainEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum
helpviewer_keywords:
- ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6639335c-48e1-4e74-a4f3-70a6a0f54af1
topic_type:
- apiref
ms.openlocfilehash: 4556ebbd05e0660da14fb59d806c8feb0b45b9bb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894230"
---
# <a name="icordebugchainenum-interface"></a><span data-ttu-id="fde31-102">ICorDebugChainEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="fde31-102">ICorDebugChainEnum Interface</span></span>

<span data-ttu-id="fde31-103">ICorDebugEnum メソッドを実装し、を列挙します。</span><span class="sxs-lookup"><span data-stu-id="fde31-103">Implements ICorDebugEnum methods, and enumerates ICorDebugChain arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fde31-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="fde31-104">Methods</span></span>  
  
|<span data-ttu-id="fde31-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="fde31-105">Method</span></span>|<span data-ttu-id="fde31-106">説明</span><span class="sxs-lookup"><span data-stu-id="fde31-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fde31-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="fde31-107">Next Method</span></span>](icordebugchainenum-next-method.md)|<span data-ttu-id="fde31-108">現在の`ICorDebugChain`位置から開始して、指定した数のインスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="fde31-108">Gets the specified number of `ICorDebugChain` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fde31-109">解説</span><span class="sxs-lookup"><span data-stu-id="fde31-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fde31-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fde31-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde31-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="fde31-111">Requirements</span></span>  
 <span data-ttu-id="fde31-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fde31-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde31-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fde31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fde31-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fde31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fde31-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde31-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="fde31-116">See also</span></span>

- [<span data-ttu-id="fde31-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="fde31-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
