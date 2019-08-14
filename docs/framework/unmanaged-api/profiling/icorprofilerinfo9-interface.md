---
title: ICorProfilerInfo9 インターフェイス
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 0ba4f2b4a515143d50bc812f04ea75d821b69471
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973802"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="5736f-102">ICorProfilerInfo9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5736f-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="5736f-103">複数のネイティブコードバージョンを持つ関数に関する情報を照会するメソッドを提供する[ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)のサブクラス。</span><span class="sxs-lookup"><span data-stu-id="5736f-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="5736f-104">メソッド</span><span class="sxs-lookup"><span data-stu-id="5736f-104">Methods</span></span>  

| <span data-ttu-id="5736f-105">メソッド</span><span class="sxs-lookup"><span data-stu-id="5736f-105">Method</span></span>|<span data-ttu-id="5736f-106">説明</span><span class="sxs-lookup"><span data-stu-id="5736f-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="5736f-107">GetNativeCodeStartAddresses メソッド</span><span class="sxs-lookup"><span data-stu-id="5736f-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="5736f-108">指定された functionId と rejitId は、現在存在する、このコードのすべての just-in-time バージョンのネイティブコードの開始アドレスを列挙します。</span><span class="sxs-lookup"><span data-stu-id="5736f-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="5736f-109">GetILToNativeMapping3 メソッド</span><span class="sxs-lookup"><span data-stu-id="5736f-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="5736f-110">ネイティブコードの開始アドレスが指定されている場合、この just-in-time バージョンのコードのネイティブから IL へのマッピング情報を返します。</span><span class="sxs-lookup"><span data-stu-id="5736f-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="5736f-111">GetCodeInfo4 メソッド</span><span class="sxs-lookup"><span data-stu-id="5736f-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="5736f-112">ネイティブコードの開始アドレスを指定すると、このコードを格納する仮想メモリのブロックが返されます。</span><span class="sxs-lookup"><span data-stu-id="5736f-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="5736f-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="5736f-113">Requirements</span></span>  
<span data-ttu-id="5736f-114">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5736f-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
<span data-ttu-id="5736f-115">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="5736f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="5736f-116">**.Net のバージョン:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5736f-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  
## <a name="see-also"></a><span data-ttu-id="5736f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5736f-117">See also</span></span>
- [<span data-ttu-id="5736f-118">プロファイリングのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5736f-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
