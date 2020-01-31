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
ms.openlocfilehash: 6b1ccffa4f24122e643a64270f44945afdbc8fff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792648"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="34292-102">ICorDebugProcess::EnableLogMessages メソッド</span><span class="sxs-lookup"><span data-stu-id="34292-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="34292-103">デバッガーへのログメッセージの転送を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="34292-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34292-104">構文</span><span class="sxs-lookup"><span data-stu-id="34292-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34292-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="34292-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="34292-106">[in] `true` では、ログメッセージを転送できます。`false` は、転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="34292-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34292-107">コメント</span><span class="sxs-lookup"><span data-stu-id="34292-107">Remarks</span></span>  
 <span data-ttu-id="34292-108">このメソッドは、によって実行される場合にのみ有効です: [: CreateProcess managedcallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md)コールバックが発生します。</span><span class="sxs-lookup"><span data-stu-id="34292-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34292-109">要件</span><span class="sxs-lookup"><span data-stu-id="34292-109">Requirements</span></span>  
 <span data-ttu-id="34292-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="34292-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34292-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34292-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34292-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34292-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34292-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34292-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
