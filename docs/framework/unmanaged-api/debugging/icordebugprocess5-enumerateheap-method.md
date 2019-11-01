---
title: ICorDebugProcess5::EnumerateHeap メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type:
- apiref
ms.openlocfilehash: c8cfc9cdf6580a002f6ac15080012a9e8c63be20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129650"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="f3ada-102">ICorDebugProcess5::EnumerateHeap メソッド</span><span class="sxs-lookup"><span data-stu-id="f3ada-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="f3ada-103">マネージヒープ上のオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="f3ada-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3ada-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3ada-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3ada-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3ada-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="f3ada-106">入出力マネージヒープ上に存在するオブジェクト[の列挙子](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)である、コードオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="f3ada-106">[out] A pointer to the address of an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3ada-107">コメント</span><span class="sxs-lookup"><span data-stu-id="f3ada-107">Remarks</span></span>  
 <span data-ttu-id="f3ada-108">`ICorDebugProcess5::EnumerateHeap` メソッドを呼び出す前に、 [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md)メソッドを呼び出し、返された[COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)オブジェクトの次のフィールド `areGCStructuresValid` の値を調べて、ガベージコレクションヒープが現在の状態は列挙可能です。</span><span class="sxs-lookup"><span data-stu-id="f3ada-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="f3ada-109">さらに、`ICorDebugProcess5::EnumerateHeap` は、マネージヒープのメモリが割り当てられる前に、プロセスの有効期間が早すぎた場合に `E_FAIL` を返します。</span><span class="sxs-lookup"><span data-stu-id="f3ada-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="f3ada-110">[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) [Heapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)インターフェイスオブジェクトは、ICorDebugEnum インターフェイスから派生した標準列挙子で、 オブジェクトを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="f3ada-110">The [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="f3ada-111">このメソッド[は、すべてのオブジェクト](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)に関する情報を提供する[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを使用して、このコレクションオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3ada-111">This method populates the [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="f3ada-112">コレクションには、オブジェクトによってルートされていないが、まだガベージコレクターによって収集されていないオブジェクトに関する情報を提供する[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)インスタンスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="f3ada-112">The collection may also include [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3ada-113">要件</span><span class="sxs-lookup"><span data-stu-id="f3ada-113">Requirements</span></span>  
 <span data-ttu-id="f3ada-114">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3ada-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ada-115">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f3ada-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3ada-116">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="f3ada-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3ada-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ada-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ada-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3ada-118">See also</span></span>

- [<span data-ttu-id="f3ada-119">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3ada-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="f3ada-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3ada-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
