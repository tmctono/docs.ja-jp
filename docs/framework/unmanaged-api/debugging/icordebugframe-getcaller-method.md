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
ms.openlocfilehash: 82902e6a395fe62464065ccea4cca5b52c960f0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988814"
---
# <a name="icordebugframegetcaller-method"></a><span data-ttu-id="5d743-102">ICorDebugFrame::GetCaller メソッド</span><span class="sxs-lookup"><span data-stu-id="5d743-102">ICorDebugFrame::GetCaller Method</span></span>
<span data-ttu-id="5d743-103">このフレームと呼ばれる現在のチェーンで ICorDebugFrame オブジェクトへのポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d743-103">Gets a pointer to the ICorDebugFrame object in the current chain that called this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d743-104">構文</span><span class="sxs-lookup"><span data-stu-id="5d743-104">Syntax</span></span>  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d743-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d743-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="5d743-106">[out]アドレスへのポインター、`ICorDebugFrame`呼び出し元のフレームを表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5d743-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the calling frame.</span></span> <span data-ttu-id="5d743-107">この値が呼び出されたフレームが現在のチェーン内の最も外側のフレームの場合は null です。</span><span class="sxs-lookup"><span data-stu-id="5d743-107">This value is null if the called frame is the outermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d743-108">必要条件</span><span class="sxs-lookup"><span data-stu-id="5d743-108">Requirements</span></span>  
 <span data-ttu-id="5d743-109">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d743-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d743-110">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d743-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d743-111">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d743-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d743-112">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d743-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
