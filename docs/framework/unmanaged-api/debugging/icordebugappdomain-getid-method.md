---
title: ICorDebugAppDomain::GetId メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb8917fa401db9424cff168fe0b06ad84065827c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737943"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="86ba7-102">ICorDebugAppDomain::GetId メソッド</span><span class="sxs-lookup"><span data-stu-id="86ba7-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="86ba7-103">アプリケーション ドメインの一意の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="86ba7-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86ba7-104">構文</span><span class="sxs-lookup"><span data-stu-id="86ba7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86ba7-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="86ba7-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="86ba7-106">[out]アプリケーション ドメインの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="86ba7-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86ba7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="86ba7-107">Remarks</span></span>  
 <span data-ttu-id="86ba7-108">アプリケーション ドメインの識別子は、格納しているプロセス内で一意です。</span><span class="sxs-lookup"><span data-stu-id="86ba7-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86ba7-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="86ba7-109">Requirements</span></span>  
 <span data-ttu-id="86ba7-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="86ba7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86ba7-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86ba7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86ba7-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86ba7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86ba7-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86ba7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
