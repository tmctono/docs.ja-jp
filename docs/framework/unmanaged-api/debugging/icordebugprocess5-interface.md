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
ms.openlocfilehash: 31ecea4857dabc55e8acd3c22a025895a686efcd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931087"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="e10fd-102">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10fd-102">ICorDebugProcess5 Interface</span></span>
<span data-ttu-id="e10fd-103">は、アプリケーションインターフェイスを拡張して、マネージヒープへのアクセスをサポートし、マネージオブジェクトのガベージコレクションに関する情報を提供し、デバッガーがアプリケーションのローカルネイティブイメージキャッシュからイメージを読み込むかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e10fd-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-104">Methods</span></span>  
  
|<span data-ttu-id="e10fd-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-105">Method</span></span>|<span data-ttu-id="e10fd-106">説明</span><span class="sxs-lookup"><span data-stu-id="e10fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e10fd-107">EnableNGENPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-107">EnableNGenPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="e10fd-108">マネージデバッガーで実行中にアプリケーションがネイティブイメージを読み込む方法を決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="e10fd-109">EnumerateGCReferences メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-109">EnumerateGCReferences Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="e10fd-110">プロセスでガベージコレクトされるすべてのオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="e10fd-111">EnumerateHandles メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-111">EnumerateHandles Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="e10fd-112">プロセス内のオブジェクトハンドルの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="e10fd-113">EnumerateHeap メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-113">EnumerateHeap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="e10fd-114">マネージヒープ上のオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="e10fd-115">EnumerateHeapRegions メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-115">EnumerateHeapRegions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="e10fd-116">マネージヒープの領域の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="e10fd-117">GetArrayLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-117">GetArrayLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="e10fd-118">メモリ内の配列のレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="e10fd-119">GetGCHeapInformation メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-119">GetGCHeapInformation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="e10fd-120">マネージヒープでガベージコレクトされるオブジェクトに関する情報を格納している[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)構造体へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-120">Gets a pointer to a [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="e10fd-121">GetObject メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-121">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md)|<span data-ttu-id="e10fd-122">マネージヒープ上のオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="e10fd-123">GetTypeFields メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-123">GetTypeFields Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="e10fd-124">型の識別子に基づいて、型のフィールド情報を格納している配列へのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="e10fd-125">GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-125">GetTypeForTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="e10fd-126">型識別子に基づいてオブジェクトに関する情報を提供する型オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="e10fd-127">GetTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-127">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="e10fd-128">指定したアドレスにあるオブジェクトの型識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="e10fd-129">GetTypeLayout メソッド</span><span class="sxs-lookup"><span data-stu-id="e10fd-129">GetTypeLayout Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="e10fd-130">型識別子に基づいて、メモリ内のオブジェクトのレイアウトに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e10fd-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="e10fd-131">Remarks</span></span>  
 <span data-ttu-id="e10fd-132">このインターフェイスは、ICorDebugProcess、ICorDebugProcess2、および [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) の各インターフェイスを論理的に拡張します。</span><span class="sxs-lookup"><span data-stu-id="e10fd-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e10fd-133">このインターフェイスは、別のコンピューターまたは別のプロセスからのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e10fd-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e10fd-134">必要条件</span><span class="sxs-lookup"><span data-stu-id="e10fd-134">Requirements</span></span>  
 <span data-ttu-id="e10fd-135">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e10fd-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e10fd-136">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="e10fd-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e10fd-137">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="e10fd-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e10fd-138">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e10fd-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e10fd-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="e10fd-139">See also</span></span>

- [<span data-ttu-id="e10fd-140">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e10fd-140">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e10fd-141">デバッグ</span><span class="sxs-lookup"><span data-stu-id="e10fd-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
