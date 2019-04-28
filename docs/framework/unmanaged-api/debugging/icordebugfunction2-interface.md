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
ms.openlocfilehash: 159cebc76f732629ed84a3b6c9041cc15f8bbb69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763764"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="e5bf3-102">ICorDebugFunction2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5bf3-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="e5bf3-103">非ユーザー コードがスキップされ、デバッグのステップをマイ コードのみをサポートする ICorDebugFunction インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5bf3-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-104">Methods</span></span>  
  
|<span data-ttu-id="e5bf3-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-105">Method</span></span>|<span data-ttu-id="e5bf3-106">説明</span><span class="sxs-lookup"><span data-stu-id="e5bf3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5bf3-107">EnumerateNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="e5bf3-108">(実装されていません。)ICorDebugFunction2 オブジェクトによって参照されている関数のネイティブ コードのステートメントを含む、ICorDebugCodeEnum にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="e5bf3-109">GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="e5bf3-110">この関数がユーザー コードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="e5bf3-111">GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="e5bf3-112">この関数のエディット コンティニュ バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="e5bf3-113">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="e5bf3-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="e5bf3-114">マイ コードのみのマークをこの関数のステップ インします。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5bf3-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5bf3-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5bf3-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5bf3-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="e5bf3-117">Requirements</span></span>  
 <span data-ttu-id="e5bf3-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5bf3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5bf3-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5bf3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5bf3-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5bf3-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5bf3-121">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5bf3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5bf3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5bf3-122">See also</span></span>

- [<span data-ttu-id="e5bf3-123">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e5bf3-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
