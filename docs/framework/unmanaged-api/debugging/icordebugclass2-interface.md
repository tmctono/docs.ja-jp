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
ms.openlocfilehash: 1f6a8b0ead430ffdd0e4e30cacae54d68fa9d730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969263"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="2b396-102">ICorDebugClass2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b396-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="2b396-103">ジェネリック、または <xref:System.Type> 型のメソッド パラメーターを持つクラスを表します。</span><span class="sxs-lookup"><span data-stu-id="2b396-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2b396-104">このインターフェイスは[、を](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)拡張します。</span><span class="sxs-lookup"><span data-stu-id="2b396-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2b396-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b396-105">Methods</span></span>  
  
|<span data-ttu-id="2b396-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="2b396-106">Method</span></span>|<span data-ttu-id="2b396-107">説明</span><span class="sxs-lookup"><span data-stu-id="2b396-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2b396-108">GetParameterizedType メソッド</span><span class="sxs-lookup"><span data-stu-id="2b396-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="2b396-109">このクラスの型宣言を取得します。</span><span class="sxs-lookup"><span data-stu-id="2b396-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="2b396-110">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="2b396-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="2b396-111">このクラスの各メソッドについて、メソッドがユーザー定義のコードかどうかを示す値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2b396-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b396-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="2b396-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b396-113">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2b396-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b396-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="2b396-114">Requirements</span></span>  
 <span data-ttu-id="2b396-115">**・**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b396-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b396-116">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="2b396-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b396-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="2b396-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b396-118">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b396-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b396-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2b396-119">See also</span></span>

- [<span data-ttu-id="2b396-120">のクラスインターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b396-120">ICorDebugClass Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="2b396-121">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2b396-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
