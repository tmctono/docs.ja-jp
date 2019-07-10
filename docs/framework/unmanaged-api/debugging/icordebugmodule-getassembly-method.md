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
ms.openlocfilehash: 8ee602c85a2f591365d40984184780f70e8532bf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762703"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="7d6d3-102">ICorDebugModule::GetAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="7d6d3-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="7d6d3-103">このモジュールを格納しているアセンブリを取得します。</span><span class="sxs-lookup"><span data-stu-id="7d6d3-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d6d3-104">構文</span><span class="sxs-lookup"><span data-stu-id="7d6d3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d6d3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7d6d3-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="7d6d3-106">[out]このモジュールを含むアセンブリを表す ICorDebugAssembly オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7d6d3-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d6d3-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="7d6d3-107">Requirements</span></span>  
 <span data-ttu-id="7d6d3-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d6d3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d6d3-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d6d3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d6d3-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d6d3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d6d3-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d6d3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
