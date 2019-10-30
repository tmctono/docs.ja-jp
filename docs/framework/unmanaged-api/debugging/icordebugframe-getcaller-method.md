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
ms.openlocfilehash: 843399b7e3de522e2c4574963897430aa60a5a50
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114795"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="aec29-102">ICorDebugFrame::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="aec29-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="aec29-103">このフレームを呼び出した現在のチェーン内のテキストボックスオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="aec29-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec29-104">構文</span><span class="sxs-lookup"><span data-stu-id="aec29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aec29-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aec29-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="aec29-106">入出力呼び出し元のフレームを表す `ICorDebugFrame` オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="aec29-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="aec29-107">呼び出されたフレームが現在のチェーンの最も外側のフレームである場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="aec29-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec29-108">［要件］</span><span class="sxs-lookup"><span data-stu-id="aec29-108">Requirements</span></span>  
 <span data-ttu-id="aec29-109">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aec29-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec29-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aec29-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aec29-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aec29-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aec29-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec29-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
