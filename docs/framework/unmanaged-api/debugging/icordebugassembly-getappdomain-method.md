---
title: ICorDebugAssembly::GetAppDomain メソッド
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 53042e722809a6574396648529c677d749154716
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132738"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="c3b5e-102">ICorDebugAssembly::GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="c3b5e-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="c3b5e-103">この `ICorDebugAssembly` インスタンスを含むアプリケーションドメインへのインターフェイスポインターを取得します。</span><span class="sxs-lookup"><span data-stu-id="c3b5e-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b5e-104">構文</span><span class="sxs-lookup"><span data-stu-id="c3b5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b5e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3b5e-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="c3b5e-106">入出力アプリケーションドメインを表す、のアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="c3b5e-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b5e-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="c3b5e-107">Remarks</span></span>  
 <span data-ttu-id="c3b5e-108">このアセンブリがシステムアセンブリの場合、`GetAppDomain` は null を返します。</span><span class="sxs-lookup"><span data-stu-id="c3b5e-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b5e-109">［要件］</span><span class="sxs-lookup"><span data-stu-id="c3b5e-109">Requirements</span></span>  
 <span data-ttu-id="c3b5e-110">**:** 「[システム要件](../../../../docs/framework/get-started/system-requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3b5e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b5e-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3b5e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3b5e-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3b5e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3b5e-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
