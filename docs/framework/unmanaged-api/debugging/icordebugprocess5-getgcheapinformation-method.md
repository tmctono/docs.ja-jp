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
ms.openlocfilehash: 3aa9fe884b16a239f5105dd262edeb8fc3e4abaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084407"
---
# <a name="icordebugprocess5getgcheapinformation-method"></a><span data-ttu-id="cf479-102">ICorDebugProcess5::GetGCHeapInformation メソッド</span><span class="sxs-lookup"><span data-stu-id="cf479-102">ICorDebugProcess5::GetGCHeapInformation Method</span></span>
<span data-ttu-id="cf479-103">現在列挙可能であるかどうかなど、ガベージコレクションヒープに関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="cf479-103">Provides general information about the garbage collection heap, including whether it is currently enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf479-104">構文</span><span class="sxs-lookup"><span data-stu-id="cf479-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGCHeapInformation(  
    [out] COR_HEAPINFO *pHeapInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf479-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cf479-105">Parameters</span></span>  
 `pHeapInfo`  
 <span data-ttu-id="cf479-106">入出力ガベージコレクションヒープに関する一般的な情報を提供する[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)値へのポインター。</span><span class="sxs-lookup"><span data-stu-id="cf479-106">[out] A pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) value that provides general information about the garbage collection heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf479-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="cf479-107">Remarks</span></span>  
 <span data-ttu-id="cf479-108">プロセス内のガベージコレクション構造が現在有効であることを確認するには、ヒープまたは個々のヒープ領域を列挙する前に、`ICorDebugProcess5::GetGCHeapInformation` メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf479-108">The `ICorDebugProcess5::GetGCHeapInformation` method must be called before enumerating the heap or individual heap regions to ensure that the garbage collection structures in the process are currently valid.</span></span> <span data-ttu-id="cf479-109">コレクションの実行中にガベージコレクションヒープをウォークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="cf479-109">The garbage collection heap cannot be walked while a collection is in progress.</span></span> <span data-ttu-id="cf479-110">それ以外の場合、列挙体は無効なガベージコレクション構造をキャプチャする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf479-110">Otherwise, the enumeration may capture garbage collection structures that are invalid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf479-111">［要件］</span><span class="sxs-lookup"><span data-stu-id="cf479-111">Requirements</span></span>  
 <span data-ttu-id="cf479-112">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf479-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf479-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf479-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf479-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf479-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf479-115">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf479-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf479-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf479-116">See also</span></span>

- [<span data-ttu-id="cf479-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf479-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="cf479-118">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="cf479-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
