---
title: ICorDebugChain::IsManaged メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
ms.openlocfilehash: 55036fcdbd186f91c0e94fb05f3023cf614751f7
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894248"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="88479-102">ICorDebugChain::IsManaged メソッド</span><span class="sxs-lookup"><span data-stu-id="88479-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="88479-103">このチェーンでマネージコードが実行されているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="88479-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88479-104">構文</span><span class="sxs-lookup"><span data-stu-id="88479-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88479-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="88479-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="88479-106">入出力`true`このチェーンでマネージコードが実行されている場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="88479-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88479-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="88479-107">Requirements</span></span>  
 <span data-ttu-id="88479-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88479-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88479-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="88479-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="88479-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="88479-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="88479-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88479-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
