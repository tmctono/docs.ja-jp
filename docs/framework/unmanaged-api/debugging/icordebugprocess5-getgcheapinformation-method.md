---
title: ICorDebugProcess5::GetGCHeapInformation メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetGCHeapInformation
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetGCHeapInformation
helpviewer_keywords:
- ICorDebugProcess5::GetGCHeapInformation method [.NET Framework debugging]
- GetGCHeapInformation method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: b9538ceb-230a-4079-9cb2-903dbf5c1848
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e94034fcdcd8d86f34c61af30a7729a80c913fac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767338"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="b7cbf-102">ICorDebugProcess5::GetGCHeapInformation メソッド</span><span class="sxs-lookup"><span data-stu-id="b7cbf-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="b7cbf-103">現在の列挙可能かどうかなど、ガベージ コレクション ヒープに関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7cbf-104">構文</span><span class="sxs-lookup"><span data-stu-id="b7cbf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7cbf-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b7cbf-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="b7cbf-106">[out]ポインターを[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)ガベージ コレクション ヒープに関する一般的な情報を提供する値。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7cbf-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b7cbf-107">Remarks</span></span>  
 <span data-ttu-id="b7cbf-108">`ICorDebugProcess5::GetGCHeapInformation`ヒープを列挙する前にメソッドを呼び出す必要がありますまたは構造体のガベージ コレクションには、プロセスのことを確認するための個々 のヒープ領域は、現在有効です。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="b7cbf-109">コレクションが進行中は、ガベージ コレクション ヒープを処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="b7cbf-110">それ以外の場合、列挙体は、無効なガベージ コレクションの構造をキャプチャする場合があります。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7cbf-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="b7cbf-111">Requirements</span></span>  
 <span data-ttu-id="b7cbf-112">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b7cbf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7cbf-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7cbf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7cbf-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7cbf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7cbf-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7cbf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cbf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b7cbf-116">See also</span></span>

- [<span data-ttu-id="b7cbf-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7cbf-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="b7cbf-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="b7cbf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
