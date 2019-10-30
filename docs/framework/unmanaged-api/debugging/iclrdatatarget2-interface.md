---
title: ICLRDataTarget2 インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: 1f0f4331302e56a90b4aefd657e07981994022ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112313"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="9bbcb-102">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bbcb-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="9bbcb-103">ターゲットプロセスの仮想メモリ領域を操作するためにデータアクセスサービス層によって使用される[ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-103">A subclass of [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9bbcb-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9bbcb-104">Methods</span></span>  
  
|<span data-ttu-id="9bbcb-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9bbcb-105">Method</span></span>|<span data-ttu-id="9bbcb-106">説明</span><span class="sxs-lookup"><span data-stu-id="9bbcb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bbcb-107">AllocVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="9bbcb-107">AllocVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="9bbcb-108">ターゲットプロセスのアドレス空間にメモリを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="9bbcb-109">FreeVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="9bbcb-109">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="9bbcb-110">ターゲットプロセスのアドレス空間で以前に割り当てられたメモリを解放します。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bbcb-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="9bbcb-111">Remarks</span></span>  
 <span data-ttu-id="9bbcb-112">API クライアント (つまりデバッガー) は、特定のターゲット プロセスに応じてこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="9bbcb-113">たとえば、ライブ プロセスの実装は、メモリ ダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="9bbcb-114">ターゲットは、メモリ領域の変更をサポートしない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bbcb-115">［要件］</span><span class="sxs-lookup"><span data-stu-id="9bbcb-115">Requirements</span></span>  
 <span data-ttu-id="9bbcb-116">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bbcb-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bbcb-117">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="9bbcb-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9bbcb-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bbcb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bbcb-119">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bbcb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbcb-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="9bbcb-120">See also</span></span>

- [<span data-ttu-id="9bbcb-121">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bbcb-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
- [<span data-ttu-id="9bbcb-122">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9bbcb-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
