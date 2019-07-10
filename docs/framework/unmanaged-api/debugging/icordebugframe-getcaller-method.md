---
title: ICorDebugFrame::GetCaller メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCaller
helpviewer_keywords:
- GetCaller method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCaller method [.NET Framework debugging]
ms.assetid: bfdc946b-8238-4eb9-8a85-884049fb0fd4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a637cebb9e1aef20c600353eb14fe900ad7513c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754159"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="fc66a-102">ICorDebugFrame::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="fc66a-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="fc66a-103">このフレームと呼ばれる現在のチェーンで ICorDebugFrame オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="fc66a-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc66a-104">構文</span><span class="sxs-lookup"><span data-stu-id="fc66a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc66a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fc66a-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="fc66a-106">[out]アドレスへのポインター、`ICorDebugFrame`呼び出し元のフレームを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fc66a-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="fc66a-107">この値が呼び出されたフレームが現在のチェーン内の最も外側のフレームの場合は null です。</span><span class="sxs-lookup"><span data-stu-id="fc66a-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc66a-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="fc66a-108">Requirements</span></span>  
 <span data-ttu-id="fc66a-109">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc66a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc66a-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc66a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc66a-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc66a-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc66a-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc66a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
