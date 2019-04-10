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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199376"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="3480a-102">ICorDebugFunction2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="3480a-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="3480a-103">非ユーザー コードがスキップされ、デバッグのステップをマイ コードのみをサポートする ICorDebugFunction インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="3480a-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3480a-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-104">Methods</span></span>  
  
|<span data-ttu-id="3480a-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-105">Method</span></span>|<span data-ttu-id="3480a-106">説明</span><span class="sxs-lookup"><span data-stu-id="3480a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3480a-107">EnumerateNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-107">EnumerateNativeCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="3480a-108">(実装されていません。)ICorDebugFunction2 オブジェクトによって参照されている関数のネイティブ コードのステートメントを含む、ICorDebugCodeEnum にインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3480a-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="3480a-109">GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-109">GetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="3480a-110">この関数がユーザー コードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="3480a-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="3480a-111">GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-111">GetVersionNumber Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="3480a-112">この関数のエディット コンティニュ バージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="3480a-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="3480a-113">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="3480a-113">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="3480a-114">マイ コードのみのマークをこの関数のステップ インします。</span><span class="sxs-lookup"><span data-stu-id="3480a-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3480a-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="3480a-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3480a-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3480a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3480a-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="3480a-117">Requirements</span></span>  
 <span data-ttu-id="3480a-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3480a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3480a-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3480a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3480a-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3480a-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3480a-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="3480a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3480a-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="3480a-122">See also</span></span>

- [<span data-ttu-id="3480a-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="3480a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
