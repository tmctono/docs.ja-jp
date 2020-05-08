---
title: ICorDebugEval::NewString メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: b263fed7db5cb2ef687da45f8cbc99a02e1e3ea2
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976136"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="eebb5-102">ICorDebugEval::NewString メソッド</span><span class="sxs-lookup"><span data-stu-id="eebb5-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="eebb5-103">指定された内容を持つ新しい文字列インスタンスを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="eebb5-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eebb5-104">構文</span><span class="sxs-lookup"><span data-stu-id="eebb5-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eebb5-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eebb5-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="eebb5-106">から文字列のコンテンツへのポインター。</span><span class="sxs-lookup"><span data-stu-id="eebb5-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eebb5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="eebb5-107">Remarks</span></span>  
 <span data-ttu-id="eebb5-108">文字列は常に、スレッドが現在実行されているアプリケーションドメインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="eebb5-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eebb5-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="eebb5-109">Requirements</span></span>  
 <span data-ttu-id="eebb5-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eebb5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eebb5-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eebb5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eebb5-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eebb5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eebb5-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eebb5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
