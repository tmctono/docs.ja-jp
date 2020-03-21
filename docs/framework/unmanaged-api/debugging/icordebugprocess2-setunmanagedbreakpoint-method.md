---
title: ICorDebugProcess2::SetUnmanagedBreakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: fb8b8f3e29c141e91587a4d0cdc81cdabccdbc9e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178645"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a><span data-ttu-id="427e5-102">ICorDebugProcess2::SetUnmanagedBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="427e5-102">ICorDebugProcess2::SetUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="427e5-103">指定したネイティブ イメージ オフセットにアンマネージ ブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="427e5-103">Sets an unmanaged breakpoint at the specified native image offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="427e5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="427e5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="427e5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="427e5-106">[in]ネイティブ`CORDB_ADDRESS`イメージ オフセットを指定するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="427e5-106">[in] A `CORDB_ADDRESS` object that specifies the native image offset.</span></span>  
  
 `bufsize`  
 <span data-ttu-id="427e5-107">[in]`buffer`配列のサイズ (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="427e5-107">[in] The size, in bytes, of the `buffer` array.</span></span>  
  
 `buffer`  
 <span data-ttu-id="427e5-108">[アウト]ブレークポイントに置き換えられるオペコードを含む配列。</span><span class="sxs-lookup"><span data-stu-id="427e5-108">[out] An array that contains the opcode that is replaced by the breakpoint.</span></span>  
  
 `bufLen`  
 <span data-ttu-id="427e5-109">[アウト]`buffer`配列に返されるバイト数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="427e5-109">[out] A pointer to the number of bytes returned in the `buffer` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="427e5-110">解説</span><span class="sxs-lookup"><span data-stu-id="427e5-110">Remarks</span></span>  
 <span data-ttu-id="427e5-111">ネイティブ イメージのオフセットが共通言語ランタイム (CLR) 内にある場合、ブレークポイントは無視されます。</span><span class="sxs-lookup"><span data-stu-id="427e5-111">If the native image offset is within the common language runtime (CLR), the breakpoint will be ignored.</span></span> <span data-ttu-id="427e5-112">これにより、ブレークポイントがデバッガーによって設定されている場合、CLR は帯域外ブレークポイントをディスパッチしないようにできます。</span><span class="sxs-lookup"><span data-stu-id="427e5-112">This allows the CLR to avoid dispatching an out-of-band breakpoint, when the breakpoint is set by the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427e5-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="427e5-113">Requirements</span></span>  
 <span data-ttu-id="427e5-114">**:**「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="427e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427e5-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="427e5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="427e5-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="427e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="427e5-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
