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
ms.openlocfilehash: c5d81564a34ed8e7ef75840e3a174661c36f5411
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994496"
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="e17ff-102">ICorDebugProcess::GetHandle メソッド</span><span class="sxs-lookup"><span data-stu-id="e17ff-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="e17ff-103">プロセスを識別するハンドルを取得します。</span><span class="sxs-lookup"><span data-stu-id="e17ff-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e17ff-104">構文</span><span class="sxs-lookup"><span data-stu-id="e17ff-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e17ff-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e17ff-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="e17ff-106">[out]ポインター、`HPROCESS`はプロセスを識別するハンドル。</span><span class="sxs-lookup"><span data-stu-id="e17ff-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e17ff-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e17ff-107">Remarks</span></span>  
 <span data-ttu-id="e17ff-108">取得されたハンドルは、デバッグのインターフェイスが所有します。</span><span class="sxs-lookup"><span data-stu-id="e17ff-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="e17ff-109">デバッガーでは、使用する前に、ハンドルを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e17ff-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e17ff-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="e17ff-110">Requirements</span></span>  
 <span data-ttu-id="e17ff-111">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e17ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e17ff-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e17ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e17ff-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e17ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e17ff-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e17ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
