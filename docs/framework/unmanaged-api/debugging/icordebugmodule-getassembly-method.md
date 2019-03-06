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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce1e42d74dc611032d941e833bb8f248a56488b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486254"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="1fb2b-102">ICorDebugModule::GetAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="1fb2b-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="1fb2b-103">このモジュールを格納しているアセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="1fb2b-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb2b-104">構文</span><span class="sxs-lookup"><span data-stu-id="1fb2b-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fb2b-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fb2b-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="1fb2b-106">[out]このモジュールを含むアセンブリを表す ICorDebugAssembly オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="1fb2b-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb2b-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="1fb2b-107">Requirements</span></span>  
 <span data-ttu-id="1fb2b-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fb2b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb2b-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fb2b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fb2b-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb2b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb2b-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
