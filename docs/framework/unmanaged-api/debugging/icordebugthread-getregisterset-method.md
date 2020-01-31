---
title: ICorDebugThread::GetRegisterSet メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
ms.openlocfilehash: 9793424e79ed878b04a5c51daad08b5d12d439e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791466"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="2feb6-102">ICorDebugThread::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="2feb6-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="2feb6-103">このコンポーネントオブジェクトのアクティブな部分に関連付けられているレジスタセットへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="2feb6-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2feb6-104">構文</span><span class="sxs-lookup"><span data-stu-id="2feb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2feb6-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2feb6-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="2feb6-106">入出力このスレッドのアクティブな部分のレジスタセットを[表す、の](icordebugregisterset-interface.md)オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2feb6-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2feb6-107">要件</span><span class="sxs-lookup"><span data-stu-id="2feb6-107">Requirements</span></span>  
 <span data-ttu-id="2feb6-108">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2feb6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2feb6-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2feb6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2feb6-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2feb6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2feb6-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2feb6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
