---
title: ICorDebugThread::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad87b6552df25926b5b4184b7884c1d444c4f1be
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769070"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="7c6ef-102">ICorDebugThread::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="7c6ef-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="7c6ef-103">この ICorDebugThread が、一部を形成するプロセスにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7c6ef-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6ef-104">構文</span><span class="sxs-lookup"><span data-stu-id="7c6ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c6ef-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7c6ef-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="7c6ef-106">[out]ICorDebugProcess インターフェイスを表すオブジェクトをプロセスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="7c6ef-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6ef-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="7c6ef-107">Requirements</span></span>  
 <span data-ttu-id="7c6ef-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c6ef-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6ef-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c6ef-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c6ef-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c6ef-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c6ef-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6ef-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
