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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a9a647a9c77a3c1f82ae3691e2a5e5b2f544cad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645410"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="9e613-102">ICorDebugBoxValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e613-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="9e613-103">ボックス化された値クラスのオブジェクトを表す"ICorDebugHeapValue"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="9e613-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e613-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e613-104">Methods</span></span>  
  
|<span data-ttu-id="9e613-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9e613-105">Method</span></span>|<span data-ttu-id="9e613-106">説明</span><span class="sxs-lookup"><span data-stu-id="9e613-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e613-107">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="9e613-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="9e613-108">ボックス化された"ICorDebugObjectValue"インスタンスにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9e613-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e613-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e613-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e613-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9e613-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e613-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="9e613-111">Requirements</span></span>  
 <span data-ttu-id="9e613-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e613-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e613-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e613-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e613-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e613-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e613-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e613-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e613-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e613-116">See also</span></span>

- [<span data-ttu-id="9e613-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9e613-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
