---
title: ICorDebugProcess::GetID メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetID
helpviewer_keywords:
- GetID method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetID method [.NET Framework debugging]
ms.assetid: b0ba8453-fa7e-4c14-93e5-335409cd4a47
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d9239ccfe8ce08e5b50b762a6fede11ab8a439b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994495"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="44f2a-102">ICorDebugProcess::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="44f2a-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="44f2a-103">プロセスのオペレーティング システム (OS) の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="44f2a-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f2a-104">構文</span><span class="sxs-lookup"><span data-stu-id="44f2a-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f2a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="44f2a-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="44f2a-106">[out]プロセスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="44f2a-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f2a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="44f2a-107">Requirements</span></span>  
 <span data-ttu-id="44f2a-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="44f2a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f2a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44f2a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44f2a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44f2a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44f2a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f2a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
