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
ms.openlocfilehash: dd82709064fe7f7d912d93f4b3f0248769f02b9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894882"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="266f8-102">ICorDebugAssembly2::IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="266f8-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="266f8-103">アセンブリにランタイムセキュリティシステムによる完全信頼が付与されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="266f8-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="266f8-104">構文</span><span class="sxs-lookup"><span data-stu-id="266f8-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="266f8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="266f8-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="266f8-106">入出力`true`アセンブリにランタイムセキュリティシステムによる完全信頼が付与されている場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="266f8-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="266f8-107">解説</span><span class="sxs-lookup"><span data-stu-id="266f8-107">Remarks</span></span>  
 <span data-ttu-id="266f8-108">このメソッドは、アセンブリのセキュリティポリシーがまだ解決されていない場合、つまりアセンブリ内のコードがまだ実行されていない場合に、CORDBG_E_NOTREADY の HRESULT を返します。</span><span class="sxs-lookup"><span data-stu-id="266f8-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="266f8-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="266f8-109">Requirements</span></span>  
 <span data-ttu-id="266f8-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="266f8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="266f8-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="266f8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="266f8-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="266f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="266f8-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="266f8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
