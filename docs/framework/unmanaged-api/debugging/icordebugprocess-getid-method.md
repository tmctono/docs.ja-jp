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
ms.openlocfilehash: 9ebdf0dd2457cd10e31ff71c32b1c09d0e014431
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765986"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="ad999-102">ICorDebugProcess::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="ad999-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="ad999-103">プロセスのオペレーティング システム (OS) の ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad999-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad999-104">構文</span><span class="sxs-lookup"><span data-stu-id="ad999-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad999-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ad999-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="ad999-106">[out]プロセスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ad999-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad999-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="ad999-107">Requirements</span></span>  
 <span data-ttu-id="ad999-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad999-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad999-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad999-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad999-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad999-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad999-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad999-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
