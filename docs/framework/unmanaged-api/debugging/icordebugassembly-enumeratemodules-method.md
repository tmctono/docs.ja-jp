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
ms.openlocfilehash: b55bd41039fce84a21c5d651d93b56f5d84b7611
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088180"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="26fda-102">ICorDebugAssembly::EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="26fda-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="26fda-103">`ICorDebugAssembly`に格納されているモジュールの列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="26fda-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26fda-104">構文</span><span class="sxs-lookup"><span data-stu-id="26fda-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26fda-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="26fda-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="26fda-106">入出力列挙子である、モジュールの列挙型インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="26fda-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26fda-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="26fda-107">Requirements</span></span>  
 <span data-ttu-id="26fda-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26fda-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26fda-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26fda-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26fda-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26fda-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26fda-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26fda-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
