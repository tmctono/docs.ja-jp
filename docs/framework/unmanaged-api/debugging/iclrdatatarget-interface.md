---
title: ICLRDataTarget インターフェイス
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113491"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="9d8af-102">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d8af-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="9d8af-103">共通言語ランタイム (CLR) のターゲット項目と対話するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d8af-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-104">Methods</span></span>  
  
|<span data-ttu-id="9d8af-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-105">Method</span></span>|<span data-ttu-id="9d8af-106">説明</span><span class="sxs-lookup"><span data-stu-id="9d8af-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d8af-107">GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-107">GetCurrentThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="9d8af-108">現在のスレッドのオペレーティングシステム id を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="9d8af-109">GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-109">GetImageBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="9d8af-110">指定したイメージのベースメモリアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="9d8af-111">GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-111">GetMachineType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="9d8af-112">ターゲットプロセスが使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="9d8af-113">GetPointerSize メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-113">GetPointerSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="9d8af-114">現在のターゲットへのポインターのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="9d8af-115">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-115">GetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="9d8af-116">指定した識別子を持つスレッドのコンテキストへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="9d8af-117">GetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-117">GetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="9d8af-118">指定したスレッドの指定したインデックスにあるスレッドローカルストレージ (TLS) の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="9d8af-119">ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-119">ReadVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="9d8af-120">指定された仮想メモリアドレスから指定されたバッファーにデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="9d8af-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="9d8af-121">Request メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-121">Request Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|<span data-ttu-id="9d8af-122">実装で定義されているように、操作を要求するために、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="9d8af-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="9d8af-123">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-123">SetThreadContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="9d8af-124">ターゲットプロセス内の指定されたスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="9d8af-125">SetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-125">SetTLSValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="9d8af-126">ターゲットプロセス内の指定したスレッドのスレッドローカルストレージ (TLS) の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="9d8af-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="9d8af-127">WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="9d8af-127">WriteVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="9d8af-128">指定されたバッファーから指定された仮想メモリアドレスにデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9d8af-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d8af-129">Remarks</span><span class="sxs-lookup"><span data-stu-id="9d8af-129">Remarks</span></span>  
 <span data-ttu-id="9d8af-130">API クライアント (つまり、デバッガー) は、特定のターゲット項目に適した方法でこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d8af-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="9d8af-131">たとえば、ライブ プロセスの実装は、メモリ ダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="9d8af-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d8af-132">［要件］</span><span class="sxs-lookup"><span data-stu-id="9d8af-132">Requirements</span></span>  
 <span data-ttu-id="9d8af-133">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d8af-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d8af-134">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="9d8af-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9d8af-135">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d8af-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d8af-136">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d8af-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d8af-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d8af-137">See also</span></span>

- [<span data-ttu-id="9d8af-138">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d8af-138">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [<span data-ttu-id="9d8af-139">デバッグ インターフェイス</span><span class="sxs-lookup"><span data-stu-id="9d8af-139">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
