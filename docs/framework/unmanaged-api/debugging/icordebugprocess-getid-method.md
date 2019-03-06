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
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495716"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="a3808-102">ICorDebugProcess::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="a3808-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="a3808-103">プロセスのオペレーティング システム (OS) の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="a3808-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3808-104">構文</span><span class="sxs-lookup"><span data-stu-id="a3808-104">Syntax</span></span>  
  
```  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3808-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a3808-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="a3808-106">[out]プロセスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="a3808-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3808-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3808-107">Requirements</span></span>  
 <span data-ttu-id="a3808-108">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3808-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3808-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3808-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3808-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3808-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3808-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3808-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
