---
title: ICorDebugReferenceValue インターフェイス
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue
helpviewer_keywords:
- ICorDebugReferenceValue interface [.NET Framework debugging]
ms.assetid: 2040e2be-119a-4cfb-ae52-b0b6f052665c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6575acfb1f75cbc8e3d59ddca5fea0953274cf2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206461"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="57cad-102">ICorDebugReferenceValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57cad-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="57cad-103">オブジェクトへの参照である値を管理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="57cad-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="57cad-104">(つまり、このインターフェイスはポインターを管理するメソッドを提供します。)このインターフェイスは、"ICorDebugValue"を実装します。</span><span class="sxs-lookup"><span data-stu-id="57cad-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57cad-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-105">Methods</span></span>  
  
|<span data-ttu-id="57cad-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-106">Method</span></span>|<span data-ttu-id="57cad-107">説明</span><span class="sxs-lookup"><span data-stu-id="57cad-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57cad-108">Dereference メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="57cad-109">参照されているオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="57cad-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="57cad-110">DereferenceStrong メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="57cad-111">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="57cad-111">Not implemented.</span></span> <span data-ttu-id="57cad-112">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="57cad-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="57cad-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="57cad-114">参照先オブジェクトの現在のメモリ アドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="57cad-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="57cad-115">IsNull メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="57cad-116">示す値を取得するかどうかこの`ICorDebugReferenceValue`、null 値の場合は、`ICorDebugReferenceValue`がオブジェクトを指していません。</span><span class="sxs-lookup"><span data-stu-id="57cad-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="57cad-117">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="57cad-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="57cad-118">現在のメモリ アドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="57cad-118">Sets the current memory address.</span></span> <span data-ttu-id="57cad-119">つまり、このメソッドはこの設定`ICorDebugReferenceValue`オブジェクトを指すようにします。</span><span class="sxs-lookup"><span data-stu-id="57cad-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57cad-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="57cad-120">Remarks</span></span>  
 <span data-ttu-id="57cad-121">共通言語ランタイム (CLR) は、デバッグ対象のプロセスが続行すると、オブジェクトのガベージ コレクションを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="57cad-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="57cad-122">ガベージ コレクションは、メモリ内の周りオブジェクトを移動可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57cad-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="57cad-123">`ICorDebugReferenceValue`はいずれかと連携してガベージ コレクション、ガベージ コレクション後にその情報が更新またはガベージ コレクションの前に暗黙的に無効にできるようにします。</span><span class="sxs-lookup"><span data-stu-id="57cad-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="57cad-124">`ICorDebugReferenceValue`デバッグ対象のプロセスが続行されるした後にオブジェクトが暗黙的に検証済みにすることがあります。</span><span class="sxs-lookup"><span data-stu-id="57cad-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="57cad-125">明示的に解放または公開されるまでは、派生"ICorDebugHandleValue"は無効化されません。</span><span class="sxs-lookup"><span data-stu-id="57cad-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57cad-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="57cad-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57cad-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="57cad-127">Requirements</span></span>  
 <span data-ttu-id="57cad-128">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="57cad-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57cad-129">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57cad-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57cad-130">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57cad-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57cad-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57cad-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57cad-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="57cad-132">See also</span></span>

- [<span data-ttu-id="57cad-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="57cad-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
