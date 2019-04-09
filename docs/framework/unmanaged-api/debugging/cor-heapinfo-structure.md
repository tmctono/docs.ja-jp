---
title: COR_HEAPINFO 構造体
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090356"
---
# <a name="corheapinfo-structure"></a><span data-ttu-id="d9c78-102">COR_HEAPINFO 構造体</span><span class="sxs-lookup"><span data-stu-id="d9c78-102">COR_HEAPINFO Structure</span></span>
<span data-ttu-id="d9c78-103">列挙可能かどうかなど、ガベージ コレクション ヒープに関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d9c78-103">Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9c78-104">構文</span><span class="sxs-lookup"><span data-stu-id="d9c78-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a><span data-ttu-id="d9c78-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d9c78-105">Members</span></span>  
  
|<span data-ttu-id="d9c78-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d9c78-106">Member</span></span>|<span data-ttu-id="d9c78-107">説明</span><span class="sxs-lookup"><span data-stu-id="d9c78-107">Description</span></span>|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` <span data-ttu-id="d9c78-108">ガベージ コレクションの構造体が有効な場合に、ヒープを列挙することができます。それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="d9c78-108">if garbage collection structures are valid and the heap can be enumerated; otherwise, `false`.</span></span>|  
|`pointerSize`|<span data-ttu-id="d9c78-109">ターゲット アーキテクチャ上のポインターのバイト単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="d9c78-109">The size, in bytes, of pointers on the target architecture.</span></span>|  
|`numHeaps`|<span data-ttu-id="d9c78-110">プロセスのヒープの論理のガベージ コレクションの数。</span><span class="sxs-lookup"><span data-stu-id="d9c78-110">The number of logical garbage collection heaps in the process.</span></span>|  
|`concurrent`|`TRUE` <span data-ttu-id="d9c78-111">同時実行の場合 (背景) のガベージ コレクションが有効になっているとします。それ以外の場合、`FALSE`します。</span><span class="sxs-lookup"><span data-stu-id="d9c78-111">if concurrent (background) garbage collection is enabled; otherwise, `FALSE`.</span></span>|  
|`gcType`|<span data-ttu-id="d9c78-112">メンバー、 [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md)ガベージ コレクターがワークステーションまたはサーバーで実行されているかどうかを示す列挙体。</span><span class="sxs-lookup"><span data-stu-id="d9c78-112">A member of the [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumeration that indicates whether the garbage collector is running on a workstation or a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9c78-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="d9c78-113">Remarks</span></span>  
 <span data-ttu-id="d9c78-114">インスタンス、`COR_HEAPINFO`構造体が呼び出しによって返される、 [icordebugprocess 5::getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d9c78-114">An instance of the `COR_HEAPINFO` structure is returned by calling the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
 <span data-ttu-id="d9c78-115">ガベージ コレクション ヒープ上のオブジェクトを列挙するには、前に常にオンにしてください、`areGCStructuresValid`フィールドをヒープが列挙可能な状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d9c78-115">Before enumerating objects on the garbage collection heap, you must always check the `areGCStructuresValid` field to ensure that the heap is in an enumerable state.</span></span> <span data-ttu-id="d9c78-116">詳細については、次を参照してください。、 [icordebugprocess 5::getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッド。</span><span class="sxs-lookup"><span data-stu-id="d9c78-116">For more information, see the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9c78-117">必要条件</span><span class="sxs-lookup"><span data-stu-id="d9c78-117">Requirements</span></span>  
 <span data-ttu-id="d9c78-118">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9c78-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9c78-119">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9c78-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9c78-120">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9c78-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d9c78-121">.NET Framework のバージョン: </span><span class="sxs-lookup"><span data-stu-id="d9c78-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9c78-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9c78-122">See also</span></span>

- [<span data-ttu-id="d9c78-123">デバッグ構造体</span><span class="sxs-lookup"><span data-stu-id="d9c78-123">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d9c78-124">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d9c78-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
