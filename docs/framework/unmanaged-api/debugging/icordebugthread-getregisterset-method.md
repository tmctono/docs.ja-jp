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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8769293364c111754f4bfe9360a0dca93c0ba13c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770608"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="7ed24-102">ICorDebugThread::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="7ed24-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="7ed24-103">この ICorDebugThread オブジェクトのアクティブな部分に関連付けられている登録のセットにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ed24-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ed24-104">構文</span><span class="sxs-lookup"><span data-stu-id="7ed24-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ed24-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ed24-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="7ed24-106">[out]アドレスへのポインター、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)レジスタを表すインターフェイス オブジェクトをこのスレッドのアクティブな部分を設定します。</span><span class="sxs-lookup"><span data-stu-id="7ed24-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ed24-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="7ed24-107">Requirements</span></span>  
 <span data-ttu-id="7ed24-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ed24-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ed24-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ed24-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ed24-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ed24-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ed24-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ed24-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
