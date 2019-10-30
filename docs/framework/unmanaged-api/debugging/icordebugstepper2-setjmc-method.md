---
title: ICorDebugStepper2::SetJMC メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139039"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="d2aa1-102">ICorDebugStepper2::SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="d2aa1-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="d2aa1-103">この ICorDebugStepper が、アプリケーションの開発者によって作成されたコードのみを使用するかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="d2aa1-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="d2aa1-104">このプロセスは、"マイコードのみ" (JMC) デバッグとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d2aa1-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2aa1-105">構文</span><span class="sxs-lookup"><span data-stu-id="d2aa1-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2aa1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d2aa1-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="d2aa1-107">からアプリケーションの開発者によって作成されたコードのみをステップ実行するには、`true` に設定します。それ以外の場合は、を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="d2aa1-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2aa1-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="d2aa1-108">Requirements</span></span>  
 <span data-ttu-id="d2aa1-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d2aa1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2aa1-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2aa1-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2aa1-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2aa1-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2aa1-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2aa1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
