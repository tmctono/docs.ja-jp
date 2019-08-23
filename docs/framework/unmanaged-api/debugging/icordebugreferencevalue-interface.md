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
ms.openlocfilehash: 67006603747abd89f1b635c065860dcbe1c47a29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965644"
---
# <a name="icordebugreferencevalue-interface"></a><span data-ttu-id="08819-102">ICorDebugReferenceValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08819-102">ICorDebugReferenceValue Interface</span></span>
<span data-ttu-id="08819-103">オブジェクトへの参照である値を管理するメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="08819-103">Provides methods that manage a value that is a reference to an object.</span></span> <span data-ttu-id="08819-104">(つまり、このインターフェイスには、ポインターを管理するメソッドが用意されています)。このインターフェイスは、"ICorDebugValue" を実装します。</span><span class="sxs-lookup"><span data-stu-id="08819-104">(That is, this interface provides methods that manage a pointer.) This interface implements "ICorDebugValue".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08819-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-105">Methods</span></span>  
  
|<span data-ttu-id="08819-106">メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-106">Method</span></span>|<span data-ttu-id="08819-107">説明</span><span class="sxs-lookup"><span data-stu-id="08819-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08819-108">Dereference メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-108">Dereference Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereference-method.md)|<span data-ttu-id="08819-109">参照されているオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="08819-109">Gets the object that is referenced.</span></span>|  
|[<span data-ttu-id="08819-110">DereferenceStrong メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-110">DereferenceStrong Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-dereferencestrong-method.md)|<span data-ttu-id="08819-111">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="08819-111">Not implemented.</span></span> <span data-ttu-id="08819-112">このメソッドを呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="08819-112">Do not call this method.</span></span>|  
|[<span data-ttu-id="08819-113">GetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-113">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-getvalue-method.md)|<span data-ttu-id="08819-114">参照先のオブジェクトの現在のメモリアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="08819-114">Gets the current memory address of the referenced object.</span></span>|  
|[<span data-ttu-id="08819-115">IsNull メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-115">IsNull Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-isnull-method.md)|<span data-ttu-id="08819-116">このが null 値であるか`ICorDebugReferenceValue`どうかを示す値を取得します`ICorDebugReferenceValue` 。この値を指定した場合、はオブジェクトをポイントしません。</span><span class="sxs-lookup"><span data-stu-id="08819-116">Gets a value that indicates whether this `ICorDebugReferenceValue` is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>|  
|[<span data-ttu-id="08819-117">SetValue メソッド</span><span class="sxs-lookup"><span data-stu-id="08819-117">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-setvalue-method.md)|<span data-ttu-id="08819-118">現在のメモリアドレスを設定します。</span><span class="sxs-lookup"><span data-stu-id="08819-118">Sets the current memory address.</span></span> <span data-ttu-id="08819-119">つまり、このメソッドは、オブジェクト`ICorDebugReferenceValue`を指すようにこれを設定します。</span><span class="sxs-lookup"><span data-stu-id="08819-119">That is, this method sets this `ICorDebugReferenceValue` to point to an object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08819-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="08819-120">Remarks</span></span>  
 <span data-ttu-id="08819-121">共通言語ランタイム (CLR) は、デバッグされたプロセスが続行されると、オブジェクトのガベージコレクションを実行する場合があります。</span><span class="sxs-lookup"><span data-stu-id="08819-121">The common language runtime (CLR) may do a garbage collection on objects when the debugged process is continued.</span></span> <span data-ttu-id="08819-122">ガベージコレクションでは、メモリ内でオブジェクトを移動できます。</span><span class="sxs-lookup"><span data-stu-id="08819-122">The garbage collection may move objects around in memory.</span></span> <span data-ttu-id="08819-123">`ICorDebugReferenceValue`はガベージコレクションと連携して、ガベージコレクションの後に情報が更新されるか、ガベージコレクションの前に暗黙的に無効にされます。</span><span class="sxs-lookup"><span data-stu-id="08819-123">An `ICorDebugReferenceValue` will either cooperate with the garbage collection so that its information is updated after the garbage collection, or it will be invalidated implicitly before the garbage collection.</span></span>  
  
 <span data-ttu-id="08819-124">デバッグ`ICorDebugReferenceValue`されたプロセスが続行されると、オブジェクトは暗黙的に無効になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08819-124">The `ICorDebugReferenceValue` object may be implicitly invalidated after the debugged process has been continued.</span></span> <span data-ttu-id="08819-125">派生された "の値" は、明示的に解放または公開されるまで無効になりません。</span><span class="sxs-lookup"><span data-stu-id="08819-125">The derived "ICorDebugHandleValue" is not invalidated until it is explicitly released or exposed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08819-126">このインターフェイスは、コンピューター間またはプロセス間でのリモート呼び出しをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="08819-126">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08819-127">必要条件</span><span class="sxs-lookup"><span data-stu-id="08819-127">Requirements</span></span>  
 <span data-ttu-id="08819-128">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="08819-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08819-129">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="08819-129">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08819-130">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="08819-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08819-131">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08819-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08819-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="08819-132">See also</span></span>

- [<span data-ttu-id="08819-133">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="08819-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
