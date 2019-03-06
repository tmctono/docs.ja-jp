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
ms.openlocfilehash: a9ba09b80d7118b0ccd9b1647011a7fc7cd74e22
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485110"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="0b963-102">ICorDebugAssembly::GetAppDomain メソッド</span><span class="sxs-lookup"><span data-stu-id="0b963-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="0b963-103">これを含むアプリケーション ドメインへのインターフェイス ポインターを取得`ICorDebugAssembly`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="0b963-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b963-104">構文</span><span class="sxs-lookup"><span data-stu-id="0b963-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b963-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b963-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0b963-106">[out]アプリケーション ドメインを表す ICorDebugAppDomain インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="0b963-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b963-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="0b963-107">Remarks</span></span>  
 <span data-ttu-id="0b963-108">このアセンブリは、システム アセンブリ場合`GetAppDomain`は null を返します。</span><span class="sxs-lookup"><span data-stu-id="0b963-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b963-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="0b963-109">Requirements</span></span>  
 <span data-ttu-id="0b963-110">**プラットフォーム:**[システム要件](../../../../docs/framework/get-started/system-requirements.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b963-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b963-111">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b963-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b963-112">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b963-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b963-113">**.NET Framework のバージョン:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b963-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
