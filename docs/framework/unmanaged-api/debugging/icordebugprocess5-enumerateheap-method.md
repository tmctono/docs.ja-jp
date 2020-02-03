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
ms.openlocfilehash: 780f9eb0984e35c4487d770b5e7ff33917cf07ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792414"
---
# <a name="icordebugprocess5enumerateheap-method"></a><span data-ttu-id="5ff1b-102">ICorDebugProcess5::EnumerateHeap メソッド</span><span class="sxs-lookup"><span data-stu-id="5ff1b-102">ICorDebugProcess5::EnumerateHeap Method</span></span>
<span data-ttu-id="5ff1b-103">マネージヒープ上のオブジェクトの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-103">Gets an enumerator for the objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff1b-104">構文</span><span class="sxs-lookup"><span data-stu-id="5ff1b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff1b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ff1b-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="5ff1b-106">入出力マネージヒープ上に存在するオブジェクト[の列挙子](icordebugheapenum-interface.md)である、コードオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-106">[out] A pointer to the address of an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is an enumerator for the objects that reside on the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ff1b-107">コメント</span><span class="sxs-lookup"><span data-stu-id="5ff1b-107">Remarks</span></span>  
 <span data-ttu-id="5ff1b-108">`ICorDebugProcess5::EnumerateHeap` メソッドを呼び出す前に、 [ICorDebugProcess5:: Getg](icordebugprocess5-getgcheapinformation-method.md)メソッドを呼び出し、返された[COR_HEAPINFO](cor-heapinfo-structure.md)オブジェクトの `areGCStructuresValid` フィールドの値を調べて、現在の状態のガベージコレクションヒープが列挙可能であることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-108">Before calling the `ICorDebugProcess5::EnumerateHeap` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="5ff1b-109">さらに、`ICorDebugProcess5::EnumerateHeap` は、マネージヒープのメモリが割り当てられる前に、プロセスの有効期間が早すぎた場合に `E_FAIL` を返します。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-109">In addition, the `ICorDebugProcess5::EnumerateHeap` returns `E_FAIL` if you attach too early in the lifetime of the process, before memory for the managed heap is allocated.</span></span>  
  
 <span data-ttu-id="5ff1b-110">は[、ICorDebugEnum](icordebugheapenum-interface.md)インターフェイスから派生した標準列挙子であり、 [COR_HEAPOBJECT](cor-heapobject-structure.md)オブジェクトを列挙できます。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-110">The [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_HEAPOBJECT](cor-heapobject-structure.md) objects.</span></span> <span data-ttu-id="5ff1b-111">このメソッド[は、すべてのオブジェクト](icordebugheapenum-interface.md)に関する情報を提供する[COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスを使用して、このコレクションオブジェクトを設定します。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-111">This method populates the [ICorDebugHeapEnum](icordebugheapenum-interface.md) collection object with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about all objects.</span></span> <span data-ttu-id="5ff1b-112">コレクションには、オブジェクトによってルートされていないが、まだガベージコレクターによって収集されていないオブジェクトに関する情報を提供する[COR_HEAPOBJECT](cor-heapobject-structure.md)インスタンスを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-112">The collection may also include [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that provide information about objects that are not rooted by any object but have not yet been collected by the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff1b-113">要件</span><span class="sxs-lookup"><span data-stu-id="5ff1b-113">Requirements</span></span>  
 <span data-ttu-id="5ff1b-114">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ff1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff1b-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ff1b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ff1b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff1b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff1b-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ff1b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff1b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5ff1b-118">See also</span></span>

- [<span data-ttu-id="5ff1b-119">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ff1b-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="5ff1b-120">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ff1b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
