---
title: ICorDebugType::GetRank メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e42db5d7ebc9ec9983fe9e56477808415b26968b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751579"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="f3a0a-102">ICorDebugType::GetRank メソッド</span><span class="sxs-lookup"><span data-stu-id="f3a0a-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="f3a0a-103">配列型の次元数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f3a0a-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3a0a-104">構文</span><span class="sxs-lookup"><span data-stu-id="f3a0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3a0a-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3a0a-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="f3a0a-106">[out]ディメンションの数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="f3a0a-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3a0a-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="f3a0a-107">Requirements</span></span>  
 <span data-ttu-id="f3a0a-108">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3a0a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3a0a-109">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3a0a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3a0a-110">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3a0a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3a0a-111">**.NET Framework のバージョン:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a0a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
