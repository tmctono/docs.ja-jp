---
title: ICorDebugProcess5 インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5904083be66d4bd6dc69729bebc28db8a800e77
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948682"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="22dce-102">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22dce-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="22dce-103">管理対象のオブジェクトのガベージ コレクションに関する情報を提供する、マネージ ヒープへのアクセスをサポートするために ICorDebugProcess インターフェイスを拡張し、デバッガーがかどうかを判断するには、アプリケーションのローカル ネイティブ イメージ キャッシュからイメージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="22dce-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22dce-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-104">Methods</span></span>  
  
|<span data-ttu-id="22dce-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-105">Method</span></span>|<span data-ttu-id="22dce-106">説明</span><span class="sxs-lookup"><span data-stu-id="22dce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22dce-107">EnableNGENPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="22dce-108">アプリケーションがマネージ デバッガーで実行中にネイティブ イメージを読み込む方法を決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="22dce-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="22dce-109">EnumerateGCReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="22dce-110">プロセスでガベージ コレクトされるすべてのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="22dce-111">EnumerateHandles メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="22dce-112">プロセスでオブジェクト ハンドルの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="22dce-113">EnumerateHeap メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="22dce-114">マネージ ヒープのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="22dce-115">EnumerateHeapRegions メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="22dce-116">マネージ ヒープの領域の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="22dce-117">GetArrayLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="22dce-118">メモリ内配列のレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="22dce-119">GetGCHeapInformation メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="22dce-120">ポインターを取得、 [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)マネージ ヒープ上でガベージ コレクトされるオブジェクトに関する情報を含む構造体。</span><span class="sxs-lookup"><span data-stu-id="22dce-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="22dce-121">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="22dce-122">マネージ ヒープにオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="22dce-123">GetTypeFields メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="22dce-124">その型の識別子に基づく型のフィールド情報を格納する配列にポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="22dce-125">GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="22dce-126">その型の識別子に基づくオブジェクトに関する情報を提供する型のオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="22dce-127">GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="22dce-128">指定したアドレスにオブジェクトの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="22dce-129">GetTypeLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="22dce-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="22dce-130">その型の識別子に基づくメモリ内のオブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="22dce-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22dce-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="22dce-131">Remarks</span></span>  
 <span data-ttu-id="22dce-132">このインターフェイスは ICorDebugProcess、ICorDebugProcess2、論理的に拡張し、 [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="22dce-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22dce-133">このインターフェイスは、別のコンピューターまたは別のプロセスでのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="22dce-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22dce-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="22dce-134">Requirements</span></span>  
 <span data-ttu-id="22dce-135">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22dce-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22dce-136">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22dce-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22dce-137">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22dce-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22dce-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22dce-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22dce-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="22dce-139">See also</span></span>

- [<span data-ttu-id="22dce-140">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="22dce-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="22dce-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="22dce-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
