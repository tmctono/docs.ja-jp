---
title: ICorDebugStepper::SetRangeIL メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9b4ee64022374cb4e1950acceb3f32925b736bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994288"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="c4ead-102">ICorDebugStepper::SetRangeIL メソッド</span><span class="sxs-lookup"><span data-stu-id="c4ead-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="c4ead-103">指定する値を設定するかどうかを呼び出す[icordebugstepper::steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)または Microsoft の基準としたネイティブ コードへの相対値の中間言語 (MSIL) コードがステップで実行されているメソッドの引数を渡す使用します。</span><span class="sxs-lookup"><span data-stu-id="c4ead-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4ead-104">構文</span><span class="sxs-lookup"><span data-stu-id="c4ead-104">Syntax</span></span>  
  
```  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4ead-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c4ead-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="c4ead-106">[in]設定`true`範囲が MSIL コードの基準としたことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ead-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="c4ead-107">設定`false`範囲がネイティブ コードの基準としたことを指定します。</span><span class="sxs-lookup"><span data-stu-id="c4ead-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="c4ead-108">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="c4ead-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4ead-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="c4ead-109">Requirements</span></span>  
 <span data-ttu-id="c4ead-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4ead-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4ead-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4ead-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4ead-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4ead-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4ead-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4ead-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
