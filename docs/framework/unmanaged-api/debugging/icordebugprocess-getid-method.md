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
ms.openlocfilehash: 8cd40ffb60bf837a9aa3b0db34892350a05964d7
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213284"
---
# <a name="icordebugprocessgetid-method"></a><span data-ttu-id="b0816-102">ICorDebugProcess::GetID メソッド</span><span class="sxs-lookup"><span data-stu-id="b0816-102">ICorDebugProcess::GetID Method</span></span>
<span data-ttu-id="b0816-103">プロセスのオペレーティングシステム (OS) ID を取得します。</span><span class="sxs-lookup"><span data-stu-id="b0816-103">Gets the operating system (OS) ID of the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0816-104">構文</span><span class="sxs-lookup"><span data-stu-id="b0816-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID([out] DWORD *pdwProcessId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0816-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b0816-105">Parameters</span></span>  
 `pdwProcessId`  
 <span data-ttu-id="b0816-106">入出力プロセスの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="b0816-106">[out] The unique ID of the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0816-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="b0816-107">Requirements</span></span>  
 <span data-ttu-id="b0816-108">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0816-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0816-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0816-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0816-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0816-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0816-111">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0816-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
