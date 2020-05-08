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
ms.openlocfilehash: 12dc5466d5be73b327f171c389c41c55901f2915
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894952"
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="96764-102">ICorDebugAssembly::EnumerateModules メソッド</span><span class="sxs-lookup"><span data-stu-id="96764-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="96764-103">に格納されているモジュールの列挙`ICorDebugAssembly`子を取得します。</span><span class="sxs-lookup"><span data-stu-id="96764-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96764-104">構文</span><span class="sxs-lookup"><span data-stu-id="96764-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96764-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96764-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="96764-106">入出力列挙子である、モジュールの列挙型インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="96764-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96764-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="96764-107">Requirements</span></span>  
 <span data-ttu-id="96764-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96764-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96764-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="96764-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96764-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96764-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96764-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96764-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
