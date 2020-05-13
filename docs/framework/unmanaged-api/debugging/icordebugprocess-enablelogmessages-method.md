---
title: ICorDebugProcess::EnableLogMessages メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnableLogMessages
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnableLogMessages
helpviewer_keywords:
- ICorDebugProcess::EnableLogMessages method [.NET Framework debugging]
- EnableLogMessages method [.NET Framework debugging]
ms.assetid: 14a4e5a3-3eaf-4f53-9dd1-762726963a23
topic_type:
- apiref
ms.openlocfilehash: 3b850a462ce354b81f4406fce7fd9d8d9b6013d8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207903"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="5da72-102">ICorDebugProcess::EnableLogMessages メソッド</span><span class="sxs-lookup"><span data-stu-id="5da72-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="5da72-103">デバッガーへのログメッセージの転送を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="5da72-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da72-104">構文</span><span class="sxs-lookup"><span data-stu-id="5da72-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5da72-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5da72-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="5da72-106">[入力] `true`ログメッセージの転送を有効にします。`false`転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="5da72-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5da72-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5da72-107">Remarks</span></span>  
 <span data-ttu-id="5da72-108">このメソッドは、によって実行される場合にのみ有効です: [: CreateProcess managedcallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md)コールバックが発生します。</span><span class="sxs-lookup"><span data-stu-id="5da72-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da72-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="5da72-109">Requirements</span></span>  
 <span data-ttu-id="5da72-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5da72-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da72-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5da72-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5da72-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da72-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
