---
title: ICorDebugProcess::GetHandle メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56f1dd892429724866182248b0c0413a7d2437cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766075"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="9a13e-102">ICorDebugProcess::GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="9a13e-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="9a13e-103">プロセスを識別するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="9a13e-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a13e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a13e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a13e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a13e-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="9a13e-106">[out]ポインター、`HPROCESS`はプロセスを識別するハンドル。</span><span class="sxs-lookup"><span data-stu-id="9a13e-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a13e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a13e-107">Remarks</span></span>  
 <span data-ttu-id="9a13e-108">取得されたハンドルは、デバッグのインターフェイスが所有します。</span><span class="sxs-lookup"><span data-stu-id="9a13e-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="9a13e-109">デバッガーでは、使用する前に、ハンドルを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a13e-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a13e-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a13e-110">Requirements</span></span>  
 <span data-ttu-id="9a13e-111">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a13e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a13e-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a13e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a13e-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a13e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a13e-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a13e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
