---
title: ICorDebugAssembly2::IsFullyTrusted メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: bef51fe9df0f85659603c637f11ed4e856c8e01a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133952"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="1c7b6-102">ICorDebugAssembly2::IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="1c7b6-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="1c7b6-103">アセンブリにランタイムセキュリティシステムによる完全信頼が付与されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="1c7b6-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7b6-104">構文</span><span class="sxs-lookup"><span data-stu-id="1c7b6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c7b6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c7b6-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="1c7b6-106">[out] アセンブリにランタイムセキュリティシステムによる完全信頼が付与されているかどうかを `true` します。それ以外の場合は、`false`ます。</span><span class="sxs-lookup"><span data-stu-id="1c7b6-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c7b6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c7b6-107">Remarks</span></span>  
 <span data-ttu-id="1c7b6-108">アセンブリのセキュリティポリシーがまだ解決されていない場合、つまり、アセンブリ内のコードがまだ実行されていない場合は、このメソッドは CORDBG_E_NOTREADY の HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="1c7b6-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7b6-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="1c7b6-109">Requirements</span></span>  
 <span data-ttu-id="1c7b6-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c7b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7b6-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c7b6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c7b6-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c7b6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c7b6-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
