---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 46ceef43806fda9956797935c5eeec61f865dc6e
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973792"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="11484-102">ICorProfilerInfo9:: GetILToNativeMapping3 メソッド</span><span class="sxs-lookup"><span data-stu-id="11484-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>
  
 <span data-ttu-id="11484-103">ネイティブコードの開始アドレスが指定されている場合、この just-in-time バージョンのコードのネイティブから IL へのマッピング情報を返します。</span><span class="sxs-lookup"><span data-stu-id="11484-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="11484-104">構文</span><span class="sxs-lookup"><span data-stu-id="11484-104">Syntax</span></span>  
  
```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="11484-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11484-105">Parameters</span></span>  
 `pNativeCodeStartAddress` \
 <span data-ttu-id="11484-106">からネイティブ関数の先頭へのポインター。</span><span class="sxs-lookup"><span data-stu-id="11484-106">[in] A pointer to the start of a native function.</span></span>

 `cMap` \
 <span data-ttu-id="11484-107">[in] `map` 配列の最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="11484-107">[in] The maximum size of the `map` array.</span></span> 

 `pcMap` \
 <span data-ttu-id="11484-108">入出力使用できる COR_DEBUG_IL_TO_NATIVE_MAP 構造体の合計数。</span><span class="sxs-lookup"><span data-stu-id="11484-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

 `map` \
 <span data-ttu-id="11484-109">入出力[COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md)構造体の配列。それぞれがオフセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="11484-109">[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="11484-110">`GetILToNativeMapping3` メソッドから制御が戻ると、`COR_DEBUG_IL_TO_NATIVE_MAP` 構造体の一部または全部が `map` に格納されます。</span><span class="sxs-lookup"><span data-stu-id="11484-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="11484-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="11484-111">Remarks</span></span>  
 <span data-ttu-id="11484-112">階層化コンパイルが有効になっている場合、メソッドは複数のネイティブコード本体を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="11484-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="11484-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)は、すべてのネイティブコード本体の開始アドレスを返します。</span><span class="sxs-lookup"><span data-stu-id="11484-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="11484-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="11484-114">Requirements</span></span>  
 <span data-ttu-id="11484-115">**・** 「 [.Net Core でサポートされるオペレーティングシステム](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11484-115">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="11484-116">**ヘッダー:** Corprof.idl、Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="11484-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="11484-117">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="11484-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11484-118">**.NET Framework のバージョン:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11484-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="11484-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="11484-119">See also</span></span>
- [<span data-ttu-id="11484-120">ICorProfilerInfo9 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="11484-120">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

