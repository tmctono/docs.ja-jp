---
title: ICorDebugModule::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 97cecd66462cf6a88012b13dec82dbf617891dd5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493844"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="b9830-102">ICorDebugModule::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="b9830-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="b9830-103">このモジュールを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b9830-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9830-104">構文</span><span class="sxs-lookup"><span data-stu-id="b9830-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9830-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9830-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="b9830-106">[out]このモジュールを格納しているプロセスを表す ICorDebugProcess オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b9830-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9830-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b9830-107">Requirements</span></span>  
 <span data-ttu-id="b9830-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9830-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9830-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9830-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9830-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9830-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9830-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9830-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
