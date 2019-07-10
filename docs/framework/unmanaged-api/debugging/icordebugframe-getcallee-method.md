---
title: ICorDebugFrame::GetCallee メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10a5247632f242a4b4e0d33cf7fa7233d1b1e13b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754204"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="d6dc6-102">ICorDebugFrame::GetCallee メソッド</span><span class="sxs-lookup"><span data-stu-id="d6dc6-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="d6dc6-103">このフレームと呼ばれる現在のチェーンで ICorDebugFrame オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6dc6-104">構文</span><span class="sxs-lookup"><span data-stu-id="d6dc6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6dc6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d6dc6-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d6dc6-106">[out]アドレスへのポインター、`ICorDebugFrame`呼び出されたフレームを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="d6dc6-107">この値は、呼び出し元のフレームが現在のチェーン内の最も内側のフレームである場合は null です。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6dc6-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="d6dc6-108">Requirements</span></span>  
 <span data-ttu-id="d6dc6-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6dc6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6dc6-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6dc6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6dc6-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6dc6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6dc6-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6dc6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
