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
ms.openlocfilehash: 07f8be1a1831bc00eea3cfb659b46b67b6a78711
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747722"
---
# <a name="icordebugcodecreatebreakpoint-method"></a><span data-ttu-id="ec238-102">ICorDebugCode::CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="ec238-102">ICorDebugCode::CreateBreakpoint Method</span></span>
<span data-ttu-id="ec238-103">指定したオフセットには、このコード セグメントでは、ブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ec238-103">Creates a breakpoint in this code segment at the specified offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec238-104">構文</span><span class="sxs-lookup"><span data-stu-id="ec238-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [in] ULONG32     offset,  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec238-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ec238-105">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="ec238-106">[in]ブレークポイントを作成するオフセットです。</span><span class="sxs-lookup"><span data-stu-id="ec238-106">[in] The offset at which to create the breakpoint.</span></span>  
  
 `ppBreakpoint`  
 <span data-ttu-id="ec238-107">[out]ブレークポイントを表す"ICorDebugFunctionBreakpoint"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ec238-107">[out] A pointer to the address of an "ICorDebugFunctionBreakpoint" object that represents the breakpoint.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec238-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="ec238-108">Remarks</span></span>  
 <span data-ttu-id="ec238-109">前に、ブレークポイントがアクティブでは、プロセス オブジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec238-109">Before the breakpoint is active, it must be added to the process object.</span></span>  
  
 <span data-ttu-id="ec238-110">このコードは、Microsoft intermediate language (MSIL) コードでは、およびの just-in-time (JIT) があるかどうか、コードの JIT コンパイルにも、ブレークポイント、コードのコンパイル済みのネイティブのバージョンが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ec238-110">If this code is Microsoft intermediate language (MSIL) code, and there is a just-in-time (JIT)-compiled, native version of the code, the breakpoint will be applied in the JIT-compiled code as well.</span></span> <span data-ttu-id="ec238-111">(同じは、コードが JIT コンパイルされた後では、true を返します。)</span><span class="sxs-lookup"><span data-stu-id="ec238-111">(The same is true if the code is JIT-compiled later.)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec238-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="ec238-112">Requirements</span></span>  
 <span data-ttu-id="ec238-113">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec238-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec238-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec238-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec238-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec238-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec238-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec238-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec238-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec238-117">See also</span></span>
