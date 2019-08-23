---
title: ICorDebugFunction2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2
helpviewer_keywords:
- ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 2b936bef-9b75-48bf-859f-42e419c65f1c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4349ad4dbaeafa63689ef85a307211428f8538
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917087"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="8f2e2-102">ICorDebugFunction2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f2e2-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="8f2e2-103">マイコードのみのステップスルーデバッグをサポートするように、この関数インターフェイスを論理的に拡張します。これにより、非ユーザーコードがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f2e2-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-104">Methods</span></span>  
  
|<span data-ttu-id="8f2e2-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-105">Method</span></span>|<span data-ttu-id="8f2e2-106">説明</span><span class="sxs-lookup"><span data-stu-id="8f2e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f2e2-107">EnumerateNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="8f2e2-108">(実装されていません。)この ICorDebugFunction2 オブジェクトによって参照されている関数内のネイティブコードステートメントを含む、コードの型の列挙体へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="8f2e2-109">GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="8f2e2-110">この関数がユーザーコードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="8f2e2-111">GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="8f2e2-112">この関数のエディットコンティニュバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="8f2e2-113">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="8f2e2-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="8f2e2-114">マイコードのみのステップ実行のために、この関数をマークします。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f2e2-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8f2e2-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f2e2-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f2e2-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8f2e2-117">Requirements</span></span>  
 <span data-ttu-id="8f2e2-118">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f2e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f2e2-119">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8f2e2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f2e2-120">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="8f2e2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f2e2-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f2e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f2e2-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8f2e2-122">See also</span></span>

- [<span data-ttu-id="8f2e2-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8f2e2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
