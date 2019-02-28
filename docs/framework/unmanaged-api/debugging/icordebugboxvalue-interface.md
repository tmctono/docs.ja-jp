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
ms.openlocfilehash: f7238574334b599c7922693c7e9a476a51785491
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967327"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="489cb-102">ICorDebugBoxValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="489cb-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="489cb-103">ボックス化された値クラスのオブジェクトを表す"ICorDebugHeapValue"のサブクラスです。</span><span class="sxs-lookup"><span data-stu-id="489cb-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="489cb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="489cb-104">Methods</span></span>  
  
|<span data-ttu-id="489cb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="489cb-105">Method</span></span>|<span data-ttu-id="489cb-106">説明</span><span class="sxs-lookup"><span data-stu-id="489cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="489cb-107">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="489cb-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="489cb-108">ボックス化された"ICorDebugObjectValue"インスタンスにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="489cb-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="489cb-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="489cb-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="489cb-110">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="489cb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489cb-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="489cb-111">Requirements</span></span>  
 <span data-ttu-id="489cb-112">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="489cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="489cb-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="489cb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="489cb-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="489cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="489cb-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="489cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489cb-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="489cb-116">See also</span></span>
- [<span data-ttu-id="489cb-117">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="489cb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
