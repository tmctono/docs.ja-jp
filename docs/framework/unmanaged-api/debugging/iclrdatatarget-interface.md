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
ms.openlocfilehash: 30806394a8895084068acaec6f7d03c6b67bb14b
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860566"
---
# <a name="iclrdatatarget-interface"></a><span data-ttu-id="306f8-102">ICLRDataTarget インターフェイス</span><span class="sxs-lookup"><span data-stu-id="306f8-102">ICLRDataTarget Interface</span></span>
<span data-ttu-id="306f8-103">共通言語ランタイム (CLR) のターゲット項目と対話するためのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="306f8-103">Provides methods for interaction with a target item of the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="306f8-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-104">Methods</span></span>  
  
|<span data-ttu-id="306f8-105">Method</span><span class="sxs-lookup"><span data-stu-id="306f8-105">Method</span></span>|<span data-ttu-id="306f8-106">説明</span><span class="sxs-lookup"><span data-stu-id="306f8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="306f8-107">GetCurrentThreadID メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-107">GetCurrentThreadID Method</span></span>](iclrdatatarget-getcurrentthreadid-method.md)|<span data-ttu-id="306f8-108">現在のスレッドのオペレーティングシステム id を取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-108">Gets the operating system identifier for the current thread.</span></span>|  
|[<span data-ttu-id="306f8-109">GetImageBase メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-109">GetImageBase Method</span></span>](iclrdatatarget-getimagebase-method.md)|<span data-ttu-id="306f8-110">指定したイメージのベースメモリアドレスを取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-110">Gets the base memory address for the specified image.</span></span>|  
|[<span data-ttu-id="306f8-111">GetMachineType メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-111">GetMachineType Method</span></span>](iclrdatatarget-getmachinetype-method.md)|<span data-ttu-id="306f8-112">ターゲットプロセスが使用している命令セットの種類の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-112">Gets an identifier for the kind of instruction set that the target process is using.</span></span>|  
|[<span data-ttu-id="306f8-113">GetPointerSize メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-113">GetPointerSize Method</span></span>](iclrdatatarget-getpointersize-method.md)|<span data-ttu-id="306f8-114">現在のターゲットへのポインターのサイズ (バイト単位) を取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-114">Gets the size, in bytes, of a pointer to the current target.</span></span>|  
|[<span data-ttu-id="306f8-115">GetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-115">GetThreadContext Method</span></span>](iclrdatatarget-getthreadcontext-method.md)|<span data-ttu-id="306f8-116">指定した識別子を持つスレッドのコンテキストへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-116">Gets a pointer to the context of the thread with the specified identifier.</span></span>|  
|[<span data-ttu-id="306f8-117">GetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-117">GetTLSValue Method</span></span>](iclrdatatarget-gettlsvalue-method.md)|<span data-ttu-id="306f8-118">指定したスレッドの指定したインデックスにあるスレッドローカルストレージ (TLS) の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="306f8-118">Gets a value in thread local storage (TLS) at the specified index for the specified thread.</span></span>|  
|[<span data-ttu-id="306f8-119">ReadVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-119">ReadVirtual Method</span></span>](iclrdatatarget-readvirtual-method.md)|<span data-ttu-id="306f8-120">指定された仮想メモリアドレスから指定されたバッファーにデータを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="306f8-120">Reads data from the specified virtual memory address into the specified buffer.</span></span>|  
|[<span data-ttu-id="306f8-121">要求メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-121">Request Method</span></span>](iclrdatatarget-request-method.md)|<span data-ttu-id="306f8-122">実装で定義されているように、操作を要求するために、共通言語ランタイム (CLR) データアクセスサービスによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="306f8-122">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>|  
|[<span data-ttu-id="306f8-123">SetThreadContext メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-123">SetThreadContext Method</span></span>](iclrdatatarget-setthreadcontext-method.md)|<span data-ttu-id="306f8-124">ターゲットプロセス内の指定されたスレッドの現在のコンテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="306f8-124">Sets the current context of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="306f8-125">SetTLSValue メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-125">SetTLSValue Method</span></span>](iclrdatatarget-settlsvalue-method.md)|<span data-ttu-id="306f8-126">ターゲットプロセス内の指定したスレッドのスレッドローカルストレージ (TLS) の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="306f8-126">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span>|  
|[<span data-ttu-id="306f8-127">WriteVirtual メソッド</span><span class="sxs-lookup"><span data-stu-id="306f8-127">WriteVirtual Method</span></span>](iclrdatatarget-writevirtual-method.md)|<span data-ttu-id="306f8-128">指定されたバッファーから指定された仮想メモリアドレスにデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="306f8-128">Writes data from the specified buffer to the specified virtual memory address.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="306f8-129">解説</span><span class="sxs-lookup"><span data-stu-id="306f8-129">Remarks</span></span>  
 <span data-ttu-id="306f8-130">API クライアント (つまり、デバッガー) は、特定のターゲット項目に適した方法でこのインターフェイスを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="306f8-130">The API client (that is, the debugger) must implement this interface as appropriate for the particular target item.</span></span> <span data-ttu-id="306f8-131">たとえば、ライブ プロセスの実装は、メモリ ダンプの実装とは異なります。</span><span class="sxs-lookup"><span data-stu-id="306f8-131">For example, a live process would have an implementation different from that of a memory dump.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="306f8-132">必要条件</span><span class="sxs-lookup"><span data-stu-id="306f8-132">Requirements</span></span>  
 <span data-ttu-id="306f8-133">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="306f8-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306f8-134">**ヘッダー:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="306f8-134">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="306f8-135">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="306f8-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="306f8-136">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306f8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306f8-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="306f8-137">See also</span></span>

- [<span data-ttu-id="306f8-138">ICLRDataTarget2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="306f8-138">ICLRDataTarget2 Interface</span></span>](iclrdatatarget2-interface.md)
- [<span data-ttu-id="306f8-139">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="306f8-139">Debugging Interfaces</span></span>](debugging-interfaces.md)
