---
title: ICorDebugAppDomain::IsAttached メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: a2f6df7647ffe9f2adff963b6629ed29ece053c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895158"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="77848-102">ICorDebugAppDomain::IsAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="77848-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="77848-103">デバッガーがアプリケーションドメインにアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="77848-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77848-104">構文</span><span class="sxs-lookup"><span data-stu-id="77848-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77848-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="77848-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="77848-106">入出力`true`デバッガーがアプリケーションドメインにアタッチされている場合は。それ以外`false`の場合は。</span><span class="sxs-lookup"><span data-stu-id="77848-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77848-107">解説</span><span class="sxs-lookup"><span data-stu-id="77848-107">Remarks</span></span>  
 <span data-ttu-id="77848-108">このデバッガーがアプリケーションドメインにアタッチされるまでは、このコントロールメソッドを使用できません。</span><span class="sxs-lookup"><span data-stu-id="77848-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77848-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="77848-109">Requirements</span></span>  
 <span data-ttu-id="77848-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77848-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77848-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77848-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77848-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77848-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77848-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77848-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
