---
title: ICorDebugAppDomain::EnumerateSteppers メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateSteppers
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateSteppers
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateSteppers method [.NET Framework debugging]
- EnumerateSteppers method [.NET Framework debugging]
ms.assetid: 3f3c4503-570e-44c1-ae6a-a3c6b840c732
topic_type:
- apiref
ms.openlocfilehash: a46d1b4ebf84514a77e62a4108f6aa34cd2dd94e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895262"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="047a2-102">ICorDebugAppDomain::EnumerateSteppers メソッド</span><span class="sxs-lookup"><span data-stu-id="047a2-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="047a2-103">アプリケーションドメイン内のすべてのアクティブな steppers の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="047a2-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="047a2-104">構文</span><span class="sxs-lookup"><span data-stu-id="047a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="047a2-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="047a2-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="047a2-106">入出力アプリケーションドメイン内のすべてのアクティブな steppers の列挙子である、ツールオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="047a2-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="047a2-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="047a2-107">Requirements</span></span>  
 <span data-ttu-id="047a2-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="047a2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="047a2-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="047a2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="047a2-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="047a2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="047a2-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="047a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
