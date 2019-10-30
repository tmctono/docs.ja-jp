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
ms.openlocfilehash: a736990188023031eb8df5a76dd16fcc289cfe20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134032"
---
# <a name="icordebugappdomainenumeratesteppers-method"></a><span data-ttu-id="56a11-102">ICorDebugAppDomain::EnumerateSteppers メソッド</span><span class="sxs-lookup"><span data-stu-id="56a11-102">ICorDebugAppDomain::EnumerateSteppers Method</span></span>
<span data-ttu-id="56a11-103">アプリケーションドメイン内のすべてのアクティブな steppers の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="56a11-103">Gets an enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56a11-104">構文</span><span class="sxs-lookup"><span data-stu-id="56a11-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateSteppers (  
    [out] ICorDebugStepperEnum   **ppSteppers  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56a11-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="56a11-105">Parameters</span></span>  
 `ppSteppers`  
 <span data-ttu-id="56a11-106">入出力アプリケーションドメイン内のすべてのアクティブな steppers の列挙子である、ツールオブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="56a11-106">[out] A pointer to the address of an ICorDebugStepperEnum object that is the enumerator for all active steppers in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56a11-107">［要件］</span><span class="sxs-lookup"><span data-stu-id="56a11-107">Requirements</span></span>  
 <span data-ttu-id="56a11-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56a11-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56a11-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56a11-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56a11-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56a11-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56a11-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56a11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
