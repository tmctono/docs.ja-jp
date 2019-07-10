---
title: ICorDebugAppDomain::EnumerateBreakpoints メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateBreakpoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a683f1531ed28fbd8ef085414bb7cb365762ffde
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738046"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="25c8d-102">ICorDebugAppDomain::EnumerateBreakpoints メソッド</span><span class="sxs-lookup"><span data-stu-id="25c8d-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="25c8d-103">アプリケーション ドメインですべてのアクティブなブレークポイントの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="25c8d-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25c8d-104">構文</span><span class="sxs-lookup"><span data-stu-id="25c8d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25c8d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="25c8d-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="25c8d-106">[out]アプリケーション ドメイン内のすべてのアクティブなブレークポイントの列挙子である ICorDebugBreakpointEnum オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="25c8d-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25c8d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="25c8d-107">Remarks</span></span>  
 <span data-ttu-id="25c8d-108">列挙子には、すべての種類関数のブレークポイント、データ ブレークポイントを含む、ブレークポイントにはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="25c8d-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25c8d-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="25c8d-109">Requirements</span></span>  
 <span data-ttu-id="25c8d-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="25c8d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25c8d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25c8d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25c8d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25c8d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25c8d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25c8d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
