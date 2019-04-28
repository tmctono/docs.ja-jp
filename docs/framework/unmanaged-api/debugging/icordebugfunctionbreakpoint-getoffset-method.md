---
title: ICorDebugFunctionBreakpoint::GetOffset メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6253191340c2f2d4f42f47d580b9d923ab3ff041
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651689"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="8ba07-102">ICorDebugFunctionBreakpoint::GetOffset メソッド</span><span class="sxs-lookup"><span data-stu-id="8ba07-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="8ba07-103">関数内でのブレークポイントのオフセットを取得します。</span><span class="sxs-lookup"><span data-stu-id="8ba07-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba07-104">構文</span><span class="sxs-lookup"><span data-stu-id="8ba07-104">Syntax</span></span>  
  
```  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba07-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8ba07-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="8ba07-106">[out]ブレークポイントのオフセットへのポインター。</span><span class="sxs-lookup"><span data-stu-id="8ba07-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba07-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="8ba07-107">Requirements</span></span>  
 <span data-ttu-id="8ba07-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ba07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba07-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ba07-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ba07-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ba07-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ba07-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ba07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
