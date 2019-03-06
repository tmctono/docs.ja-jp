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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496379"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="9a945-102">ICorDebugAppDomain::IsAttached メソッド</span><span class="sxs-lookup"><span data-stu-id="9a945-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="9a945-103">アプリケーション ドメインに、デバッガーがアタッチされているかどうかを示す値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9a945-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a945-104">構文</span><span class="sxs-lookup"><span data-stu-id="9a945-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a945-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a945-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="9a945-106">[out]`true`デバッガーがアプリケーション ドメインに接続されている。 それ以外の場合`false`します。</span><span class="sxs-lookup"><span data-stu-id="9a945-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a945-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="9a945-107">Remarks</span></span>  
 <span data-ttu-id="9a945-108">ICorDebugController メソッドは、アプリケーション ドメインに、デバッガーがアタッチされるまで使用できません。</span><span class="sxs-lookup"><span data-stu-id="9a945-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a945-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="9a945-109">Requirements</span></span>  
 <span data-ttu-id="9a945-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a945-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a945-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a945-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a945-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a945-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a945-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a945-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
