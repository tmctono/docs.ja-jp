---
title: ICorDebugBoxValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: bece1be7474c57d38f083e322c2af1b0ba705ee9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894762"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="ec926-102">ICorDebugBoxValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec926-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="ec926-103">ボックス化された値クラスオブジェクトを表す "" "のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="ec926-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ec926-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="ec926-104">Methods</span></span>  
  
|<span data-ttu-id="ec926-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="ec926-105">Method</span></span>|<span data-ttu-id="ec926-106">説明</span><span class="sxs-lookup"><span data-stu-id="ec926-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ec926-107">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="ec926-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="ec926-108">ボックス化された "の" のインスタンスへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="ec926-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec926-109">解説</span><span class="sxs-lookup"><span data-stu-id="ec926-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec926-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="ec926-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec926-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec926-111">Requirements</span></span>  
 <span data-ttu-id="ec926-112">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec926-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec926-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec926-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec926-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec926-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec926-115">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec926-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec926-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec926-116">See also</span></span>

- [<span data-ttu-id="ec926-117">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ec926-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
