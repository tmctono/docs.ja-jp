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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d231595ab2c7b41d1a24f654e9785b90b34ac780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744506"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="0f3ee-102">ICorDebugAssembly2::IsFullyTrusted メソッド</span><span class="sxs-lookup"><span data-stu-id="0f3ee-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="0f3ee-103">かどうか、アセンブリで許可されている完全な信頼ランタイムのセキュリティ システムを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="0f3ee-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f3ee-104">構文</span><span class="sxs-lookup"><span data-stu-id="0f3ee-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f3ee-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0f3ee-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="0f3ee-106">[out]`true`場合は、アセンブリで許可されている完全な信頼ランタイムのセキュリティ システムです。 それ以外の場合、`false`します。</span><span class="sxs-lookup"><span data-stu-id="0f3ee-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f3ee-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0f3ee-107">Remarks</span></span>  
 <span data-ttu-id="0f3ee-108">このメソッドは、HRESULT の CORDBG_E_NOTREADY アセンブリのセキュリティ ポリシーはまだ解決されていません、つまり、アセンブリでコードが見つからない場合はまだ実行されているを返します。</span><span class="sxs-lookup"><span data-stu-id="0f3ee-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f3ee-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0f3ee-109">Requirements</span></span>  
 <span data-ttu-id="0f3ee-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f3ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f3ee-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f3ee-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f3ee-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f3ee-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f3ee-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f3ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
