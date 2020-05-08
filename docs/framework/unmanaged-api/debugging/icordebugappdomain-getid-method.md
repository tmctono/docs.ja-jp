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
ms.openlocfilehash: 63346c679efc083dea9ab0eaa4f983a5308695f8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895253"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="692fb-102">ICorDebugAppDomain::GetId メソッド</span><span class="sxs-lookup"><span data-stu-id="692fb-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="692fb-103">アプリケーションドメインの一意の識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="692fb-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="692fb-104">構文</span><span class="sxs-lookup"><span data-stu-id="692fb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="692fb-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="692fb-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="692fb-106">入出力アプリケーションドメインの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="692fb-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="692fb-107">解説</span><span class="sxs-lookup"><span data-stu-id="692fb-107">Remarks</span></span>  
 <span data-ttu-id="692fb-108">アプリケーションドメインの識別子は、含まれているプロセス内で一意です。</span><span class="sxs-lookup"><span data-stu-id="692fb-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="692fb-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="692fb-109">Requirements</span></span>  
 <span data-ttu-id="692fb-110">**:**「[システム要件](../../get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="692fb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="692fb-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="692fb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="692fb-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="692fb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="692fb-113">**.NET Framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="692fb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
