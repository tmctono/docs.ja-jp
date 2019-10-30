---
title: ICorDebugModule::GetAssembly メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: 29c9d9dde4776ef729c0bbae7b644171a265e3ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137462"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="ad936-102">ICorDebugModule::GetAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="ad936-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="ad936-103">このモジュールの格納アセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="ad936-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad936-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad936-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad936-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad936-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="ad936-106">入出力このモジュールを格納しているアセンブリを表す、オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="ad936-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad936-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="ad936-107">Requirements</span></span>  
 <span data-ttu-id="ad936-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad936-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad936-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad936-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad936-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad936-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad936-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad936-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
