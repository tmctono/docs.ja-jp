---
title: ICorDebugCode::CreateBreakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugCode.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::CreateBreakpoint
helpviewer_keywords:
- ICorDebugCode::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 46842618-0fe4-480b-871c-82fba82d23d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ec7d615b99ac301948d7ea25318115713ce06ea
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700843"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="3fdc3-102">ICorDebugCode::CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="3fdc3-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="3fdc3-103">このコードセグメントの指定したオフセット位置にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdc3-104">構文</span><span class="sxs-lookup"><span data-stu-id="3fdc3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fdc3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3fdc3-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="3fdc3-106">からブレークポイントを作成する位置のオフセット。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="3fdc3-107">入出力ブレークポイントを表す "いいね! ブレークポイント" オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fdc3-108">コメント</span><span class="sxs-lookup"><span data-stu-id="3fdc3-108">Remarks</span></span>  
 <span data-ttu-id="3fdc3-109">ブレークポイントがアクティブになる前に、そのブレークポイントをプロセスオブジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="3fdc3-110">このコードが Microsoft 中間言語 (MSIL) コードで、just-in-time (JIT) でコンパイルされたネイティブバージョンのコードがある場合、ブレークポイントは JIT コンパイルコードにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="3fdc3-111">(コードが後で JIT コンパイルされる場合も同様です)。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdc3-112">要件</span><span class="sxs-lookup"><span data-stu-id="3fdc3-112">Requirements</span></span>  
 <span data-ttu-id="3fdc3-113">**・** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3fdc3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fdc3-114">**ヘッダー:** CorDebug .idl、CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="3fdc3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fdc3-115">**ライブラリ**CorGuids .lib</span><span class="sxs-lookup"><span data-stu-id="3fdc3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fdc3-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fdc3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
