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
ms.openlocfilehash: ab1351af042aba5042cc7a04614bc3cf14f7d7ae
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379462"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="91fa8-102">ICorDebugStepper2::SetJMC メソッド</span><span class="sxs-lookup"><span data-stu-id="91fa8-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="91fa8-103">この ICorDebugStepper が、アプリケーションの開発者によって作成されたコードのみを使用するかどうかを指定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="91fa8-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="91fa8-104">このプロセスは、"マイコードのみ" (JMC) デバッグとも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="91fa8-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91fa8-105">構文</span><span class="sxs-lookup"><span data-stu-id="91fa8-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91fa8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="91fa8-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="91fa8-107">から`true`アプリケーションの開発者によって作成されたコードのみをステップ実行するには、をに設定します。それ以外の場合はに設定 `false` します。</span><span class="sxs-lookup"><span data-stu-id="91fa8-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91fa8-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="91fa8-108">Requirements</span></span>  
 <span data-ttu-id="91fa8-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91fa8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91fa8-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91fa8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91fa8-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91fa8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91fa8-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91fa8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
