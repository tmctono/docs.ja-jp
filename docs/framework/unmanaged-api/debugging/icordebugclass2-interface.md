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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46358a66d79030aeea42c75827f05cf07fa925ea
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967751"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="54f2d-102">ICorDebugClass2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54f2d-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="54f2d-103">ジェネリック、または <xref:System.Type> 型のメソッド パラメーターを持つクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="54f2d-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="54f2d-104">このインターフェイスは拡張[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)します。</span><span class="sxs-lookup"><span data-stu-id="54f2d-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54f2d-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="54f2d-105">Methods</span></span>  
  
|<span data-ttu-id="54f2d-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="54f2d-106">Method</span></span>|<span data-ttu-id="54f2d-107">説明</span><span class="sxs-lookup"><span data-stu-id="54f2d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54f2d-108">GetParameterizedType メソッド</span><span class="sxs-lookup"><span data-stu-id="54f2d-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="54f2d-109">このクラスの型宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="54f2d-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="54f2d-110">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="54f2d-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="54f2d-111">このクラスの各メソッドでは、メソッドは、ユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="54f2d-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54f2d-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="54f2d-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54f2d-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="54f2d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54f2d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="54f2d-114">Requirements</span></span>  
 <span data-ttu-id="54f2d-115">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54f2d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54f2d-116">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54f2d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54f2d-117">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54f2d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54f2d-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54f2d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54f2d-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="54f2d-119">See also</span></span>
- [<span data-ttu-id="54f2d-120">ICorDebugClass インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54f2d-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="54f2d-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="54f2d-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
