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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988001"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="e8f2f-102">ICorDebugModule::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="e8f2f-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="e8f2f-103">このモジュールを格納しているプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e8f2f-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8f2f-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8f2f-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8f2f-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8f2f-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="e8f2f-106">[out]このモジュールを格納しているプロセスを表す ICorDebugProcess オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="e8f2f-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8f2f-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="e8f2f-107">Requirements</span></span>  
 <span data-ttu-id="e8f2f-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f2f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8f2f-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8f2f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8f2f-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8f2f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8f2f-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8f2f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
