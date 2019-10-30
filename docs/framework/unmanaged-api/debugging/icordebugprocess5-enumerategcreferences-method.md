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
ms.openlocfilehash: 84b5da043f9bd437ee9099135ba865c1ab23bb9d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129670"
---
# <a name="icordebugprocess5enumerategcreferences-method"></a><span data-ttu-id="8a193-102">ICorDebugProcess5::EnumerateGCReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="8a193-102">ICorDebugProcess5::EnumerateGCReferences Method</span></span>
<span data-ttu-id="8a193-103">プロセスでガベージコレクトされるすべてのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="8a193-103">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a193-104">構文</span><span class="sxs-lookup"><span data-stu-id="8a193-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateGCReferences(  
    [in] Bool enumerateWeakReferences,   
    [out] ICorDebugGCReferenceEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a193-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a193-105">Parameters</span></span>  
 `enumerateWeakReferences`  
 <span data-ttu-id="8a193-106">から弱い参照も列挙するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="8a193-106">[in] A Boolean value that indicates whether weak references are also to be enumerated.</span></span> <span data-ttu-id="8a193-107">`enumerateWeakReferences` が `true`場合、`ppEnum` 列挙子には、厳密な参照と弱い参照の両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a193-107">If `enumerateWeakReferences` is `true`, the `ppEnum` enumerator includes both strong references and weak references.</span></span> <span data-ttu-id="8a193-108">`enumerateWeakReferences` が `false`の場合、列挙子には厳密な参照のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a193-108">If `enumerateWeakReferences` is `false`, the enumerator includes only strong references.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="8a193-109">入出力ガベージコレクションの対象となるオブジェクトの列挙子[である、](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)ツールのアドレスへのポインターです。</span><span class="sxs-lookup"><span data-stu-id="8a193-109">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a193-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="8a193-110">Remarks</span></span>  
 <span data-ttu-id="8a193-111">このメソッドは、プロセス内の任意のマネージオブジェクトの完全なルートチェーンを確認する方法を提供し、オブジェクトがまだアクティブである理由を判断するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a193-111">This method provides a way to determine the full rooting chain for any managed object in a process and can be used to determine why an object is still alive.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a193-112">［要件］</span><span class="sxs-lookup"><span data-stu-id="8a193-112">Requirements</span></span>  
 <span data-ttu-id="8a193-113">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a193-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a193-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a193-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a193-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a193-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a193-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a193-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a193-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a193-117">See also</span></span>

- [<span data-ttu-id="8a193-118">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a193-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="8a193-119">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="8a193-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
