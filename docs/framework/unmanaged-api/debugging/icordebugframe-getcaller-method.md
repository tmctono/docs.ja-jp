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
ms.openlocfilehash: b29de0b70daa783197e78fe985d379d4124bc140
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205146"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="1dabd-102">ICorDebugFrame::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="1dabd-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="1dabd-103">このフレームを呼び出した現在のチェーン内のテキストボックスオブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="1dabd-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dabd-104">構文</span><span class="sxs-lookup"><span data-stu-id="1dabd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1dabd-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1dabd-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="1dabd-106">入出力呼び出し元のフレームを表すオブジェクトのアドレスへのポインター `ICorDebugFrame` 。</span><span class="sxs-lookup"><span data-stu-id="1dabd-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="1dabd-107">呼び出されたフレームが現在のチェーンの最も外側のフレームである場合、この値は null になります。</span><span class="sxs-lookup"><span data-stu-id="1dabd-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1dabd-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="1dabd-108">Requirements</span></span>  
 <span data-ttu-id="1dabd-109">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dabd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dabd-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1dabd-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1dabd-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1dabd-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1dabd-112">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1dabd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
