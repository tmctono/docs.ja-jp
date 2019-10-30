---
title: ICorDebugClass2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: cb2ab28824d209dd1eed627600e30e9ddb0d7c7a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125718"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="7ebc6-102">ICorDebugClass2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ebc6-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="7ebc6-103">ジェネリック、または <xref:System.Type> 型のメソッド パラメーターを持つクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="7ebc6-104">このインターフェイスは[、を](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)拡張します。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ebc6-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ebc6-105">Methods</span></span>  
  
|<span data-ttu-id="7ebc6-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="7ebc6-106">Method</span></span>|<span data-ttu-id="7ebc6-107">説明</span><span class="sxs-lookup"><span data-stu-id="7ebc6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ebc6-108">GetParameterizedType メソッド</span><span class="sxs-lookup"><span data-stu-id="7ebc6-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="7ebc6-109">このクラスの型宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="7ebc6-110">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="7ebc6-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="7ebc6-111">このクラスの各メソッドについて、メソッドがユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ebc6-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="7ebc6-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ebc6-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ebc6-114">［要件］</span><span class="sxs-lookup"><span data-stu-id="7ebc6-114">Requirements</span></span>  
 <span data-ttu-id="7ebc6-115">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ebc6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ebc6-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ebc6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ebc6-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ebc6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ebc6-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ebc6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ebc6-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="7ebc6-119">See also</span></span>

- [<span data-ttu-id="7ebc6-120">のクラスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ebc6-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="7ebc6-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="7ebc6-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
