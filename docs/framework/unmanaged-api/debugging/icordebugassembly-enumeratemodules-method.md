---
title: ICorDebugAssembly::EnumerateModules メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.EnumerateModules
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f763151f4e450c48eb9304936541243af06bdca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485318"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="55a05-102">ICorDebugAssembly::EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="55a05-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="55a05-103">含まれるモジュールの列挙子を取得、`ICorDebugAssembly`します。</span><span class="sxs-lookup"><span data-stu-id="55a05-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a05-104">構文</span><span class="sxs-lookup"><span data-stu-id="55a05-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55a05-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="55a05-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="55a05-106">[out]列挙子である ICorDebugModuleEnum インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="55a05-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a05-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="55a05-107">Requirements</span></span>  
 <span data-ttu-id="55a05-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55a05-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a05-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55a05-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55a05-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55a05-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55a05-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
