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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fced656168952c1064de213405147baf7856b2c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737359"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="d58b3-102">ICorDebugAssembly::GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="d58b3-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="d58b3-103">これを含むアプリケーション ドメインへのインターフェイス ポインターを取得`ICorDebugAssembly`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="d58b3-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="d58b3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d58b3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d58b3-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="d58b3-106">[out]アプリケーション ドメインを表す ICorDebugAppDomain インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="d58b3-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d58b3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="d58b3-107">Remarks</span></span>  
 <span data-ttu-id="d58b3-108">このアセンブリは、システム アセンブリ場合`GetAppDomain`は null を返します。</span><span class="sxs-lookup"><span data-stu-id="d58b3-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58b3-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="d58b3-109">Requirements</span></span>  
 <span data-ttu-id="d58b3-110">**プラットフォーム:** [システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d58b3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58b3-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d58b3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d58b3-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d58b3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d58b3-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58b3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
