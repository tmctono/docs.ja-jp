---
title: ICorDebugAssembly::GetProcess メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aeadcbd8f2d09320645c36fdc771cfb2cb976036
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645540"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="3e26d-102">ICorDebugAssembly::GetProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="3e26d-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="3e26d-103">この ICorDebugAssembly インスタンスが実行されているプロセスにインターフェイス ポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="3e26d-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e26d-104">構文</span><span class="sxs-lookup"><span data-stu-id="3e26d-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e26d-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e26d-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3e26d-106">[out]プロセスを表す ICorDebugProcess インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="3e26d-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e26d-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="3e26d-107">Requirements</span></span>  
 <span data-ttu-id="3e26d-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e26d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e26d-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3e26d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3e26d-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e26d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e26d-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e26d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
