---
title: ICorDebugFunction::CreateBreakpoint メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695ce7f25813a191c74bec6563fc7f8ae8d1143d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496119"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="a4cff-102">ICorDebugFunction::CreateBreakpoint メソッド</span><span class="sxs-lookup"><span data-stu-id="a4cff-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="a4cff-103">この関数の先頭にブレークポイントを作成します。</span><span class="sxs-lookup"><span data-stu-id="a4cff-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4cff-104">構文</span><span class="sxs-lookup"><span data-stu-id="a4cff-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4cff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a4cff-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="a4cff-106">[out]関数の新しいブレークポイントを表す ICorDebugFunctionBreakpoint オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="a4cff-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4cff-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a4cff-107">Requirements</span></span>  
 <span data-ttu-id="a4cff-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4cff-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4cff-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4cff-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4cff-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4cff-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4cff-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4cff-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
