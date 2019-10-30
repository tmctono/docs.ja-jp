---
title: ICorDebugAppDomain::IsAttached メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134669"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="98635-102">ICorDebugAppDomain::IsAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="98635-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="98635-103">デバッガーがアプリケーションドメインにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="98635-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98635-104">構文</span><span class="sxs-lookup"><span data-stu-id="98635-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98635-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="98635-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="98635-106">[out] デバッガーがアプリケーションドメインにアタッチされている場合は `true`それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="98635-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98635-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="98635-107">Remarks</span></span>  
 <span data-ttu-id="98635-108">このデバッガーがアプリケーションドメインにアタッチされるまでは、このコントロールメソッドを使用できません。</span><span class="sxs-lookup"><span data-stu-id="98635-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98635-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="98635-109">Requirements</span></span>  
 <span data-ttu-id="98635-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98635-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98635-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98635-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98635-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98635-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98635-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98635-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
