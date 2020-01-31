---
title: ICorDebugTypeEnum インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
ms.openlocfilehash: ed7bceec9bf6ea0cf69cbb57fff83a91093ba6c4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791211"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="f1ca9-102">ICorDebugTypeEnum インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1ca9-102">ICorDebugTypeEnum Interface</span></span>
<span data-ttu-id="f1ca9-103">"ICorDebugEnum" メソッドを実装し、"" 配列を列挙します。</span><span class="sxs-lookup"><span data-stu-id="f1ca9-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1ca9-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1ca9-104">Methods</span></span>  
  
|<span data-ttu-id="f1ca9-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="f1ca9-105">Method</span></span>|<span data-ttu-id="f1ca9-106">説明</span><span class="sxs-lookup"><span data-stu-id="f1ca9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1ca9-107">Next メソッド</span><span class="sxs-lookup"><span data-stu-id="f1ca9-107">Next Method</span></span>](icordebugtypeenum-next-method.md)|<span data-ttu-id="f1ca9-108">現在の位置から開始して、指定した数の `ICorDebugType` インスタンスを列挙から取得します。</span><span class="sxs-lookup"><span data-stu-id="f1ca9-108">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1ca9-109">コメント</span><span class="sxs-lookup"><span data-stu-id="f1ca9-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1ca9-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f1ca9-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1ca9-111">要件</span><span class="sxs-lookup"><span data-stu-id="f1ca9-111">Requirements</span></span>  
 <span data-ttu-id="f1ca9-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1ca9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1ca9-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1ca9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1ca9-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1ca9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1ca9-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1ca9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ca9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1ca9-116">See also</span></span>

- [<span data-ttu-id="f1ca9-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f1ca9-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
