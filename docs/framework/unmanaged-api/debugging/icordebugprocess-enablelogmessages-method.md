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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe237ca01d409636f184930d26ca970d58e90437
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749521"
---
# <a name="icordebugprocessenablelogmessages-method"></a><span data-ttu-id="1ef53-102">ICorDebugProcess::EnableLogMessages メソッド</span><span class="sxs-lookup"><span data-stu-id="1ef53-102">ICorDebugProcess::EnableLogMessages Method</span></span>
<span data-ttu-id="1ef53-103">でき、デバッガーのログ メッセージの送信を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1ef53-103">Enables and disables the transmission of log messages to the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef53-104">構文</span><span class="sxs-lookup"><span data-stu-id="1ef53-104">Syntax</span></span>  
  
```  
HRESULT EnableLogMessages([in]BOOL fOnOff);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ef53-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1ef53-105">Parameters</span></span>  
 `fOnOff`  
 <span data-ttu-id="1ef53-106">[in]`true` ; のログ メッセージの転送が可能`false`転送を無効にします。</span><span class="sxs-lookup"><span data-stu-id="1ef53-106">[in] `true` enables the transmission of log messages; `false` disables the transmission.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ef53-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ef53-107">Remarks</span></span>  
 <span data-ttu-id="1ef53-108">このメソッドが後でのみ有効では、 [icordebugmanagedcallback::createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)コールバックが発生します。</span><span class="sxs-lookup"><span data-stu-id="1ef53-108">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback occurs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ef53-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="1ef53-109">Requirements</span></span>  
 <span data-ttu-id="1ef53-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ef53-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ef53-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ef53-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ef53-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ef53-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ef53-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ef53-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
