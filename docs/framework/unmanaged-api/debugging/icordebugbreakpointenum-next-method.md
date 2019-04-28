---
title: ICorDebugBreakpointEnum::Next メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b65eb3e733fa7970e4c0e7de09755598eaf149
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645345"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="776b7-102">ICorDebugBreakpointEnum::Next メソッド</span><span class="sxs-lookup"><span data-stu-id="776b7-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="776b7-103">現在の位置から始まり、列挙体から ICorDebugBreakpoint インスタンスの指定した数を取得します。</span><span class="sxs-lookup"><span data-stu-id="776b7-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="776b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="776b7-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="776b7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="776b7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="776b7-106">[in]数`ICorDebugBreakpoint`インスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="776b7-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="776b7-107">[out]それぞれが指すポインターの配列、`ICorDebugBreakpoint`ブレークポイントを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="776b7-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="776b7-108">[out]数へのポインター`ICorDebugBreakpoint`インスタンスが実際に返されます。</span><span class="sxs-lookup"><span data-stu-id="776b7-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="776b7-109">この値は null になる場合`celt`は 1 つです。</span><span class="sxs-lookup"><span data-stu-id="776b7-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="776b7-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="776b7-110">Requirements</span></span>  
 <span data-ttu-id="776b7-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="776b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="776b7-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="776b7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="776b7-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="776b7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="776b7-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="776b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
