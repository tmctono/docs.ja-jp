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
ms.openlocfilehash: 909bcad035516c494d1f867b71bb8f52939eba13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993994"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="da836-102">ICorDebugThread::GetRegisterSet メソッド</span><span class="sxs-lookup"><span data-stu-id="da836-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="da836-103">この ICorDebugThread オブジェクトのアクティブな部分に関連付けられている登録のセットにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="da836-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da836-104">構文</span><span class="sxs-lookup"><span data-stu-id="da836-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da836-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da836-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="da836-106">[out]アドレスへのポインター、 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)レジスタを表すインターフェイス オブジェクトをこのスレッドのアクティブな部分を設定します。</span><span class="sxs-lookup"><span data-stu-id="da836-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da836-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="da836-107">Requirements</span></span>  
 <span data-ttu-id="da836-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="da836-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da836-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da836-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da836-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da836-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da836-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da836-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
