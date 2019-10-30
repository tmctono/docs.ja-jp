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
ms.openlocfilehash: 3611684a17d51fc4fdba31dd4049540039b43e8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110516"
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="3806d-102">ICorDebugAppDomain::EnumerateBreakpoints メソッド</span><span class="sxs-lookup"><span data-stu-id="3806d-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="3806d-103">アプリケーションドメイン内のすべてのアクティブなブレークポイントの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="3806d-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3806d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3806d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3806d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3806d-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="3806d-106">入出力アプリケーションドメイン内のすべてのアクティブなブレークポイントの列挙子である、の各オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3806d-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3806d-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3806d-107">Remarks</span></span>  
 <span data-ttu-id="3806d-108">列挙子には、関数ブレークポイントやデータブレークポイントなど、すべての種類のブレークポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3806d-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3806d-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="3806d-109">Requirements</span></span>  
 <span data-ttu-id="3806d-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3806d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3806d-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3806d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3806d-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3806d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3806d-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3806d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
