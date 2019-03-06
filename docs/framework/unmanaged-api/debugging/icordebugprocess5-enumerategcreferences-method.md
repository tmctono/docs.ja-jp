---
title: ICorDebugProcess5::EnumerateGCReferences メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateGCReferences
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateGCReferences
helpviewer_keywords:
- EnumerateGCReferences method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateGCReferences method [.NET Framework debugging]
ms.assetid: 86c397c3-81d8-463e-a248-3cbe06c44d9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e2648765d896c189cc2deb5590a0a2a9b3f410
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476486"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="70243-102">ICorDebugProcess5::EnumerateGCReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="70243-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="70243-103">プロセスでガベージ コレクトされるすべてのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="70243-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70243-104">構文</span><span class="sxs-lookup"><span data-stu-id="70243-104">Syntax</span></span>  
  
```  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70243-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="70243-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="70243-106">[in]弱い参照を列挙するもあるかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="70243-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="70243-107">場合`enumerateWeakReferences`は`true`、`ppEnum`列挙子には、強い参照と弱い参照の両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="70243-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="70243-108">場合`enumerateWeakReferences`は`false`、列挙子には、強力な参照のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="70243-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="70243-109">[out]アドレスへのポインター、 [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)ガベージ コレクトされる列挙子は、オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="70243-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70243-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="70243-110">Remarks</span></span>  
 <span data-ttu-id="70243-111">このメソッドは、プロセス内の任意のマネージ オブジェクトのルートの完全なチェーンを決定する方法を提供し、オブジェクトがまだ有効な状態の理由を特定するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="70243-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70243-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="70243-112">Requirements</span></span>  
 <span data-ttu-id="70243-113">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="70243-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70243-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70243-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70243-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70243-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70243-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70243-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70243-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="70243-117">See also</span></span>
- [<span data-ttu-id="70243-118">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70243-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="70243-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="70243-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
