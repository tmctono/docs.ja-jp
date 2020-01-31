---
title: ICorDebugProcess::ModifyLogSwitch メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ModifyLogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ModifyLogSwitch
helpviewer_keywords:
- ICorDebugProcess::ModifyLogSwitch method [.NET Framework debugging]
- ModifyLogSwitch method [.NET Framework debugging]
ms.assetid: 5fd30875-555e-4e96-877b-5dd266cde7c4
topic_type:
- apiref
ms.openlocfilehash: 27e13e298c1be61018a92e53a0ee82c786729c7d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792581"
---
# <a name="icordebugprocessmodifylogswitch-method"></a><span data-ttu-id="09ae8-102">ICorDebugProcess::ModifyLogSwitch メソッド</span><span class="sxs-lookup"><span data-stu-id="09ae8-102">ICorDebugProcess::ModifyLogSwitch Method</span></span>
<span data-ttu-id="09ae8-103">指定されたログスイッチの重大度レベルを設定します。</span><span class="sxs-lookup"><span data-stu-id="09ae8-103">Sets the severity level of the specified log switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09ae8-104">構文</span><span class="sxs-lookup"><span data-stu-id="09ae8-104">Syntax</span></span>  
  
```cpp  
HRESULT ModifyLogSwitch(  
    [in] WCHAR *pLogSwitchName,  
    [in] LONG  lLevel);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09ae8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="09ae8-105">Parameters</span></span>  
 `pLogSwitchName`  
 <span data-ttu-id="09ae8-106">からログスイッチの名前を指定する文字列へのポインター。</span><span class="sxs-lookup"><span data-stu-id="09ae8-106">[in] A pointer to a string that specifies the name of the log switch.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="09ae8-107">から指定されたログスイッチに設定される重大度レベル。</span><span class="sxs-lookup"><span data-stu-id="09ae8-107">[in] The severity level to be set for the specified log switch.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09ae8-108">コメント</span><span class="sxs-lookup"><span data-stu-id="09ae8-108">Remarks</span></span>  
 <span data-ttu-id="09ae8-109">このメソッドは、によって実行される場合にのみ有効です: [: CreateProcess managedcallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md)コールバックが発生しました。</span><span class="sxs-lookup"><span data-stu-id="09ae8-109">This method is valid only after the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09ae8-110">要件</span><span class="sxs-lookup"><span data-stu-id="09ae8-110">Requirements</span></span>  
 <span data-ttu-id="09ae8-111">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09ae8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09ae8-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09ae8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09ae8-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09ae8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09ae8-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09ae8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
