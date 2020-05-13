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
ms.openlocfilehash: 611091d39da6d7f646457457f20ce1eaf37db361
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213206"
---
# <a name="icordebugfunction2-interface"></a><span data-ttu-id="8e324-102">ICorDebugFunction2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e324-102">ICorDebugFunction2 Interface</span></span>

<span data-ttu-id="8e324-103">マイコードのみのステップスルーデバッグをサポートするように、この関数インターフェイスを論理的に拡張します。これにより、非ユーザーコードがスキップされます。</span><span class="sxs-lookup"><span data-stu-id="8e324-103">Logically extends the ICorDebugFunction interface to provide support for Just My Code step-through debugging, which skips non-user code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8e324-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-104">Methods</span></span>  
  
|<span data-ttu-id="8e324-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-105">Method</span></span>|<span data-ttu-id="8e324-106">説明</span><span class="sxs-lookup"><span data-stu-id="8e324-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8e324-107">EnumerateNativeCode メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-107">EnumerateNativeCode Method</span></span>](icordebugfunction2-enumeratenativecode-method.md)|<span data-ttu-id="8e324-108">(実装されていません。)この ICorDebugFunction2 オブジェクトによって参照されている関数内のネイティブコードステートメントを含む、コードの型の列挙体へのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e324-108">(Not yet implemented.) Gets an interface pointer to an ICorDebugCodeEnum that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>|  
|[<span data-ttu-id="8e324-109">GetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-109">GetJMCStatus Method</span></span>](icordebugfunction2-getjmcstatus-method.md)|<span data-ttu-id="8e324-110">この関数がユーザーコードとしてマークされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="8e324-110">Gets a value that indicates whether this function is marked as user code.</span></span>|  
|[<span data-ttu-id="8e324-111">GetVersionNumber メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-111">GetVersionNumber Method</span></span>](icordebugfunction2-getversionnumber-method.md)|<span data-ttu-id="8e324-112">この関数のエディットコンティニュバージョンを取得します。</span><span class="sxs-lookup"><span data-stu-id="8e324-112">Gets the Edit and Continue version of this function.</span></span>|  
|[<span data-ttu-id="8e324-113">SetJMCStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="8e324-113">SetJMCStatus Method</span></span>](icordebugfunction2-setjmcstatus-method.md)|<span data-ttu-id="8e324-114">マイコードのみのステップ実行のために、この関数をマークします。</span><span class="sxs-lookup"><span data-stu-id="8e324-114">Marks this function for Just My Code stepping.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e324-115">Remarks</span><span class="sxs-lookup"><span data-stu-id="8e324-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e324-116">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8e324-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e324-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="8e324-117">Requirements</span></span>  
 <span data-ttu-id="8e324-118">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e324-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e324-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e324-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e324-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e324-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e324-121">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e324-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e324-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e324-122">See also</span></span>

- [<span data-ttu-id="8e324-123">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="8e324-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
